###### Dogmas base estrictos a seguir:

- Principios y sintaxis de POO estrictamente igual a la de java, o lo más similar posible.
- Convención camelCase
- 0 Código fuera del scope de la clase
- Tipado fuerte para métodos, atributos, constantes y variables, ósea tipado fuerte para todo
- Asignación de `__` para métodos y atributos que deben encapsularse de manera privada por su naturaleza. Ejemplo: `__hola`
- Asignación de `@staticmethod` para métodos que deben ser estáticos por su naturaleza
- Siempre se declaran primero los atributos de clase en la parte superior con `__` similar a Java. y se le asigna el tipo de dato y se inicializan con None en dado en caso que lo requiera, si no lo quiere no lo debes hacer,k Ejemplo: `__nombre: str = None`,  `__apellido: str`  
- Para usar algo de una clase en otra, únicamente se puede usar importando la clase directamente. Ejemplo: `from src.domain.model.Persona import Persona`. No se permite importar métodos o atributos directamente.
- Para atributos  que por su naturaleza deban ser constantes se usa SCREAMING_SNAKE_CASE y estos atributos constantes no se ponen en ninguna parte del constructor
- No está permitido asignar métodos o funciones como atributos directos en el constructor. Ejemplo: `self.__metodo()`. En dado caso que se necesite o sea necesario se puede asignar un método como valor de un atributo, ejemplo:  `self.__id = self.__generateId()`, de no ser necesario esto último no se debe hacer.
- No deben haber if anidados, se usa Guard clauses u otra estrategia que veas correcta para mantener un código legible, mantenible y escalable. pero que no implique anidamientos de bucles. if. etc.
- No se permite usar @classmethod
- Se tipa fuertemente con `typing` si es necesario
- Aquí te dejo un ejemplo de una clase genérica que aplica estos dogmas:

```
import random  
  
  
class Persona:  
    # Constant  
    __GREETING = "Hola cómo estas?!"  
  a
    # Class attributes  
    __id = int = None  
    __name: str = None  
    __lastname: str = None   
    __age: int = None   
  
    # Constructor  
    def __init__(self, name: str, lastname: str, age: int):  
        self.__id = self.__generateId()  
        self.__name = name  
        self.__lastname = lastname  
        self.__age = age  
  
    # Getter methods  
    def getId(self) -> float:  
        return self.__id  
  
    def getName(self) -> str:  
        return self.__name  
  
    def getLastname(self) -> str:  
        return self.__lastname  
  
    def getAge(self) -> int:  
        return self.__age  
  
    # Setter methods  
    def setName(self, name: str) -> None:  
        self.__name = name  
  
    def setLastname(self, lastname: str) -> None:  
        self.__lastname = lastname  
  
    def setAge(self, age: int) -> None:  
        self.__age = age  
  
    # Normal methods  
    def printData(self) -> None:  
        print(f"ID: {self.__id}")  
        print(f"Name: {self.__name}")  
        print(f"Lastname: {self.__lastname}")  
        print(f"Age: {self.__age}")  
  
    # Private methods  
    def __generateId(self) -> float:  
        return random.random()  
  
    #static methods  
    @staticmethod  
    def greet() -> str:  
        return Persona.__GREETING
```

Cuál sería la manera correcta de agregar tecnología JWT para este implementando Arquitectura hexagonal y DDD dentro del frontend, se alinea a buenas practicas de DDD y arquitectura hexagonal y codigo escalable, mantenible y testeable.

 ]]
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiJmNzE1MTZiYi0yNGU3LTQyOGUtOGRmNi03MTZhOGM4MGYzMDciLCJyb2xlIjoiQURNSU5JU1RSQURPUiIsImV4cCI6MTcyMzQ5MzA2M30.6rhLZc2LqKBB8KtrIYyfNgHFfRiBvPndCELq8XgAB6Y

Puntos clave
- app (todo lo necesario para arrancar la app)
	- main
		- com
			- company
				- project
					- MainApplication 
		- resources
			- application.properties
	- test
		- com
			- company
				- project	 
- src
	- bounded-context (depende de shared)
		- main
			- com
				- company
					- project
						- domain
							- clases java
						- infrastructure
							- clases java
						- application
							- clases java
		- test
	- shared (recursos comunes para bounded context)
		- main
			- com
				- company
					- project
						- domain
							- clases java
						- infrastructure
							- clases java
		- test

# Hexagonal Spring Skeleton  
Template for a Spring application with hexagonal architecture + DDD focused on REST API  
  
## Prerequisites  
- Java SE 17  
- Deployed PostgreSQL database  
  
### Installation with CLI:  
- Build the project using Gradle  
    - `./gradlew build`  
  
- Configure environment variables in `application.properties`  
    - `${DATASOURCE_URL}`  
    - `${DATASOURCE_USERNAME}`  
    - `${DATASOURCE_PASSWORD}`  
  
- Run the application:  
    - `./gradlew bootRun`

spring.datasource.url=jdbc:postgresql://aws-0-us-east-1.pooler.supabase.com:6543/postgres  
spring.datasource.username=postgres.inrkdquzxxkgourngwef  
spring.datasource.password=Valenciano2005.