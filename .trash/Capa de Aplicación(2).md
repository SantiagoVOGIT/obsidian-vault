---
aliases: 
tags:
  - redes
---
###### Concepto:

Los protocolos de aplicación permiten la interoperabilidad entre sistemas y aplicaci
transmisión eficiente, confiable y segura de datos a través de Internet.
Son fundamentales para habilitar una amplia gama de servicios y aplicaciones en línea.

- [[HTTP]] / [[HTTPS]]
- [[FTP]]
- [[WS]]/[[WSS]]

| Categoría                     | Protocolo                | Transporte | Puerto                     | Esquema URI       | Notas                                                   |
| ----------------------------- | ------------------------ | ---------- | -------------------------- | ----------------- | ------------------------------------------------------- |
| **Web y REST**                | HTTP/1.1                 | TCP        | 80                         | http://           | Protocolo de capa de aplicación, sin estado             |
|                               | HTTPS                    | TCP        | 443                        | https://          | HTTP sobre SSL/TLS, encripta todo el contenido          |
|                               | HTTP/2                   | TCP        | 80/443                     | http://, https:// | Optimizado con compresión y multiplexado                |
|                               | HTTP/3 (QUIC)            | UDP        | 80/443                     | http://, https:// | Basado en QUIC, TLS integrado por defecto               |
| **Web en tiempo real**        | WebSocket (WS)           | TCP        | 80                         | ws://             | Comunicación full-dúplex, no encriptado                 |
|                               | WebSocket Secure (WSS)   | TCP        | 443                        | wss://            | Encriptado vía SSL/TLS                                  |
|                               | Server-Sent Events (SSE) | TCP        | 80/443                     | —                 | Usa HTTP(S), unidireccional servidor→cliente            |
| **Transferencia de archivos** | FTP                      | TCP        | 21 (control), 20 (datos)   | ftp://            | **OBSOLETO**: Inseguro, sin encriptación                |
|                               | FTPS (implicit TLS)      | TCP        | 990 (control), 989 (datos) | ftps://           | FTP con SSL/TLS, problemas con firewalls                |
|                               | SFTP                     | TCP        | 22                         | sftp://           | Basado en SSH, reemplaza FTP/FTPS                       |
|                               | SCP                      | TCP        | 22                         | scp://            | Basado en SSH, OpenSSH recomienda usar SFTP             |
| **Correo electrónico**        | SMTP                     | TCP        | 25                         | mailto:           | Transmisión entre servidores, bloqueado por ISPs        |
|                               | Submission (SMTP+AUTH)   | TCP        | 587                        | mailto:           | Puerto recomendado con STARTTLS                         |
|                               | SMTPS                    | TCP        | 465                        | smtps://          | SMTP con TLS implícito                                  |
|                               | POP3                     | TCP        | 110                        | pop3://           | Protocolo más antiguo, sin encriptación por defecto     |
|                               | POP3S                    | TCP        | 995                        | pop3s://          | POP3 sobre SSL/TLS                                      |
|                               | IMAP                     | TCP        | 143                        | imap://           | Gestión completa de buzón, sin encriptación por defecto |
|                               | IMAPS                    | TCP        | 993                        | imaps://          | IMAP sobre SSL/TLS                                      |
| **RPC / APIs**                | SOAP                     | TCP        | 80/443                     | —                 | Usa HTTP(S) como transporte                             |
|                               | JSON-RPC                 | TCP        | 80/443                     | —                 | Agnóstico de transporte, comúnmente HTTP(S)             |
|                               | XML-RPC                  | TCP        | 80/443                     | —                 | Usa HTTP(S) como transporte                             |
|                               | gRPC                     | TCP        | 80/443                     | —                 | Usa HTTP/2 como transporte                              |
|                               | GraphQL                  | TCP        | 80/443                     | —                 | Opera sobre HTTP, endpoint único                        |
|                               | OData                    | TCP        | 80/443                     | —                 | Protocolo RESTful sobre HTTP(S)                         |
|                               | OpenAPI/REST             | TCP        | 80/443                     | —                 | APIs REST sobre HTTP(S)                                 |
| **Mensajería / Colas**        | AMQP                     | TCP        | 5672                       | amqp://           | Protocolo estándar para message brokering               |
|                               | AMQPS (TLS)              | TCP        | 5671                       | amqps://          | AMQP seguro con TLS/SSL                                 |
|                               | MQTT                     | TCP        | 1883                       | mqtt://           | Protocolo ligero para dispositivos IoT                  |
|                               | MQTTS (TLS)              | TCP        | 8883                       | mqtts://          | MQTT seguro con TLS                                     |
|                               | STOMP                    | TCP        | 61613                      | stomp://          | Protocolo simple basado en texto                        |
|                               | Apache Kafka             | TCP        | 9092                       | —                 | Plataforma de streaming distribuida                     |
| **IoT**                       | CoAP                     | UDP        | 5683                       | coap://           | Para redes restringidas, con retransmisión              |
|                               | CoAPS (DTLS)             | UDP        | 5684                       | coaps://          | CoAP seguro con DTLS                                    |
|                               | LwM2M                    | UDP        | 5683/5684                  | —                 | Gestión de dispositivos basado en CoAP                  |
| **Directorios**               | LDAP                     | TCP        | 389                        | ldap://           | Servicios de directorio, conexión no protegida          |
|                               | LDAPS                    | TCP        | 636                        | ldaps://          | LDAP con TLS mandatorio, TLS 1.2+ requerido             |
| **Seguridad**                 | OAuth 2.0 / OIDC         | TCP        | 80/443                     | —                 | Protocolos de seguridad sobre HTTP(S)                   |
|                               | SAML                     | TCP        | 80/443                     | —                 | Framework XML para identidad federada                   |
| **Acceso Remoto**             | SSH                      | TCP        | 22                         | ssh://            | Reemplaza Telnet, comunicación criptográfica            |
|                               | RDP                      | TCP/UDP    | 3389                       | rdp://            | Protocolo propietario de Microsoft                      |
|                               | VNC                      | TCP        | 5900+N                     | vnc://            | Control remoto de escritorio gráfico                    |
| **Descubrimiento**            | DNS                      | UDP/TCP    | 53                         | —                 | UDP por defecto, TCP para transferencias                |
|                               | DNS-over-HTTPS (DoH)     | TCP        | 443                        | —                 | DNS encriptado sobre HTTPS                              |
|                               | DNS-over-TLS (DoT)       | TCP        | 853                        | —                 | DNS encriptado sobre TLS dedicado                       |
|                               | mDNS / DNS-SD            | UDP        | 5353                       | —                 | DNS multicast para redes locales                        |
| **Gestión**                   | SNMP                     | UDP        | 161                        | snmp://           | Gestión de dispositivos, v3 requerido para seguridad    |
|                               | NETCONF                  | TCP        | 830 (o 22)                 | —                 | Configuración de red sobre SSH                          |
|                               | RESTCONF                 | TCP        | 443 (80)                   | —                 | Configuración RESTful sobre HTTP(S)                     |
|                               | Syslog                   | UDP/TCP    | 514 (UDP), 601/1470 (TCP)  | syslog://         | Logging centralizado                                    |
| **Monitoreo**                 | Prometheus HTTP API      | TCP        | 9090                       | http://           | API de monitoreo sobre HTTP                             |
| **Sincronización**            | NTP                      | UDP        | 123                        | ntp://            | Sincronización de relojes                               |
|                               | SNTP                     | UDP        | 123                        | —                 | Subconjunto de NTP, versión simplificada                |

###### Índice:

- 

###### Anotaciones:

> 

######  Recursos:

- []()