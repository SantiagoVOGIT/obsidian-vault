###### Repositorio de frontend: 

###### Tecnologías:

- Typescript: ^5.2.2
- React: ^18.3.1
	- "axios": "^1.6.0",
	- "react-router-dom": "^6.2.1"
- Vite ^5.3.1
- Bootstrap: v5.3.

###### Dogmas base estrictos a seguir: 
- El domain solo se puede conocer así mismo, application puede conocerse así mismo y conocer a domain. e infraestructura puede conocerce a sí mismo, a domain y application. Osea, en domain no deben haber imports ni de infra ni de application, en aplication solo deben ir imports de domain, e infraestructura puede tener import de todo
- POO similar a la de java
- Convención camelCase
- 0 Código fuera del scope de la clase
- Tipado fuerte para métodos, atributos, constantes y variables
- En el constructor no deben haber construcciones internas de funciones. se limita a llamarlas. Por ejemplo. this.metodoInterno(); eso es erroneo, .el constructor solo debe de tener atributos y debe verse así. Ejemplo: this.atributo = metodo() (en dado caso que se necesite una función como el valor de un atributo del constructor)
- Asignación de `private`, `protected` o `public` para métodos y atributos que por su naturaleza deben encapsularse o no encapsularse
- Asignación de `static` para métodos u atributos que deben ser estáticos por su naturaleza y su contexto
- Siempre se declaran primero los atributos de clase en la parte superior asignándosele únicamente su tipo de dato y su modificador de acceso, similar a java
- Se usa `export class (nombre clase)` para exportar clases
- Para atributos  que por su naturaleza deban ser constantes se usa SCREAMING_SNAKE_CASE y estos atributos constantes no se ponen en ninguna parte del constructor, únicamente en la parte superior, y deben llevar `readonly`
- No deben haber if anidados, se usa guard clauses u otra estrategia que veas correcta. pero que no implique anidar if

-  Aqui te dejo un ejemplo de una clase generica que aplica estos dogmas:

```
export class Persona {  
  
    private static readonly SALUDO_CONSTANTE: string = "Hola";  
  
    private id: number;  
    private name: string;  
    private lastname: string;  
    private age: number;  
  
    constructor(name: string, lastname: string, age: number) {  
        this.id = this.generateId();  
        this.name = name;  
        this.lastname = lastname;  
        this.age = this.setAge(age);  
    }  
  
    public getId(): number {  
        return this.id;  
    }  
  
    public getName(): string {  
        return this.name;  
    }  
  
    public getLastname(): string {  
        return this.lastname;  
    }  
  
    public getAge(): number {  
        return this.age;  
    }  
  
    public setName(name: string): void {  
        this.name = name;  
    }  
  
    public setLastname(lastname: string): void {  
        this.lastname = lastname;  
    }  
  
   private isValidAge(age: number): void {  
       if (age < 0) {  
           throw new Error("Age must be greater than 0");  
       }  
   }  
  
    public setAge(age: number): number {  
        this.isValidAge(age)  
        return this.age = age;  
    }  
  
    public printData(): string {  
        return `Id: ${this.id}, Name: ${this.name}, Lastname: ${this.lastname}, Age: ${this.age}`;  
    }  
  
    private generateId(): number {  
        return Math.floor(Math.random() * 1000);  
    }  
  
    public static saludar(): string {  
        return this.SALUDO_CONSTANTE;  
    }  
  
}

```
reply in spanish