## 1. Proceso de la Evaluación (Assessment)

- El concepto central de Sarlaft 4.0 es la "Evaluación" (Assessment).
- La evaluación permite validar si los clientes (tomador, asegurado, beneficiario, afiliado) cumplen con las validaciones de la Superintendencia Financiera para poder adquirir una póliza con Sura.
- Pasos generales del proceso de evaluación:
    1. El aplicativo cliente envía la información básica de las figuras involucradas (tomador, asegurado, etc.) y del negocio/póliza.
    2. Sarlaft 4.0 recibe los datos, crea la evaluación, determina el nivel de riesgo y establece el estado de la evaluación como FINALIZADO, RECHAZADO o PENDIENTE.
    3. Si el estado es FINALIZADO, el negocio puede ser expedido. Si es RECHAZADO, no se permite la expedición. Si es PENDIENTE, se debe completar un formulario de Sarlaft 4.0.
    4. Sarlaft 4.0 verifica que se completaron todos los requisitos y determina el estado final de la evaluación.
    5. Sarlaft 4.0 envía una notificación al aplicativo cliente con el estado final de la evaluación.

## 2. Entradas a la Evaluación (Assessment)

Las principales formas de crear una evaluación en Sarlaft 4.0 son:

- Servicio REST (assessment): Recibe la información de tomador, figuras y datos del negocio/póliza. Permite crear evaluaciones de hasta 10 figuras.
- Servicio REST masivo: Recibe la misma información que el servicio REST, pero con un límite de 100 pólizas.
- Mensajería RabbitMQ asíncrona: Permite recibir solicitudes de creación de evaluación con la misma información que los servicios REST.
- Sarlaft Manual: Opción de formulario web para que un asesor o auxiliar cree una evaluación directamente.

## 3. Validaciones (Assessment)

Las validaciones realizadas en el proceso de evaluación de Sarlaft tienen las siguientes características:

- Pueden ser síncronas o asíncronas.
- Pueden bloquear o no la finalización de un Sarlaft.
- Dejan evidencia de las validaciones realizadas.
- Se heredan de Sarlafts anteriores si la persona tiene uno vigente.

Tipos de validaciones:

- Validación PEPS: Identifica si el cliente es una Persona Políticamente Expuesta.
- Validación GAFI: Identifica si el país de nacimiento del cliente está en la lista GAFI.
- Validación RRCC: Identifica si el cliente está marcado como Riesgo Consultable.
- Validación Registraduría: Valida la identidad del cliente con la Registraduría Nacional.
- Validación XPERIAN: Valida la identidad del cliente a través de Experian o CIFIN.

Los posibles estados de las validaciones son: EXITOSO, FALLIDO, PENDIENTE, CANCELADA y FALLA_TECNICA.

## 4. Comunicación con el motor (assessment)

- Durante el proceso de evaluación, se comunica con el motor de Sarlaft 4.0 en 3 ocasiones:
    1. Determinación del nivel de riesgo
    2. Identificación de las validaciones requeridas
    3. Determinación del tipo de formulario y requisitos

## 5. Determinar si requiere diligenciar Sarlaft

- Se verifica si el cliente ya tiene un Sarlaft vigente para el mismo tipo de riesgo o superior.
- Si es así, se clonan las evidencias del Sarlaft existente y se marca como FINALIZADO.

## 6. Determinar estado de la evaluación

- La evaluación se considera FINALIZADA cuando todos los Sarlafts asociados están en estado FINALIZADO o CANCELADO.
- Un Sarlaft se considera FINALIZADO cuando todas sus evidencias están en estado EXITOSO o FALLA_TÉCNICA, el formulario está completo y los requisitos están ADJUNTADOS o FINALIZADOS.

## 7. Webhook (Assessment)

- Mecanismo de notificación al aplicativo cliente sobre el resultado de la evaluación.
- Puede ser a través de QUEUE o REST, según la configuración del aplicativo.
- Notifica cuando la evaluación está FINALIZADA, RECHAZADA, PENDIENTE_ACCIÓN_MANUAL o FINALIZADA_EXCEPCIÓN.

## 9. Consulta información de Cliente (getClient)

- Se consulta información del cliente en fuentes internas (Sarlaft y modelo de clientes de Sura) y externas (Experian, Informacolombia).
- Esto permite pre-diligenciar el formulario de Sarlaft.

## 10. Validación y Habilitación Cliente PEPs

- Se valida si el cliente (tomador o figuras) se considera una Persona Expuesta Políticamente (PEPs).
- Si es PEPs y no tiene una solicitud de habilitación vigente, el Sarlaft queda en estado PENDIENTE.
- El director/gerente de la oficina debe crear una solicitud de habilitación PEPs para levantar el control.

## 11. Requisitos de Sarlaft

- Los requisitos son documentos que el cliente debe adjuntar en su formulario de Sarlaft.
- Se determinan según el nivel de riesgo y el tipo de persona (natural o jurídica).
- El proceso incluye la creación, adjunción y finalización de los requisitos.

## 12. Crear Evaluación por Formulario

- Existe la opción de crear una evaluación de Sarlaft 4.0 directamente desde un formulario en el aplicativo.
- Se solicitan los datos básicos de la evaluación y se envía un correo al cliente con la URL para diligenciar el formulario.

## 13. Consultas Modelo RedComercial

- El microservicio de RedComercial expone 3 servicios web para consultar:
    1. Listado de oficinas donde está inscrito un asesor
    2. Información de contacto de las oficinas de un asesor
    3. Información de contacto de un asesor

## 14. Consultas Módulo de Clientes

- El módulo de clientes del aplicativo de Sarlaft 4.0 permite:
    1. Consultar el listado de evaluaciones generadas, filtrando por perfil de usuario
    2. Consultar los detalles de una evaluación específica
    3. Finalizar una evaluación sin cumplir todos los requisitos (perfil administrador)

## 15. Parametrización Entidades

- Existen entidades parametrizadas en la tabla `tsaf_entidad` que reciben un tratamiento especial en el proceso de categorización de riesgo.
- Tipos de entidades: FINASEPEN, REGIMEN, BOLSA, PASSTHROUGH
- Hay servicios web para consultar, cambiar estado y matricular nuevas entidades.

## 17. Desmarcar cliente PEPS

- Existe un módulo para desmarcar a un cliente como PEPS, utilizando el servicio web `/sarlaftbackweb/clientes/peps/desmarcar`.

## 18. Consultar Catálogos

- Existen catálogos internos (administrados por Sarlaft 4.0) y catálogos externos (administrados por el gobierno de accesos y clientes).
- Los catálogos internos se obtienen de tablas en la base de datos y se cargan en caché.
- Los catálogos externos se obtienen a través de un microintegrador que consume el servicio web externo `consultarParametrosTipoDescripcion` de ServiciosWebSIC, y se almacenan en caché.