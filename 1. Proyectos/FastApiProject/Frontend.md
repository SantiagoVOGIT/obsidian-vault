###### Repositorio de frontend: 

###### Tecnologías:

- Typescript: ^5.2.2
- React: ^18.3.1
	- "axios": "^1.6.0",
	- "react-router-dom": "^6.2.1"
- Vite ^5.3.1
- Bootstrap: v5.3.

###### Dogmas base estrictos a seguir: 

- POO similar a la de java
- 0 Código fuera del scope de la clase
- Tipado fuerte para métodos, atributos, constantes y variables
- Asignación de `private`, `protected` o `public` para métodos y atributos que por su naturaleza deben encapsularse o no encapsularse
- Asignación de `static` para métodos u atributos que deben ser estáticos por su naturaleza
- Siempre se declaran primero los atributos de clase en la parte superior asignándosele únicamente su tipo de dato y su modificador de acceso, similar a java
- Se usa `export class (nombre clase)` para exportar clases
- Para atributos constantes se usa SCREAMING_SNAKE_CASE y estos atributos constantes no se ponen en ninguna parte del constructor, y deben llevar `readonly`
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