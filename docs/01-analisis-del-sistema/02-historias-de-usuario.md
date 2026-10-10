# Historias de Usuario

## EP-01: Detección automática de anomalías

| ID | Historia de usuario |
|---|---|
| HU-01 | Como conductor, quiero que la app detecte baches automáticamente mientras manejo, para no tener que hacer nada con el celular durante el viaje. |
| HU-02 | Como conductor, quiero que la app distinga entre tipos de anomalía (bache, grieta, inundación, curva peligrosa), para que la información sea útil para otros conductores. |

## EP-02: Operación offline y sincronización

| ID | Historia de usuario |
|---|---|
| HU-03 | Como conductor, quiero que la app siga detectando anomalías aunque no haya señal de celular, para no perder datos en los tramos remotos de la vía. |
| HU-04 | Como conductor, quiero que ningún evento detectado se pierda aunque la conexión falle a mitad de la sincronización, para que mis datos siempre lleguen al servidor. |

## EP-03: Gestión de anomalías en el servidor

| ID | Historia de usuario |
|---|---|
| HU-05 | Como sistema, necesito validar la calidad de cada evento recibido antes de mostrarlo en el mapa, para que solo aparezcan datos confiables. |
| HU-06 | Como administrador, quiero que el sistema distinga automáticamente baches permanentes de obstáculos temporales, para priorizar las alertas correctamente. |

## EP-04: Mapa y visualización para el conductor

| ID | Historia de usuario |
|---|---|
| HU-07 | Como conductor no registrado, quiero ver el mapa de anomalías del tramo Ayacucho–Vinchos, para conocer el estado de la vía antes de decidir registrarme. |
| HU-08 | Como conductor registrado, quiero ver el mapa completo del corredor de 333 km con las anomalías actualizadas, para planificar mi viaje con información real. |
| HU-09 | Como conductor registrado, quiero recibir alertas anticipadas de anomalías próximas durante mi viaje, para reducir la velocidad a tiempo. |
| HU-10 | Como conductor registrado, quiero ver mi historial de recorridos, para saber qué tramos he cubierto y cuántas anomalías detecté. |

## EP-05: Panel administrativo

| ID | Historia de usuario |
|---|---|
| HU-11 | Como administrador, quiero iniciar sesión en el panel web con mis credenciales, para acceder a la gestión del sistema de forma segura. |
| HU-12 | Como administrador, quiero ver el mapa completo del corredor con todas las anomalías detectadas, para monitorear el estado general de la vía. |
| HU-13 | Como administrador, quiero ver el dashboard con estadísticas globales del sistema, para tomar decisiones sobre el funcionamiento de la plataforma. |
| HU-14 | Como administrador, quiero gestionar los usuarios del sistema (crear, editar rol, desactivar), para mantener el control de acceso. |
| HU-15 | Como administrador, quiero ver el log de auditoría completo del sistema, para tener trazabilidad de todas las acciones sensibles. |

## EP-06: Infraestructura y despliegue

| ID | Historia de usuario |
|---|---|
| HU-16 | Como equipo de desarrollo, quiero que el sistema se despliegue con un solo comando, para que cualquier miembro pueda levantar el entorno de producción sin pasos manuales. |
| HU-17 | Como equipo de desarrollo, quiero monitorear la disponibilidad del sistema en tiempo real, para detectar caídas antes de que los usuarios las reporten. |