###### Tecnologías:

- Phyton
- Fastapi[all]~=0.111.0
- psycopg2-binary  
- SQLAlchemy~=2.0.31
- PostgreSQL 
###### Dogmas base estrictos a seguir:

- El domain solo se puede conocer así mismo, application puede conocerse así mismo y conocer a domain. e infraestructura puede conocerce a sí mismo, a domain y application. Osea, en domain no deben haber imports ni de infra ni de application, en aplication solo deben ir imports de domain, e infraestructura puede tener import de todo
- POO pura similar a la de Java
- Convención camelCase
- 0 Código fuera del scope de la clase
- Tipado fuerte para métodos, atributos, constantes y variables
- Asignación de `__` para métodos y atributos que deben encapsularse de manera privada por su naturaleza. Ejemplo: `__hola`
- Asignación de `@staticmethod` para métodos que deben ser estáticos por su naturaleza
- Siempre se declaran primero los atributos de clase en la parte superior con `__` similar a Java. y se le asigna el tipo de dato Ejemplo: `__nombre: str`
- Para usar algo de una clase en otra, únicamente se puede usar importando la clase directamente. Ejemplo: `from src.domain.model.Persona import Persona`. No se permite importar métodos o atributos directamente.
- Para atributos  que por su naturaleza deban ser constantes se usa SCREAMING_SNAKE_CASE y estos atributos constantes no se ponen en ninguna parte del constructor
- No está permitido asignar métodos como atributos en el constructor. Ejemplo: `self.__setupRoutes()`. Solo se pueden poner métodos como el valor de un atributo, más no un atributo en el constructor así porque si. Ejemplo: `self.__id = self.__generateId()`, esto es correcto, `self.metodo()` esto es incororecto. 
- No deben haber if anidados, se usa guard clauses u otra estrategia que veas correcta. pero que no implique anidar if
- No se permite usas @classmethod
- Se tipa fuertemente con `typing`
- Aqui te dejo un ejemplo de una clase generica que aplica estos dogmas:

```
import random  
  
  
class Persona:  
    # Constant  
    __GREETING = "Hola cómo estas?!"  
  a
    # Class attributes  
    __id = int  
    __name: str  
    __lastname: str  
    __age: int  
  
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


