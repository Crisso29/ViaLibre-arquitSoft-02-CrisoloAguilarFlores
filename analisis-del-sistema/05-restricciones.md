# Restricciones

| ID | Restricción | Descripción |
|---|---|---|
| RC-01 | Plataforma móvil | La aplicación debe desarrollarse exclusivamente para Android 8.0 o superior en Kotlin nativo, dado que representa el 87% del mercado peruano de smartphones. |
| RC-02 | Modelo embebido | La inferencia de anomalías debe ejecutarse dentro del dispositivo usando TensorFlow Lite, con un tamaño de modelo menor a 5 MB para no impactar el almacenamiento del usuario. |
| RC-03 | Almacenamiento local | El buffer offline debe implementarse con SQLite, la base de datos integrada en Android, sin dependencias externas adicionales. |
| RC-04 | Backend monolito modular | El backend debe desarrollarse como un monolito modular en .NET 8, con módulos internos bien separados que permitan migrar hacia servicios independientes en fases posteriores sin reescribir el código base. |
| RC-05 | Base de datos geoespacial | El almacenamiento de anomalías debe realizarse en PostgreSQL con la extensión PostGIS, que es el estándar para datos geoespaciales compatible con las herramientas del MTC (QGIS, ArcGIS). |
| RC-06 | Infraestructura gratuita | El sistema debe desplegarse sobre Oracle Cloud Free Tier (2 OCPU ARM + 12 GB RAM), con Cloudflare para CDN y SSL, manteniendo el costo operativo mensual en cero durante toda la vida del proyecto. |
| RC-07 | Control de versiones | Todo el código fuente y la configuración de infraestructura deben gestionarse en Git y mantenerse en un repositorio GitHub accesible para el docente. |
| RC-08 | Un solo desarrollador | El proyecto es ejecutado por un único desarrollador con dedicación de 20 horas semanales durante 16 semanas. |
| RC-09 | Presupuesto | El gasto en efectivo no puede superar S/ 200 durante toda la ejecución del proyecto. |
| RC-10 | Plazo académico | La entrega final debe completarse antes del cierre del semestre 2026-II según el calendario de la UNSCH. |