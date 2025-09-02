Hardware → Driver Genérico Windows → OS APIs → Aplicaciones
         Driver Específico Fabricante → OS APIs → Aplicaciones
								  OS APIs → Librerías de lenguajes → Aplicaciones

Arquitectura web: Hardware → Drivers → OS APIs → Navegador → Web APIs → Aplicación Web


```mermaid 


graph TD

    App[Anillo 3: Aplicación / Librerías de lenguaje] -- syscall/API --> Kernel[Anillo 0: Núcleo del SO]

    Kernel --> DriverGen[Anillo 0: Driver genérico Windows]

    DriverGen --> DriverHW[Anillo 0: Driver específico de fabricante]

    DriverHW --> HW[Hardware]
```
