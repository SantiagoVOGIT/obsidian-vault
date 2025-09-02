---
aliases:
  - Protocol Data Units
tags:
  - redes
---
###### Concepto:

Encapsulación/Desencapsulación 

| Capa (TCP/IP) | Nombre de la capa                             | PDU                                | Composición                                                                                       | Tamaño típico                            |
| ------------- | --------------------------------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| 4 (superior)  | Aplicación (Application)                      | **Data / message**                 | **Application data**                                                                              | Variable (0 - 65,535B)                   |
| 3             | Transporte (Host-to-Host)                     | **TCP segment** / **UDP datagram** | **Transport header** (**TCP header** / **UDP header**) + **Application data**                     | App data + 20-60B (TCP) / + 8B (UDP)     |
| 2             | Internet (Network)                            | **IP datagram** / **IP packet**    | **IP header** + **Transport segment** (**TCP segment** / **UDP datagram**) + **Application data** | Segment + 20-60B (IPv4) / + 40B (IPv6)   |
| 1             | Enlace / Acceso a red (Link / Network Access) | **Frame (trama)**                  | **Link-layer header** + **Payload** (**IP packet**) + **Link-layer trailer** _(si aplica)_        | Packet + 14-18B (Ethernet) + 0-4B (FCS)  |
| 0 (implícita) | Física (Physical)                             | **Bits / Symbols**                 | **Physical signal** (eléctrica/óptica/inalámbrica — representación a nivel de bit/símbolo)        | Frame × 8 bits + preámbulo/delimitadores |


![[Pasted image 20250815111802.png]]

###### Anotaciones:

> 

######  Recursos:

- []()