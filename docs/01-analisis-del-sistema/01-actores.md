# Actores del Sistema

En v1.0 el sistema tiene solo dos actores activos para limitar el alcance para su desarrollo en este ciclo 2026-II. Los demás están identificados para versiones futuras.

| Actor | Tipo | Descripción | Interfaz |
|---|---|---|---|
| Conductor | Principal (v1.0) | Persona que transita la Vía Los Libertadores. Sus sensores detectan anomalías pasivamente. Puede ver el mapa del corredor. | App Android |
| Administrador | Principal (v1.0) | Gestiona el sistema: usuarios, anomalías, auditoría, dashboard global. Es personal de CRISSO DEV S.A.C. | Panel web |
| Empresa suscriptora | Futuro (v1.5+) | Empresas de transporte, aseguradoras. Acceden a analítica de flota y tramos. | Panel web |
| Autoridad Vial | Futuro (v2.0+) | Provías Nacional, SUTRAN, gobiernos regionales. Acceden bajo convenio institucional. | Panel web |

## Detalle de actores activos en v1.0

**Conductor no registrado:** Instala la app, sus sensores aportan datos anónimamente. Ve solo el tramo demo Ayacucho–Vinchos (~65 km). No requiere correo ni contraseña.

**Conductor registrado:** Se registra con correo verificado. Accede al mapa completo de 333 km, historial de recorridos (6 meses) y alertas anticipadas en ruta.

**Administrador:** Accede al panel web con correo y contraseña. Ve el mapa completo con todas las anomalías, estadísticas globales, gestión de usuarios y log de auditoría.