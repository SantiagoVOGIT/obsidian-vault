---
aliases:
  - IPv4
tags:
---
###### Concepto:



estructura clasica de 4 grupos de bytes 000.000.000.000

|         Rango (CIDR) | Nombre / propósito                               | Descripción                                                                                                                                  |
| -------------------: | ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
|          `0.0.0.0/8` | Direcciones "esta red / host no especificado"    | Usado para referirse al host fuente en "esta" red (dirección no especificada / INADDR_ANY). No debe aparecer como destino en redes normales. |
|         `10.0.0.0/8` | Private-Use (RFC1918)                            | Espacio privado no enrutable en Internet pública; para redes internas.                                                                       |
|      `100.64.0.0/10` | Shared Address Space (CGN)                       | Espacio reservado para uso entre proveedor y cliente en escenarios de Carrier-Grade NAT (no globalmente enrutable).                          |
|        `127.0.0.0/8` | Loopback                                         | Bloque usado para loopback local al host (ej. `127.0.0.1`); nunca aparece en la red.                                                         |
|     `169.254.0.0/16` | Link-Local (APIPA)                               | Direcciones configuradas automáticamente cuando no hay DHCP; sólo válidas en el enlace local.                                                |
|      `172.16.0.0/12` | Private-Use (RFC1918)                            | Segundo bloque reservado para redes privadas (172.16.0.0–172.31.255.255).                                                                    |
|       `192.0.0.0/24` | IETF Protocol Assignments / IANA special-purpose | Bloque reservado para asignaciones relacionadas con protocolos IETF (IANA special-purpose registry).                                         |
|       `192.0.2.0/24` | TEST-NET-1 (documentación)                       | Bloque para ejemplos y documentación (no debe aparecer en Internet real).                                                                    |
|     `192.88.99.0/24` | (6to4 relay anycast) — **deprecado**             | Anteriormente usado para relays 6to4 anycast; marcado como deprecado por la IETF.                                                            |
|     `192.168.0.0/16` | Private-Use (RFC1918)                            | Bloque común en redes domésticas y de oficina (no enrutable públicamente).                                                                   |
|      `198.18.0.0/15` | Benchmarking / test                              | Reservado para pruebas/benchmarking de interconexión de redes (no debe usarse en producción).                                                |
|    `198.51.100.0/24` | TEST-NET-2 (documentación)                       | Bloque para ejemplos y documentación.                                                                                                        |
|     `203.0.113.0/24` | TEST-NET-3 (documentación)                       | Bloque para ejemplos y documentación.                                                                                                        |
|        `224.0.0.0/4` | Multicast (Class D)                              | Espacio reservado para multicast IPv4 (224.0.0.0–239.255.255.255); hay subregistros IANA para asignaciones conocidas.                        |
|        `240.0.0.0/4` | Reserved (historically "Class E")                | Reservado para uso futuro; no debe utilizarse en Internet pública.                                                                           |
| `255.255.255.255/32` | Limited broadcast                                | Dirección de broadcast limitada (no debe ser encaminada fuera del enlace local).                                                             |

Internet Classful

| Clase | Rango IPv4                      | Máscara por defecto |                                Nº redes (clásico) | Hosts por red (total) | Hosts por red (usables) | Propósito / nota                                                             |
| ----: | :------------------------------ | :-----------------: | ------------------------------------------------: | --------------------: | ----------------------: | ---------------------------------------------------------------------------- |
|     A | `0.0.0.0` – `127.255.255.255`   |        `/8`         | 128 (0–127) — típicamente 126 utilizables (1–126) |            16,777,216 |              16,777,214 | Grandes redes. (127/8 reservado para loopback; 0/8 tiene uso especial)       |
|     B | `128.0.0.0` – `191.255.255.255` |        `/16`        |                                            16,384 |                65,536 |                  65,534 | Redes medianas.                                                              |
|     C | `192.0.0.0` – `223.255.255.255` |        `/24`        |                                         2,097,152 |                   256 |                     254 | Redes pequeñas / subredes.                                                   |
|     D | `224.0.0.0` – `239.255.255.255` |  N/A (no máscara)   |                                               N/A |                   N/A |                     N/A | **Multicast** (no son redes host tradicionales).                             |
|     E | `240.0.0.0` – `255.255.255.255` |         N/A         |                                               N/A |                   N/A |                     N/A | **Reservado / experimental / futuro uso** (no para uso general en Internet). |

![[Pasted image 20250818102753.png]]

###### Anotaciones:

> 

######  Recursos:

- []()

[^1]: jeje

[^2]: h
