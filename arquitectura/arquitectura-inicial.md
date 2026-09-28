# Arquitectura Inicial del Sistema

## Diagrama de arquitectura

```mermaid
flowchart TD

%% =========================
%% ACTORES
%% =========================
subgraph ACTORES["ACTORES"]
  Conductor["Conductor"]
  Ciudadano["Ciudadano"]
  Autoridad["Autoridad Vial\n(Provías / SUTRAN)"]
  Admin["Administrador"]
end

%% =========================
%% PRESENTACIÓN
%% =========================
subgraph PRESENTACION["PRESENTACIÓN"]
  AppAndroid["App Android → Kotlin + TFLite"]
  MapaWeb["Mapa Web → React + Leaflet"]
  Panel["Panel Institucional → React"]
end

%% =========================
%% LÓGICA DE NEGOCIO
%% =========================
subgraph NEGOCIO["LÓGICA DE NEGOCIO"]
  Deteccion["Detección y Clasificación"]
  Sincronizacion["Sincronización Offline"]
  Ingesta["Ingesta de Eventos"]
  Anomalias["Gestión de Anomalías"]
  Usuarios["Autenticación y Accesos"]
end

%% =========================
%% DATOS
%% =========================
subgraph DATOS["DATOS"]
  SQLite["SQLite · Buffer local"]
  Kafka["Kafka · Cola de mensajes"]
  Postgres["PostgreSQL + PostGIS"]
  Redis["Redis · Caché"]
end

%% =========================
%% SISTEMAS EXTERNOS
%% =========================
subgraph EXTERNOS["SISTEMAS EXTERNOS"]
  OSM["OpenStreetMap"]
  Cloudflare["Cloudflare · CDN + SSL"]
  FCM["Firebase Cloud Messaging"]
end

%% =========================
%% FLUJO PRINCIPAL
%% =========================
Conductor --> AppAndroid
Ciudadano --> MapaWeb
Autoridad --> Panel
Admin --> Panel

AppAndroid --> Deteccion
AppAndroid --> Sincronizacion
MapaWeb --> Anomalias
Panel --> Anomalias
Panel --> Usuarios

Deteccion --> SQLite
Sincronizacion --> Kafka
Ingesta --> Kafka
Ingesta --> Anomalias
Anomalias --> Postgres
Anomalias --> Redis
Usuarios --> Postgres

%% Sistemas externos
MapaWeb --> OSM
AppAndroid --> Cloudflare
AppAndroid --> FCM
```

## Descripción

La arquitectura se organiza en tres capas principales:

- **Presentación:** la app Android es el punto de entrada del conductor; el mapa web es accesible para cualquier ciudadano sin registro; el panel institucional requiere autenticación y está destinado a autoridades viales y administradores.

- **Lógica de negocio:** contiene los módulos de detección y clasificación de anomalías (ejecutados localmente en el dispositivo), sincronización offline con patrón Store-and-Forward, ingesta de eventos vía Kafka, gestión del mapa de anomalías y control de accesos por roles.

- **Datos:** SQLite actúa como buffer local en el dispositivo, Kafka absorbe la ráfaga de sincronizaciones simultáneas, PostgreSQL con PostGIS almacena las anomalías geolocalizadas y Redis gestiona la caché del mapa público.

El sistema nace como monolito modular. Cada módulo tiene responsabilidades claras y puede extraerse como servicio independiente conforme el sistema crezca, sin necesidad de reescribir la lógica de negocio.