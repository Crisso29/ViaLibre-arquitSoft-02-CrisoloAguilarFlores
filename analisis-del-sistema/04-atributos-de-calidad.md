# Atributos de Calidad

| ID | Atributo de calidad | Escenario |
|---|---|---|
| AC-01 | **Rendimiento** | La app debe clasificar cada anomalía en menos de 50 ms usando el modelo embebido, para que el conductor no perciba ningún retraso entre el bache y el registro del evento. |
| AC-02 | **Disponibilidad** | El servidor debe mantenerse operativo el 99.5% del tiempo mensual, considerando que las autoridades viales consultan el panel todos los días para planificar el mantenimiento de la vía. |
| AC-03 | **Operación sin conexión** | La app debe funcionar de forma completa sin señal durante todo el trayecto, dado que más del 50% de la Vía Los Libertadores no tiene cobertura celular estable. |
| AC-04 | **Seguridad** | Ningún dato que permita identificar al conductor debe quedar almacenado en el servidor, cumpliendo con la Ley de Protección de Datos Personales N° 29733 del Perú. |
| AC-05 | **Mantenibilidad** | El sistema debe estar organizado en módulos independientes para que un cambio en la lógica de detección no afecte al mapa web ni al panel institucional. |
| AC-06 | **Eficiencia de recursos** | La app no debe consumir más del 8% de batería por hora activa ni más de 1 MB de datos móviles por hora de viaje, para no perjudicar al conductor durante trayectos largos. |
| AC-07 | **Capacidad de carga** | El backend debe procesar sin degradación la sincronización simultánea de hasta 300 dispositivos, situación típica cuando los conductores recuperan señal al entrar a zonas urbanas como Huamanga o Pisco. |