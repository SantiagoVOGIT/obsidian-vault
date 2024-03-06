- [x] Los microservicios de Sarlaftapi, SarlaftEngine deben tener su pipeline de despliegue con la ultima versión de la plantilla de despliegues Gerencia_Tecnologia/ti-templates_pipelines-conf (branch master) para los ambientes de desarrollo, laboratorio y producción. ✅ 2024-02-28

- [x] Los pipelines mencionados en el criterio 1 debe contar con configuración para correr con análisis estático en sonarqube de Sura. ✅ 2024-02-28

- [ ] El pipeline mencionado en el criterio 1 debe contar con configuración para correr pruebas de soapui y jmeter, aplica para Sarlaftapi

- [ ] El análisis estático de Sarlaftapi, SarlaftEngine debe tener cobertura mínimo del 95%, ~~mantenibilidad en 0~~,  ~~code smell en 0~~, ~~código duplicado 0~~, ~~bugs 0~~ , ~~vulnerabilidades 0,~~ ~~security hotspots 0~~

- [x] Los pipelines deben crearse en la carpeta Sarlaft4_Back [https://dev.azure.com/SuraColombia/Gerencia_Tecnologia/_build?definitionScope=%5CEGV_ADM_Y_FIN%5CSarlaft4_Back](https://dev.azure.com/SuraColombia/Gerencia_Tecnologia/_build?definitionScope=%5cEGV_ADM_Y_FIN%5cSarlaft4_Back) ✅ 2024-02-28

- [ ] Después de superados los umbrales del criterio 4 solicitar configurar el quality gates del motor y sarlaftapi en el top para sonarqube. Una vez hecho el cambio de configuracion al correr el pipeline el resultado en sonar debe ser Passed

- [x] Actualizar las url de los pipelines y sonar en confluence. ✅ 2024-02-28