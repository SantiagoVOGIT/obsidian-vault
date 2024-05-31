---
tags:
  - proyectos
---
|**Pipelines:**

- Sarlaft4_Back:
- https://dev.azure.com/SuraColombia/Gerencia_Tecnologia/_build?definitionScope=%5CEGV_ADM_Y_FIN%5CSarlaft4_Back

**Repositorios**

- 892-sarlaft-brms-ms:
- https://dev.azure.com/SuraColombia/Gerencia_Tecnologia/_git/892-sarlaft-brms-ms
- https://sonarqube.suramericana.com.co/solucionescorporativas/dashboard?id=892-sarlaft-brms-ms&branch=feature%2F470168-cambiar-azure-por-pipelines-b

- 892-sarlaft-api-ms
- https://dev.azure.com/SuraColombia/Gerencia_Tecnologia/_git/892-sarlaft-api-ms
- https://sonarqube.suramericana.com.co/solucionescorporativas/dashboard?branch=feature%2F470168-cambiar-azure-por-pipelines-a&id=892-sarlaft-api-ms

**Documentación**

- 892-sarlaft-brms:
- https://segurosti.atlassian.net/wiki/spaces/EPA/pages/1809941005/Motor+de+Evaluaci+n

- 892-sarlaft-api-ms:
- https://segurosti.atlassian.net/wiki/spaces/EPA/pages/1801159134/Microservicio+SarlaftAPI

Debido al tipo de cambio técnico que se realizo en los dos microservicios (pruebas unitarias), la prueba de implantación se da por exitosa debido a la ejecución del 100% de pruebas unitarias exitosas en el pipeline, además de la carga exitosa en SonarQube reflejándose así el porcentaje de cobertura deseado derivado de los criterios de aceptación en la plataforma.