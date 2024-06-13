# M4C7
Checkpoint_7
## ¿Qué diferencia a Javascript de cualquier otro lenguaje de programación?
**Compilado vs interpretado**
Una de las principales diferencias entre JavaScript y otros lenguajes de programación es cómo se ejecutan. La mayoría de los lenguajes de programación son compilados, lo que significa que el código debe compilarse en código de máquina antes de poder ejecutarse. 
Por otro lado, JavaScript es un lenguaje interpretado, lo que significa que no es necesario compilarlo antes de poder ejecutarlo. Esto hace que sea más fácil trabajar con JavaScript, ya que se no tiene que esperar a que se compile su código antes de poder probarlo.

**Del lado del cliente frente al lado del servidor**
Otra diferencia clave entre JavaScript y otros lenguajes de programación es dónde se ejecutan. Como se mencionó anteriormente, JavaScript está diseñado para ejecutarse en navegadores web y, por lo tanto, es un lenguaje de programación del lado del cliente. Esto significa que el código escrito en JavaScript se ejecutará en la computadora del usuario en lugar de en el servidor. Por otro lado, otros lenguajes de programación suelen ejecutarse en el lado del servidor, lo que significa que deben enviarse desde el servidor a la computadora del usuario antes de poder ejecutarse.

**Orientado a objetos versus procesal**
JavaScript es un lenguaje de programación orientado a objetos. Esto significa que el código escrito en JavaScript se compone de objetos que contienen datos y funciones. Estos objetos se pueden manipular y utilizar para crear programas complejos. Por otro lado, muchos otros lenguajes de programación son procedimentales, lo que significa que el código escrito en estos lenguajes consta de una serie de instrucciones que deben seguirse en orden.


**Escritura dinámica versus estática**
Otra diferencia clave entre JavaScript y otros lenguajes de programación es cómo manejan los tipos de datos. JavaScript es un lenguaje dinámico, lo que significa que las variables no necesitan declararse con un tipo específico. Esto facilita el trabajo con datos ya no se tiene que especificar su tipo al declarar variables. Otros lenguajes de programación suelen tener tipos estáticos, lo que significa que las variables deben declararse con un tipo específico antes de poder usarse.

##  ¿Cuáles son algunos tipos de datos JS?

**Tipos de datos**
Un valor en JavaScript siempre pertenece a un tipo de dato determinado. Por ejemplo, un string o un número.
Podemos almacenar un valor de cualquier tipo dentro de una variable. 
Por ejemplo, una variable puede contener en un momento un string y luego almacenar un número:

`` //no hay error

let message = "hola";

message = 123456;``

Los lenguajes de programación que permiten estas cosas, como JavaScript, se denomina “dinámicamente tipados”, lo que significa que allí hay tipos de datos, pero las variables no están vinculadas rígidamente a ninguno de ellos.

**Hay ocho tipos de datos básicos en JavaScript.** 

### Number

``Number
let n = 123;

n = 12.345;``

El tipo number representa tanto números enteros como de punto flotante.
Hay muchas operaciones para números. Por ejemplo, multiplicación *, división /, suma +, resta -, y demás.
Además de los números comunes, existen los llamados **“valores numéricos especiales”** que también pertenecen a este tipo de datos: Infinity, -Infinity y NaN.

**• Infinity** representa el Infinito matemático ∞. Es un valor especial que es mayor que cualquier número.
Podemos obtenerlo como resultado de la división por cero:

``alert( 1 / 0 ); 

// Infinity``

O simplemente hacer referencia a él directamente:

``alert( Infinity ); 

// Infinity``

**• NaN** representa un error de cálculo. 
Es el resultado de una operación matemática incorrecta o indefinida
por ejemplo:

``alert( "no es un número" / 2 ); 

// NaN, tal división es errónea``

Cualquier otra operación sobre NaN devuelve NaN:

``alert( NaN + 1 ); // NaN

alert( 3 * NaN ); // NaN

alert( "not a number" / 2 - 1 ); // NaN``

Por lo tanto, si hay un NaN en alguna parte de una expresión matemática, se propaga a todo el resultado (con una única excepción: NaN ** 0 es 1).
[Números](https://es.javascript.info/number).


### BigInt

En JavaScript, el tipo “number” no puede representar de forma segura valores enteros mayores que (2^53-1) (eso es 9007199254740991), o menor que -(2^53-1) para negativos.

Para ser realmente precisos, el tipo de dato “number” puede almacenar enteros muy grandes (hasta 1.7976931348623157 * 10308), pero fuera del rango de enteros seguros ±(253-1) habrá un error de precisión, porque no todos los dígitos caben en el almacén fijo de 64-bit. Así que es posible que se almacene un valor “aproximado”.

Por ejemplo, estos dos números (justo por encima del rango seguro) son iguales:

``console.log(9007199254740991 + 1); // 9007199254740992

console.log(9007199254740991 + 2); // 9007199254740992``

Se puede decir que ningún entero impar mayor que (2^53-1) puede almacenarse en el tipo de dato “number”.
Para la mayoría de los propósitos, el rango ±(2^53-1) es suficiente, pero a veces necesitamos números realmente grandes; por ejemplo, para criptografía o marcas de tiempo de precisión de microsegundos.

BigInt se agregó recientemente al lenguaje para representar enteros de longitud arbitraria.

Un valor BigInt se crea agregando n al final de un entero:

``// la "n" al final significa que es un BigInt
const bigInt = 1234567890123456789012345678901234567890n;``

### String

Un string en JavaScript es una cadena de caracteres y debe colocarse entre comillas.

``let str = "Hola";
let str2 = 'Las comillas simples también están bien';
let phrase = `se puede incrustar otro ${str}`;``

En JavaScript, hay 3 tipos de comillas.

        1. Comillas dobles:`` "Hola"``.
        2. Comillas simples: ``'Hola'``.
        3. Backticks (comillas invertidas): ``Hola``.

Las comillas dobles y simples son comillas “sencillas” (funcionan igual).

Los backticks son comillas de “funcionalidad extendida”. Nos permiten incrustar variables y expresiones en una cadena de caracteres encerrándolas en ${...}, por ejemplo:

``let name = "John";
// incrustar una variable
alert( `Hola, ${name}!` ); // Hola, John!
// incrustar una expresión
alert( `el resultado es ${1 + 2}` ); //el resultado es 3``

La expresión dentro de ${...} se evalúa y el resultado pasa a formar parte de la cadena. 
Se puede poner cualquier cosa ahí dentro: una variable como name, una expresión aritmética como 1 + 2, o algo más complejo.Esto sólo se puede hacer con los backticks. 

``alert( "el resultado es ${1 + 2}" ); // el resultado es ${1 + 2} (las comillas dobles no hacen nada)``

### Boolean (tipo lógico)

El tipo boolean tiene sólo dos valores posibles: true y false.
Este tipo se utiliza comúnmente para almacenar valores de sí/no: true significa “sí, correcto, verdadero”, y false significa “no, incorrecto, falso”.

Por ejemplo:

``let nameFieldChecked = true; // sí, el campo name está marcado
let ageFieldChecked = false; // no, el campo age no está marcado``

Los valores booleanos también son el resultado de comparaciones:

``let isGreater = 4 > 1;
alert( isGreater ); // verdadero (el resultado de la comparación es "sí")``


### El valor “null” (nulo)

El valor especial null no pertenece a ninguno de los tipos descritos anteriormente.
Forma un tipo propio separado que contiene sólo el valor null:

``let age = null;``

En JavaScript, null no es una “referencia a un objeto inexistente” o un “puntero nulo” como en otros lenguajes.
Es sólo un valor especial que representa “nada”, “vacío” o “valor desconocido”.
El código anterior indica que el valor de age es desconocido o está vacío por alguna razón.

### El valor “undefined” (indefinido)

El valor especial undefined también se distingue. Hace un tipo propio, igual que null.

El significado de undefined es “valor no asignado”.

Si una variable es declarada, pero no asignada, entonces su valor es undefined:


``let age;

alert(age); // muestra "undefined"``


Técnicamente, es posible asignar undefined a cualquier variable:


``let age = 100;

// cambiando el valor a undefined
age = undefined; 

alert(age); // "undefined"``


### Object y Symbol

El tipo object (objeto) es especial.

Todos los demás tipos se llaman “primitivos” porque sus valores pueden contener una sola cosa (ya sea una cadena, un número, o lo que sea). 

Por el contrario, los objetos se utilizan para almacenar colecciones de datos y entidades más complejas.El tipo symbol (símbolo) se utiliza para crear identificadores únicos para los objetos. 

### El operador typeof
El operador typeof devuelve el tipo de dato del operando. 
Es útil cuando queremos procesar valores de diferentes tipos de forma diferente o simplemente queremos hacer una comprobación rápida.

La llamada a typeof x devuelve una cadena con el nombre del tipo:

``typeof undefined // "undefined"
typeof 0 // "number"
typeof 10n // "bigint"
typeof true // "boolean"
typeof "foo" // "string"
typeof Symbol("id") // "symbol"
typeof Math // "object"  (1)
typeof null // "object"  (2)
typeof alert // "function"  (3)``

typeof es un operador, no una función. Los paréntesis aquí no son parte del operador typeof. 
Son del tipo usado en agrupamiento matemático. Usualmente, tales paréntesis contienen expresiones matemáticas tales como (2 + 2), pero aquí solo tienen un argumento (x). Algunos prefieren typeof(x), aunque la sintaxis typeof x es mucho más común.

[Resumen](https://es.javascript.info/types#resumen)


## ¿Cuáles son las tres funciones de String en JS?
## ¿Qué es un condicional?
## ¿Qué es un operador ternario?
## ¿Cuál es la diferencia entre una declaración de función y una expresión de función?
## ¿Qué es la palabra clave "this" en JS?

