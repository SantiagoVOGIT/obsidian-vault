---
aliases:
  - CIDR
  - Classless Inter-Domain Routing
tags:
  - redes
---
###### Concepto:

**CIDR** (Classless Inter-Domain Routing) define un método para asignar y enrutear direcciones [[IPv4|IPv4]]/[[IPv6|IPv6]] sin depender de las antiguas clases A/B/C. CIDR utiliza un sufijo de prefijo (`/n`) que indica cuántos bits de la dirección pertenecen a la porción de red; los bits restantes pertenecen a los [[host|hosts]]. CIDR permite agrupar (summarize) rutas y asignar bloques de tamaño flexible, optimizando el uso del espacio de direcciones y reduciendo el tamaño de las tablas de enrutamiento.

**Notación**

- Forma general: `dirección/prefijo` → ejemplo: `192.0.2.0/24`.
- `n` en `/n` es un entero entre `0` y `32` (IPv4) o entre `0` y `128` (IPv6) y representa el número de bits de red.

**Ventajas principales**

- Reduce el desperdicio de direcciones al permitir bloques ajustados a la necesidad real.
- Facilita el _route aggregation_ (resumen de rutas), disminuyendo entradas en tablas de enrutamiento.
- Elimina las restricciones fijas de las clases A/B/C, ofreciendo mayor flexibilidad administrativa.

**Impacto**

CIDR ha resultado fundamental para el crecimiento sostenible de Internet, extendiendo significativamente la vida útil del protocolo IPv4 y manteniéndose como componente esencial en el diseño de redes modernas.

###### Anotaciones:

> 

######  Recursos:

- []()