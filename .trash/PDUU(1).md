---
aliases:
  - Protocol Data Units
tags:
  - redes
---
###### Concepto:

| Capa (TCP/IP) | Nombre de la capa                             | PDU                                | Composición                                                                                       |
| ------------- | --------------------------------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------- |
| 4 (superior)  | Aplicación (Application)                      | **Data / message**                 | **Application data**                                                                              |
| 3             | Transporte (Host-to-Host)                     | **TCP segment** / **UDP datagram** | **Transport header** (**TCP header** / **UDP header**) + **Application data**                     |
| 2             | Internet (Network)                            | **IP datagram** / **IP packet**    | **IP header** + **Transport segment** (**TCP segment** / **UDP datagram**) + **Application data** |
| 1             | Enlace / Acceso a red (Link / Network Access) | **Frame (trama)**                  | **Link-layer header** + **Payload** (**IP packet**) + **Link-layer trailer** *(si aplica)*        |
| 0 (implícita) | Física (Physical)                             | **Bits / Symbols**                 | **Physical signal** (eléctrica/óptica/inalámbrica — representación a nivel de bit/símbolo)        |


###### Anotaciones:

> 

######  Recursos:

- []()