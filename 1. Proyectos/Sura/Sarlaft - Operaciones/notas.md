

Pendientes de Sarlaft 

- Una evaluación contiene todas las evidencias exitosas y no tiene ningún otro paso pendiente pero no se actualizo su estado a finalizada y se queda en pendiente.
	- **Frecuencia del error**: muy baja
	- **Causa**: desconocida
	- **Incidentes relacionados**:
	- **Propuesta**: agregar un nuevo servicio que permita al cliente refrescar el estado de una evaluación. El servicio debería poder hacer un análisis actual de la evaluación y refrescar su estado al correspondiente según las reglas de negocio.


- El correo de validación de identidad con XPERIAN no llega pese a que intenta reenviar en varias ocasiones 
- 

| Estado              | Si  | No  |
| ------------------- | --- | --- |
| Encolados           |     | x   |
| Servicio AKS caído  |     |     |
| Base de datos caída |     |     |
|                     |     |     |

Se identifica que fue un evento temporal y se soluciono de manera autónoma. 
No se presentaron reportes o afectaciones por parte de ningún usuario. 



- Se cierra debido a que no requería intervención técnica debido a que se identifico que el usuario no tenía la cámara y comerció al día
- La analista de negocio me reporto que al filtrar por ciertos números de identificación no se estaban mostrando las evaluaciones correspondientes a ese cliente en el frontend, pero en la base de datos si existían evaluaciones para ese usuario, mediante algunas pruebas y validaciones se identifico que el problema era porque el frontend insertaba un código de operación por defecto en la petición, que es el 01, y estas evaluaciones en la base de datos salían con el código de operación 07, entonces se estaban consultando estas evaluaciones por el código operación incorrecto, se hizo la prueba haciendo la peticion con el 07 y ya traia los resultados, se valido con la analista de negocio y se identifico que era porque este codigo no estaba autorizado.
- El otro incidente en donde una usuaria reportaba que tenia un error al matricular a unos cliente en las tablas paramétricas y 1

- Responsable principal de cara a la área de operaciones técnica de Sarlaft 4.0 (desde agosto)
	- Monitoreo y revisión constante de la salud de los servicios del aplicativo (microservicios, mensajería, bases de datos, logging, etc.)
	- Resolución y abordaje de incidentes técnicos en producción ya sean críticos o menores
	- Comunicación con los usuarios de negocio para el refinamiento en el abordaje de los incidentes.
- Desarrollo e implementación de nuevas funcionalidades abstraídas en historias de usuario mediante la colaboración con clientes no técnicos.
- Contribución activa en reuniones de planificación, revisión diaria de los avances del equipo y retroalimentación basada en los resultados trimestrales.
- Formación continua a través de cursos en plataformas educativas de pago, videos gratuitos, lectura de documentación, blogs, etc.
- Trabajo colaborativo y comunicación entre analistas, usuarios de negocio e integrantes de otros equipos.

- Alrededor de 8 historias de usuario cerradas y en producción
- Aumento del 20% en la cobertura de test unitarios del servicio Sarlaft API
- Más de 35 intervenciones técnicas de incidencias en producción (apoyo en general en procesos, facilitación de recursos e información, resolución de incidencias directas)
- Alrededor de más de 20 incidentes cerrados

Como desarrollador de software con experiencia en el sector de seguros, he contribuido al éxito de proyectos críticos a través de:

- Desarrollo e implementación de nuevas funcionalidades abstraídas en historias de usuario mediante la colaboración con clientes no técnicos.
- Optimización de estructuras y consultas de bases de datos para soportar operaciones a gran escala o que presentaban deficiencia.
- Análisis sistemático y resolución eficiente de incidencias críticas en entornos de producción.
- Implementación de soluciones rápidas sin comprometer la estabilidad del sistema a largo plazo.
- Facilitación de la comunicación entre equipos técnicos y no técnicos para alinear objetivos y expectativas.
- Contribución activa en reuniones de planificación, revisión diaria de los avances del equipo y retroalimentación basada en los resultados trimestrales.
- Desarrollo de suites de pruebas automatizadas para garantizar la confiabilidad del software.
- Contribución a la implementación de prácticas de integración y despliegue continuo (CI/CD).
- Demostración de iniciativa en la adquisición de habilidades técnicas y blandas para potenciar mi rendimiento en el equipo mediante la participación en charlas y reuniones de formación.
- Formación continua a través de cursos en plataformas educativas de pago, videos gratuitos, lectura de documentación, blogs, etc.
- Aplicación práctica del conocimiento adquirido mediante el desarrollo de proyectos personales en mis espacios libres.
- Aprovechamiento de la experiencia de compañeros más experimentados, buscando activamente retroalimentación y oportunidades de aprendizaje colaborativo.


1. **Desarrollo e Innovación**:
    - Desarrollo e implementación de nuevas funcionalidades abstraídas en historias de usuario mediante la colaboración con clientes no técnicos.
2. **Gestión de Datos y Rendimiento**:
    - Optimización de estructuras y consultas de bases de datos para soportar operaciones a gran escala o que presentaban deficiencia.
3. **Resolución de Problemas y Mantenimiento**:
    - Análisis sistemático y resolución eficiente de incidencias críticas en entornos de producción.
    - Implementación de soluciones rápidas sin comprometer la estabilidad del sistema a largo plazo.
4. **Colaboración y Comunicación**:
    - Facilitación de la comunicación entre equipos técnicos y no técnicos para alinear objetivos y expectativas.
    - Contribución activa en reuniones de planificación, revisión diaria de los avances del equipo y retroalimentación basada en los resultados trimestrales.
6. **Automatización y Pruebas**:
    - Desarrollo de suites de pruebas automatizadas para garantizar la confiabilidad del software.
    - Contribución a la implementación de prácticas de integración y despliegue continuo (CI/CD).
7. **Aprendizaje y Adaptabilidad**:
	- Demostración de iniciativa en la adquisición de habilidades técnicas y blandas para potenciar mi rendimiento en el equipo mediante la participación en charlas y reuniones de formación.
	- Formación continua a través de cursos en plataformas educativas de pago, videos gratuitos, lectura de documentación, blogs, etc.
	- Aplicación práctica del conocimiento adquirido mediante el desarrollo de proyectos personales en mis espacios libres.
	- Aprovechamiento de la experiencia de compañeros más experimentados, buscando activamente retroalimentación y oportunidades de aprendizaje colaborativo.




**Bases de datos (PDN):**
- Transaccional (core): `psql-srsarlaftp7fca05e4`
- No transaccional: (backup, administrativo): `psql-srsarlaftpba1b6649`

index="idx_sarlaft4_err" "modulo=FUNCTION-WEBHOOK" "*WebhookRestAdapterRest.notificationPost*"



```
SELECT *  
FROM sarlaft.tsaf_evaluacion  
WHERE nmevaluacion = ''
```

```
SELECT *  
FROM sarlaft.tsaf_cliente  
WHERE nmidentificacion = ''
```


![[{B11BA439-E9B5-4BBE-B3D1-BA7E301FBA32}.png]]

![[{B4EE05FA-E0F8-4D20-9EF4-29708D25FB6B}.png]]