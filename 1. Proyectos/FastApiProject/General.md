Dogmas

Explicación de estructuración de carpetas:
- common: en estas carpetas van aquellos elementos que son ajenos a la arquitectura subyacente, clases enums, validaciones genericas (expresiones regulares) etc, pero dichos elementos pese a ser genericos se limitan a la capa hexagonal en la que se encuentren.
- 

1. Infraestructura:
    - Aquí es donde se implementan los repositorios concretos.
    - Contiene las implementaciones específicas de la tecnología para acceder a bases de datos, servicios externos, etc.
2. Dominio:
    - Aquí se definen las interfaces (puertos) de los repositorios.
    - Estas interfaces son abstracciones que describen qué operaciones pueden realizar los repositorios, pero no cómo las realizan.
3. Aplicación:
    - Utiliza las interfaces de repositorio definidas en el dominio.
    - No contiene implementaciones de repositorios.

1. Definir las interfaces de los repositorios en la capa de dominio.
2. Implementar estas interfaces en la capa de infraestructura.
3. Usar estas implementaciones a través de las interfaces en la capa de aplicación.
4. Mantener separa toda logica de dominio, de toda logica de implementación de detalles a nivel de tecnologías especificas, mantener el dominio descontaminado. (el dominio no tiene por que tener importaciones de librerias de terceros, solo nuestros, en infraestructura si puede haberlos.)
no osea, es que es primera vez que estoy haciendo un proyecto coin diferentes ambientes entonces no he entendi muy bien como funciona, mi idea es que, yo estoy usando vercel para desplegar mi aplicación, y quiero tener los tipicos ambientes que se usan production etc, y tengo mis repos en github, entonces quiero hacerlo de la manera que se adecua al estandar y la manera correcta y moderna de hacer esto con las herramientas que te nombre. mi teoria era que hubiesen 3 ramas tanto en el repo del forntend, como del backend, y que en cada una ya estuvieran la url base definida correspondiente a la rama de ambiente a la que apunta, no sé si este correcto esa teoria que tengo


## Contexto de mi aplicación generales:

- Despliegue: Dockerizado y desplegado en Vercel
- Propósito: Es una API que será consumida por un frontend en React que está en otro repositorio y también desplegado en Vercel. Básicamente, es una SPA (Single Page Application).