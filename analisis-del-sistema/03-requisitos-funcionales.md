# Requisitos Funcionales

| ID | Requisito funcional |
|---|---|
| RF-01 | El sistema debe detectar automáticamente anomalías del pavimento (baches, hundimientos, pavimento deteriorado y rompemuelles no señalizados) mientras el conductor recorre la vía, sin requerir ninguna acción manual durante el trayecto. |
| RF-02 | El sistema debe registrar la ubicación exacta de cada anomalía detectada con un margen de error no mayor a diez metros. |
| RF-03 | El sistema debe guardar todos los eventos detectados en el almacenamiento local del dispositivo cuando no hay conexión a internet. |
| RF-04 | El sistema debe sincronizar automáticamente los eventos acumulados hacia el servidor cuando el dispositivo recupere señal, sin intervención del usuario. |
| RF-05 | El sistema debe clasificar cada anomalía por tipo y por severidad (leve, moderada, grave) usando el modelo de aprendizaje automático embebido en la app. |
| RF-06 | El sistema debe alertar al conductor con al menos un kilómetro de anticipación cuando se aproxime a un tramo con anomalías graves reportadas en los últimos siete días. |
| RF-07 | El sistema debe mostrar un mapa de la Vía Los Libertadores con todas las anomalías reportadas en los últimos siete días, accesible desde cualquier navegador sin registro. |
| RF-08 | El sistema debe permitir filtrar las anomalías del mapa por tipo y por severidad. |
| RF-09 | El sistema debe presentar a las autoridades viales el ranking de kilómetros con mayor densidad de anomalías, actualizado diariamente. |
| RF-10 | El sistema debe permitir exportar los datos de anomalías en formato GeoJSON compatible con QGIS y ArcGIS. |
| RF-11 | El sistema debe autenticar el acceso al panel institucional mediante tokens con expiración máxima de ocho horas por sesión. |
| RF-12 | El sistema debe diferenciar tres niveles de acceso: ciudadano público (sin autenticación), autoridad vial y administrador. |
| RF-13 | El sistema debe anonimizar cada dispositivo emisor mediante un hash irreversible, sin almacenar ningún dato personal del conductor. |
| RF-14 | El sistema debe registrar en un log de auditoría cada cambio de estado relevante, con fecha, hora y responsable de la acción. |

## Relación entre historias de usuario y requisitos funcionales

| Historia de usuario | Requisitos funcionales relacionados |
|---|---|
| HU01 — Detección automática | RF-01, RF-02, RF-05 |
| HU02 — Alerta anticipada | RF-06 |
| HU03 — Funcionamiento sin señal | RF-03, RF-04 |
| HU04 — Consulta del mapa | RF-07, RF-08 |
| HU05 — Acceso sin registro | RF-07 |
| HU06 — Ranking de anomalías | RF-09 |
| HU07 — Exportación GeoJSON | RF-10 |
| HU08 — Gestión de accesos | RF-11, RF-12, RF-13, RF-14 |