###### Dogmas base estrictos a seguir: 
- Principios y sintaxis de POO estrictamente igual a la de java, o lo más similar posible de acuerdo al limite del lenguaje.
- En el constructor no deben haber construcciones internas de funciones. se limita a llamarlas. Por ejemplo. this.metodoInterno(); eso es erroneo, .el constructor solo debe de tener atributos y debe verse así. Ejemplo: this.atributo = metodo() (en dado caso que se necesite una función como el valor de un atributo del constructor, ojo únicamente si es necesario, de lo contrario no lo hagas)
- Tipado fuerte para métodos, atributos, constantes y variables, ósea tipado fuerte para todo
- Asignación de `#` para métodos y atributos que deben encapsularse de manera privada por su naturaleza. 
- Se usa un get logico para los getters. ejemplo:  `getInfo`
- Asignación de `static` para métodos u atributos que deben ser estáticos por su naturaleza y su contexto
- Siempre se declaran primero los atributos de clase en la parte superior asignándosele únicamente su tipo de dato y su modificador de acceso, similar a java
- Se usa `export class (nombre clase)` para exportar clases
-  No deben haber if anidados, se usa guard clauses u otra estrategia que veas correcta. pero que no implique anidar if