---
aliases: []
---
- [x] **1. Creación de pipelines:** ✅ 2024-02-28

- **Ruta:** Ruta indicada en Azure Pipelines.
- **Objetivo:** Crear pipelines para:
    - Feature de la rama master para sarlaft engine.
    - Release de enero de sarlaftapi.

- [x] **2. Ajustar pipelines para SonarQube:** ✅ 2024-02-28

- **Agregar las siguientes líneas:**
    ```
    preBuild:
    - with: sonarqube
      configure:
        serviceConnection: sc-az-solucionescorporativas-pdn_eefce279-9b08-4687-a872-762a8e311aed
    ```
- **Ubicación:** Agregar las líneas en la sección `continuousIntegration`.

- [x] **3. Actualizar nombre de repositorio:** ✅ 2024-02-28

- **Repositorio:** sarlaftengines.
- **Cambio:** Actualizar el nombre del repositorio a uno nuevo.

- [ ] **4. Subir cobertura de sarlaftapi:**

- **Objetivo:** Aumentar la cobertura al 95% como mínimo.
- **Acción:** Implementar las medidas necesarias para alcanzar la cobertura deseada.

- [ ] **5. Probar y crear PR para develop y master:**

- **Pruebas:** Realizar pruebas exhaustivas de las pipelines y la cobertura de sarlaftapi.
- **Pull requests:** Crear PRs para las ramas develop y master.