---
aliases: 
tags:
---
###### Concepto:

En **Java**, cada [[1.2 Variable|variable]] tiene un [[1.7 Tipos de datos|tipo de dato]] específico que determina qué clase de datos puede contener y cuánta [[Memoria|memoria]] ocupa.

**Sintaxis:** Las variables se pueden [[1.2.1 Declaración|declarar]] e [[1.2.2 Inicialización|inicializar]] de varias formas:

```java
// Forma 1: declaración e inicialización por separado
Tipo nombreVariable;
nombreVariable = valor;

// Forma 2: declaración e inicialización conjunta
Tipo nombreVariable = valor;

// Forma 3: declaración de varias variables del mismo tipo
Tipo var1, var2, var3;
```

Las variables en Java deben seguir estas **normas de nomenclatura**:

**Convenciones recomendadas:**

- Se utiliza la notación [[2.4.1 camelCase|camelCase]] para los identificadores (ejemplo: `contadorTotal`)
- Se emplean nombres descriptivos que indiquen el propósito de la variable

**Restricciones obligatorias:**

- No pueden comenzar con un dígito
- Solo admiten letras (A–Z, a–z), dígitos (0–9), guiones bajos (`_`) y el símbolo de dólar (`$`)
- No pueden coincidir con palabras reservadas de Java
- No pueden contener espacios en blanco
- Se deben evitar caracteres fuera del alfabeto inglés como la letra 'ñ', tildes (á, é, í, ó, ú) o diéresis (ü)

**Inicialización:** Las variables locales deben inicializarse antes de ser utilizadas, mientras que las variables de instancia se inicializan automáticamente con valores por defecto (`0`, `false`, `null` según el tipo).

###### Anotaciones:

> 

######  Recursos:

- [VARIABLES en Java ☕ Todo lo que tenés que saber ✅](https://youtu.be/OG7CNqAQ954?si=LBztgEgFHVOnJBhF)