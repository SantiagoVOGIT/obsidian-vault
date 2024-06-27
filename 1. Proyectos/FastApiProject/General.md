###### Explicación de carpetas claves:

- Infraestructura:
	- input-adapters: aquí van aquellos elementos que adaptan el contenido que se recibe en el exterior para que nuestra aplicación lo entienda, por general aquí van los controllers
	- output-adapters: aquí van aquellos elementos que adaptan el contenido que se envía de nuestra aplicación para que el mundo exterior lo pueda entender, por lo general aquí van las implementaciones de las interfaces de los repositorios.
	
- Aplicación: 
	- input-ports:


## Contexto de mi aplicación generales:

- Despliegue: Dockerizado y desplegado en Vercel
- Propósito: Es una API que será consumida por un frontend en React que está en otro repositorio y también desplegado en Vercel. Básicamente, es una SPA (Single Page Application).