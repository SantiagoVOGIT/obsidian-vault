---
aliases:
  - mascara de red
  - mascara de subred
  - subnet mask
tags:
  - redes
---
###### Concepto:

Se define **máscara de red o subred** como un patrón binario que determina qué bits de una dirección [[IPv4]] o [[IPv6|IPv6]] pertenecen a la porción de red y cuáles a la porción de [[host]]. Se representa habitualmente como notación decimal punteada en IPv4 (por ejemplo `255.255.255.0`) o como prefijo [[CIDR|CIDR]]  (por ejemplo `/24`). En IPv6 se utiliza la longitud del prefijo (`/64`, `/56`, etc.) en lugar de una máscara decimal.

**Notación y formas de representación**

- **CIDR (prefijo):** `/n` donde `n` es el número de bits de red en la máscara (ej.: `/24`).
- **Notación decimal punteada (IPv4):** cuatro octetos separados por puntos (ej.: `255.255.255.0`).
- **Notación binaria:** 32 bits para IPv4 (unos contiguos a la izquierda, ceros a la derecha).
- **Wildcard (Cisco/ACL):** máscara invertida usada en ciertas configuraciones (`0.0.0.255` corresponde a `255.255.255.0`).

**Función y comportamiento**

- La porción de red es aquella que es común a todos los host de una red, y la porción de host es la que cambia e identifica a cada máquina
- El host usa la máscara localmente para decidir si una dirección destino está en la misma subred.
    - Si la dirección destino pertenece a la misma subred, el host intenta entrega directa (ARP/ND/).
    - Si no pertenece, el host envía el paquete al [[Gateway|gateway]] (ej.: router) predeterminado o a la siguiente entrada en la tabla de enrutamiento.
- La máscara no forma parte del IP header; por tanto, no se envía en cada paquete.
- Siempre existen 2 direcciones reservadas, una para la dirección de red base, y otra para la de [[Broadcast|broadcast]].

 **Ejemplo práctico**

IP: `192.168.1.130/25`

- Máscara `/25` = `255.255.255.128` = binario `11111111.11111111.11111111.10000000`.
- Dirección de red: `192.168.1.128`.
- Broadcast: `192.168.1.255`.
- Rango utilizable: `192.168.1.129` → `192.168.1.254`.

#####  Mascaras más utilizadas: 

| Prefijo (bits de red) | Máscara (decimal) | Bits host | Total direcciones | Hosts útiles (por defecto) | Wildcard (máscara invertida) | Notas                                            |
| --------------------: | :---------------: | :-------: | ----------------: | :------------------------: | :--------------------------: | :----------------------------------------------- |
|                    /0 |      0.0.0.0      |    32     |        4294967296 |         4294967294         |       255.255.255.255        | Red global (toda la IPv4)                        |
|                    /8 |     255.0.0.0     |    24     |          16777216 |          16777214          |        0.255.255.255         | Clase A original                                 |
|                   /12 |    255.240.0.0    |    20     |           1048576 |          1048574           |         0.15.255.255         |                                                  |
|                   /16 |    255.255.0.0    |    16     |             65536 |           65534            |         0.0.255.255          | Clase B original                                 |
|                   /20 |   255.255.240.0   |    12     |              4096 |            4094            |          0.0.15.255          |                                                  |
|                   /22 |   255.255.252.0   |    10     |              1024 |            1022            |          0.0.3.255           |                                                  |
|                   /23 |   255.255.254.0   |     9     |               512 |            510             |          0.0.1.255           |                                                  |
|                   /24 |   255.255.255.0   |     8     |               256 |            254             |          0.0.0.255           | Clase C original                                 |
|                   /25 |  255.255.255.128  |     7     |               128 |            126             |          0.0.0.127           |                                                  |
|                   /26 |  255.255.255.192  |     6     |                64 |             62             |           0.0.0.63           |                                                  |
|                   /27 |  255.255.255.224  |     5     |                32 |             30             |           0.0.0.31           |                                                  |
|                   /28 |  255.255.255.240  |     4     |                16 |             14             |           0.0.0.15           |                                                  |
|                   /29 |  255.255.255.248  |     3     |                 8 |             6              |           0.0.0.7            | Subred típica para enlaces pequeños              |
|                   /30 |  255.255.255.252  |     2     |                 4 |             2              |           0.0.0.3            | Muy usada en enlaces punto-a-punto tradicionales |
|                   /31 |  255.255.255.254  |     1     |                 2 |    2 (RFC3021 para P2P)    |           0.0.0.1            | Permitido en enlaces punto-a-punto.              |
|                   /32 |  255.255.255.255  |     0     |                 1 |             1              |           0.0.0.0            | Host route (una sola IP)                         |

###### Anotaciones:

> [!note]
> La máscara no constituye una dirección IP; actúa como un filtro (enmascaramiento) aplicado sobre la dirección IP para extraer la parte de red.

######  Recursos:

- []()