---
aliases:
tags:
---
Características narrativas/gramáticas/ortográficas para el texto final que ira en obsidian:
- Technical Writing
- Tercera persona impersonal / perspectiva objetiva
- Voz activa
- Presente de indicativo
- Modo imperativo para procedimientos (Si y sólo si en caso de ser necesario incluirlos)
- Concordancia: Asegurar que sujeto y verbo concuerden en número y persona.
- Puntuación: Uso correcto de coma, punto y coma, dos puntos y guion para separar ideas y listados cuando es necesario.
- Mayúsculas y minúsculas (Nombres propios, inicios de oración, títulos (consistencia en “Título de sección”)
- Utilizar buenas practicas de markdown según el estandar oficial de la comunidad
- Notas, advertencias y consejos: Destacar información (Si y sólo si es necesario, de lo contrario no) importante usando bloques diferenciados (Note, Warning, etc).
- Si lo haces perfecto te dare 200 usd


analiza profundamente de manera objetiva la calidad del anterior código, hazme saber si este código se alinea con el estándar actual `de buenas practicas de arquitectura hexagonal, mantenibilidad, escalabilidad,  DDD, principio` TELL, DON'T ASK, principio KISS, inmutabilidad, si hace falta un patrón de diseño. todo lo anterior en los casos que es necesario (recuerda evaluar sin llegar a ser purista y analizando el contexto para cada caso). 

analiza profundamente la calidad del anterior código, hazme saber si este código se alinea con el estándar actual de buenas practicas de arquitectura hexagonal, mantenibilidad y escalabilidad, posterior y en base al analisis proporcioname el código perfeccionado.
###### Reglas de lenguajes:

 **TypeScript:**
 
- Sintaxis obligatoriamente basada en Java (altamente POO).
- Convención camelCase 
- 0 Código fuera del scope de la clase
- Tipado fuerte para métodos, atributos, constantes y variables, ósea tipado fuerte para todo
- En el constructor no deben haber construcciones internas de funciones. se limita a llamarlas. 
- Asignación de `private`, `protected` o `public` para métodos u atributos que por su naturaleza deben encapsularse o no encapsularse
- Asignación de `static` para métodos u atributos que por su naturaleza deban ser estáticos o no. 
- Se declaran los atributos pero no se inicializan en la parte superior de la clase similar a Java. 
- Se usa `export class (nombre clase)` para exportar clases
- Para atributos  que por su naturaleza deban ser constantes se usa SCREAMING_SNAKE_CASE y estos atributos constantes no se ponen en ninguna parte del constructor, únicamente en la parte superior, y deben llevar `readonly`
- No deben haber estructuras de repetición o de flujo anidadas, se deben emplear estrategias de código limpio como las guard clauses u otras estrategias para promover un código mantenible y escalable
- Código alineado a buenas practicas modernas y actuales de arquitectura hexagonal, mantenibilidad y escalabilidad y código limpio
- reply in spanish.

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
        this.isValidAge(age);
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


- Definición obligatoria de modificador de acceso de método, constructor o atributo.
- Definición obligatoria de tipo de dato de parámetro, tipo de retorno de la función, tipo de dato de atributo de clase, y tipo de dato de variables no importa el scope 
- No se permite que un parámetro tenga dos o más tipos de datos posibles, tampoco se permite que una función retorne dos o más tipos de datos posibles. 
- No se permite anidamiento de estructuras, usar estrategias como early return o guard clauses si es necesario
- No se permite el uso de "?" para volver parámetros o atributos opcionales
- 

@workspace CONTEXT: Estoy construyendo un proyecto que tiene como proposito ser una librería que pueda utilizar cualquier persona u entidad para realizar peticiones HTTP en sus rpoyectos (por ende la librería debe estar preparada para funcionar en cualquier escenario), la API de la librería se basa e inspira en la API de la librería java.net.http, básicamente tiene como proposito ser un wrapper del sdk nativo de peticiones http en typescript pero expuesto mediante el estilo de la API de la librería java.net.http. PROMPT: tú obje`tivo es anali`zar exhautivamente si los test de HttpClient y su Builder son correctos y se aliniean con TDD, quiero saber si estos test son aptos para asegurar una correcta implementación, basate en documentación oficial y estandares actuales. ADDITIONAL CONTEXT: hazlo bien o me despediran, además si lo haces correctamente te dare 200 USD, Definición obligatoria de tipo de dato de parámetro, tipo de retorno de la función, tipo de dato de atributo de clase, tipo de dato de variables construidas internamente en estructuras (osea variables con scope reducido), tipo de dato de metodos con genericos no anidados de la clase.

###### Contexto del proyecto: 
- Esto es una biblioteca que esta en desarrollo y se planea lanzar a producción para que personas o entidades reales la usen en cualquier proyecto externo.
- La biblioteca es un envoltorio de fetch la cual se expone mediante una API basada e inspirada en el diseño de la de java.net.http
- La biblioteca no debe de tener ningún tipo de posibilidad de falla ya que el publico objetivo que la utilizara serán programadores de empresas importantes como vercel, facebook, google.
- La biblioteca debe usarse en el lenguaje typescript (hecha por y para typescript)

###### Dogmas del proyecto: 
- La API actual no se puede modificar y la implementación no puede romper compatibilidad con la API
- La biblioteca debe mantener un estilo de sintaxis basado en el contrato de reglas sintácticas de Java
- La biblioteca no debe de tener ningún tipo de posibilidad de falla ya que el publico objetivo que la utilizara seran programadores de empresas importantes como Amazon, facebook, google.

###### Prompt:
- refactorizar o corregir cualquier contenido del código que no asegure los cumplimientos de estos dogmas y refactorizarlo para que aseguren el cumplimiento regulatorio que estableció mi empresa para los d`ogmas que d`ebe de seguir la biblioteca, en dado caso que el contenido los cumpla dejarlo como está.


```
import { HttpClient } from "../lib/HttpClient";  
import { HttpRequest } from "../lib/HttpRequest";  
import { HttpMethod } from "../lib/util/HttpMethod";  
import { HttpResponse } from "../lib/HttpResponse";  
import { CachePolicy } from "../lib/util/CachePolicy";  
  
interface CreateCellDTO {  
    spaceNumber: string;  
    vehicleType: string;  
    status: string;  
}  
  
interface Response {  
    message: string;  
    details: string;  
}  
  
export interface CellDTO {  
    id: string;  
    spaceNumber: string;  
    vehicleType: string;  
    status: string;  
    createdAt: Date;  
}  
  
export class Main {  
    public static async main(): Promise<void> {  
        try {  
            await Main.testGet();  
        } catch (error) {  
            console.error('Error en las pruebas:', error);  
        }  
    }  
  
    private static async testPost(): Promise<void> {  
  
        const body: CreateCellDTO = {  
            spaceNumber: "8",  
            vehicleType: "AUTOMOVIL",  
            status: "DISPONIBLE"  
        }  
  
        const client: HttpClient = HttpClient.newHttpClient();  
  
        const request: HttpRequest = HttpRequest.newBuilder()  
            .url("http://localhost:8080/v1/cells")  
            .method(HttpMethod.POST)  
            .cache(CachePolicy.DEFAULT)  
            .body<CreateCellDTO>(body)  
            .header("Content-Type", "application/json")  
            .build()  
  
        const response: HttpResponse<Response> = await client.send<Response>(request);  
  
        console.log(request.body<CreateCellDTO>());  
        console.log(response.body());  
  
  
    }  
  
    private static async testGet(): Promise<void> {  
  
        const client: HttpClient = HttpClient.newHttpClient();  
  
        const request: HttpRequest = HttpRequest.newBuilder()  
            .url("http://localhost:8080/v1/cells")  
            .method(HttpMethod.GET)  
            .build()  
  
        const response: HttpResponse<CellDTO[]> = await client.send<CellDTO[]>(request);  
  
        console.log(response.body());  
  
  
    }  
  
  
}  
  
Main.main();
```

representante legal:
```
let component = Array.from(document.querySelectorAll('*'))
  .find(e => e.__ngContext__ && 
    e.__ngContext__.length && 
    e.__ngContext__.some(c => c && c.form && c.legalRepresentativeArray))
  ?.__ngContext__
  ?.find(c => c && c.form && c.legalRepresentativeArray);

if (component) {
  // Obtener el FormArray
  let formArray = component.legalRepresentativeArray;
  
  formArray.controls.forEach(control => {
    let primerApellidoControl = control.get('primerApellido');
    if (primerApellidoControl) {
      // Eliminar la validación existente y mantener solo required
      let currentValidators = primerApellidoControl.validator;
      primerApellidoControl.setValidators([
        control => control.value ? null : { required: true }
      ]);
      primerApellidoControl.updateValueAndValidity();
    }
  });
}
```
accionista:

```
let component = Array.from(document.querySelectorAll('*'))
  .find(e => e.__ngContext__ && 
    e.__ngContext__.length && 
    e.__ngContext__.some(c => c && c.form && c.shareholderArray))
  ?.__ngContext__
  ?.find(c => c && c.form && c.shareholderArray);

if (component) {

  let formArray = component.shareholderArray;
  
  formArray.controls.forEach(control => {
    let primerApellidoControl = control.get('primerApellido');
    if (primerApellidoControl) {
      // Eliminar la validación existente y mantener solo required
      primerApellidoControl.setValidators([
        control => control.value ? null : { required: true }
      ]);
      primerApellidoControl.updateValueAndValidity();
    }
  });
}
```

3. Verificar si estás autenticado en NPM:
npm login
npm notice Log in on https://registry.npmjs.org/
Login at:
https://www.npmjs.com/login?next=/login/cli/62fc659c-d04b-48e2-b028-73524ff8b7e6
Press ENTER to open in the browser...

Logged in on https://registry.npmjs.org/.
Perfecto! El paquete se ve bien. Ahora vamos a crear un tag para la versión 3.0.0:
git push origin v3.0.0
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/SantiagoVOGIT/http-client-for-ts.git
 * [new tag]         v3.0.0 -> v3.0.0
5. Finalmente, publica tu paquete en NPM:
bash