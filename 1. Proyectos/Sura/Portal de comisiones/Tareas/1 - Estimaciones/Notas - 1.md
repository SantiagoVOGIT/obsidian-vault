---
tags:
  - Proyectos
---
Dudas para los POs:

504915-[PORTAL DE COMISIONES] Filtro página inicial en el portal de comisiones:
- De donde sale número radicado
- Qué vistas o páginas son las que se requieren modificar

**Tareas:**
- Eliminar todos los filtros del encabezado de la vista general de la tabla
- Agregar la columna con el campo "Número de radicado" en la vista general de la tabla
- En la vista general de la tabla, las columnas deben de quedar en el siguiente orden: "Número de radicado", "Estado", "Código asesor", "Ramo", "Póliza", "Recibo", "Descripción", "Asignado a", "Fecha de reclamo",  "Clasificación", "Fecha de legalización",
- Eliminar el filtro de "Clasificación".
- En el modal se debe de permitir combinar dos o más filtros, y no debe ser necesario rellenar todos los filtros para poder continuar.
- Los campos "Número de radicado", "Código asesor", "Ramo", y "Póliza" deben permitir el filtrado mediante búsqueda sobre la lista de opciones, y que al seleccionar una opción se autocomplete en el input.
- El filtro de "Estado" se debe mantener como una lista desplegable con las siguientes opciones: "Abierto", "En trámite", "Cerrado", "Sin estado".

**Tareas nuevas:** 
- Agregar la columna con el campo "Número de radicado" en la vista general de la tabla
- Eliminar el botón "Filtrar" y su modal
- Eliminar el filtro de "Clasificación"
- Conservar el botón "Exportar" y su funcionalidad, este puede situarse en donde estaba antiguamente el botón "Filtrar"
- En la vista general de la tabla, las columnas deben de quedar en el siguiente orden: "Número de radicado", "Estado", "Código asesor", "Ramo", "Póliza", "Recibo", "Descripción", "Asignado a",  "Clasificación", "Fecha de reclamo", "Fecha de legalización",
- Se recomienda eliminar la columna de fecha de legalización si es posible, de lo contrario dejarla
- En el encabezado deben de quedar los filtros para las siguientes columnas: "Número de radicado", "Estado", "Código asesor", "Ramo", "Póliza", "Recibo", y por lapso de fechas, este último debe de quedar al lado del botón exportar.
- Los filtros "Código asesor", "Ramo", "Póliza" pasan de ser una lista desplegable a ser un input con una lista filtrable mediante búsqueda personalizada. Además debe de autocompletar el input al seleccionar una opción de la lista. Así mismo, en el momento de seleccionar una opción y autocompletarse en el input se debe aplicar el filtro para los reclamos de la vista general de la tabla.
- Los filtros "Número de radicado", y "Recibo" pasan de ser una lista desplegable a ser un input pero sin lista filtrable, estos deben filtrar mediante búsqueda personalizada directamente la lista de reclamos de la vista general de la tabla en tiempo real.
- El filtro de "Estado" se debe mantener como una lista desplegable con las siguientes opciones: "Abierto", "En trámite", "Cerrado", "Otros".
- Al filtrar por el valor "Otros" deben aparecer todos los reclamos con "Estado" diferente a "Abierto", "En trámite", "Cerrado" en la vista general de la tabla.
- Se debe de permitir combinar dos o más filtros a la vez y no debe ser necesario diligenciar todos los filtros para realizar el filtrado. 



505327-[PORTAL DE COMISIONES] Ajuste en la Página inicial del Portal de comisiones

- Del más antiguo a más reciente según que fecha?
- Qué vistas o páginas son las que se requieren modificar
- Esta modificación es la misma pagina que la anterior?

**Tareas:**

1.  Que al abrir la vista general de la tabla de manera predeterminada aparezcan todos los resultados sin necesidad de haber usado algún filtro
2. De manera predeterminada y constante se deben filtrar los resultados de la siguiente manera: .
	- Según su valor de "Estado": primero "Abierto", luego "En trámite", luego en "Cerrado" y por último "Otros".  
	- Según su valor de "Fecha de reclamo": en orden ascendente, partiendo desde la fecha más antigua a la más reciente. Lo que quiere decir, que las fechas que primero se visualicen sean las más antiguas. 
3. Colocar los anteriores encabezados alineados con la información

Posible historia:
- Corregir la responsividad del nav


543295-[PORTAL DE COMISIONES] Fecha corte Corredores nómina semanal Portal de Comisiones

- Hay más corredores aparte de esos que usted me menciono?, el cambio solo lo quiere para esos corredores?, o es para todos o los que se proporcionan son de ejemplo?
- Qué vistas o páginas son las que se requieren modificar

Tareas extra:
- Reunión con Lu sobre la propuesta
- Validación con Isa respecto al botón exportar
- Validación respecto a la historia de usuario de las fecha de corte por parte de Isa 
- Reunión con Sebas para validar los cambios que el tiene
- Reunión con Vivi y Sebas para aclarar la estimación propuesta


1. _Tener un único botón para filtrar la información, el que actualmente existe, en la parte superior derecha._
2. _Eliminar todos los filtros que aparecen en la hoja principal (los encabezados de la información deben ser fijos, no deben tener lista desplegable)_
3. _En el único botón (numero 1), mantener los filtros actuales: por fechas, ramo, póliza y código asesor._
4. _Agregar en el botón, el campo de número de radicado, estado (abierto, en trámite, cerrado, sin estado)_
5. _Que se pueda filtrar en dicho botón por cualquiera de los anteriores campos o combinar dos o más filtros. Es decir, no todos los campos se debe diligenciar para hacer el filtro, si alguno no se diligencia, quiere decir que aplica para todo en lo que corresponde a dicho campo._

