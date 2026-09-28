# Arquitectura Inicial del Sistema

## Diagrama de arquitectura

```mermaid
flowchart TD

subgraph ACTORES["ACTORES"]
  Conductor["Conductor"]
  Ciudadano["Ciudadano"]
  Autoridad["Autoridad Vial"]
  Admin["Administrador"]
end

subgraph PRESENTACION["PRESENTACIÓN"]
  AppAndroid["App Android\nKotlin + TFLite"]
  MapaWeb["Mapa Web\nReact + Leaflet"]
  Panel["Panel Institucional\nReact"]
end

subgraph NEGOCIO["LÓGICA DE NEGOCIO"]
  Deteccion["Detección y Clasificación"]
  Sincronizacion["Sincronización Offline"]
  Ingesta["Ingesta de Eventos"]
  Anomalias["Gestión de Anomalías"]
  Usuarios["Autenticación y Accesos"]
end

subgraph DATOS["DATOS"]
  SQLite["SQLite\nBuffer local"]
  Kafka["Kafka\nCola de mensajes"]
  Postgres["PostgreSQL + PostGIS"]
  Redis["Redis · Caché"]
end

subgraph EXTERNOS["SISTEMAS EXTERNOS"]
  OSM["OpenStreetMap"]
  Cloudflare["Cloudflare\nCDN + SSL"]
  FCM["Firebase\nCloud Messaging"]
end

Conductor --> AppAndroid
Ciudadano --> MapaWeb
Autoridad --> Panel
Admin --> Panel

ACTORES --> PRESENTACION
PRESENTACION --> NEGOCIO
NEGOCIO --> DATOS
DATOS -->|integraciones| EXTERNOS

Conductor ~~~ Ciudadano
Ciudadano ~~~ Autoridad
Autoridad ~~~ Admin

Deteccion ~~~ Sincronizacion
Sincronizacion ~~~ Ingesta
Ingesta ~~~ Anomalias
Anomalias ~~~ Usuarios

SQLite ~~~ Kafka
Kafka ~~~ Postgres
Postgres ~~~ Redis

OSM ~~~ Cloudflare
Cloudflare ~~~ FCM
```

## Descripción

La arquitectura se organiza en tres capas principales:

- **Presentación:** la app Android es el punto de entrada del conductor; el mapa web es accesible para cualquier ciudadano sin registro; el panel institucional requiere autenticación y está destinado a autoridades viales y administradores.

- **Lógica de negocio:** contiene los módulos de detección y clasificación de anomalías, sincronización offline con patrón Store-and-Forward, ingesta de eventos vía Kafka, gestión del mapa de anomalías y control de accesos por roles.

- **Datos:** SQLite actúa como buffer local en el dispositivo, Kafka absorbe la ráfaga de sincronizaciones simultáneas, PostgreSQL con PostGIS almacena las anomalías geolocalizadas y Redis gestiona la caché del mapa público.

El sistema nace como monolito modular. Cada módulo tiene responsabilidades claras y puede extraerse como servicio independiente conforme el sistema crezca, sin necesidad de reescribir la lógica de negocio.