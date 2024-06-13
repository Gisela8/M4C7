# M4C7

## Checkpoint_7

## ¿Qué diferencia a Javascript de cualquier otro lenguaje de programación?

**Compilado vs interpretado**
Una de las principales diferencias entre JavaScript y otros lenguajes de programación es cómo se ejecutan. 
La mayoría de los lenguajes de programación son compilados, lo que significa que el código debe compilarse en código de máquina antes de poder ejecutarse. 
JavaScript es un lenguaje interpretado, lo que significa que no es necesario compilarlo antes de poder ejecutarlo. 
Esto hace que sea más fácil trabajar con JavaScript, ya que se no tiene que esperar a que se compile su código antes de poder probarlo.

**Del lado del cliente frente al lado del servidor**
Otra diferencia clave entre JavaScript y otros lenguajes de programación es dónde se ejecutan. JavaScript está diseñado para ejecutarse en navegadores web y, 
por lo tanto, es un lenguaje de programación del lado del cliente. Esto significa que el código escrito en JavaScript se ejecutará en la computadora del usuario en lugar de en el servidor.
Por otro lado, otros lenguajes de programación suelen ejecutarse en el lado del servidor, lo que significa que deben enviarse desde el servidor a la computadora del usuario antes de poder ejecutarse.

**Orientado a objetos versus procesal**
JavaScript es un lenguaje de programación orientado a objetos. Esto significa que el código escrito en JavaScript se compone de objetos que contienen datos y funciones. 
Estos objetos se pueden manipular y utilizar para crear programas complejos. 
Por otro lado, muchos otros lenguajes de programación son procedimentales, lo que significa que el código escrito en estos lenguajes consta de una serie de instrucciones que deben seguirse en orden.


**Escritura dinámica versus estática**
Otra diferencia clave entre JavaScript y otros lenguajes de programación es cómo manejan los tipos de datos. JavaScript es un lenguaje dinámico, lo que significa que las variables no necesitan declararse con un tipo específico. 
Esto facilita el trabajo con datos ya no se tiene que especificar su tipo al declarar variables. 
Otros lenguajes de programación suelen tener tipos estáticos, lo que significa que las variables deben declararse con un tipo específico antes de poder usarse.

##  ¿Cuáles son algunos tipos de datos JS?

**Tipos de datos**
Un valor en JavaScript siempre pertenece a un tipo de dato determinado. Por ejemplo, un string o un número.
Se puede almacenar un valor de cualquier tipo dentro de una variable. 
Por ejemplo, una variable puede contener en un momento un string y luego almacenar un número:

    //no hay error
    let message = "hola";
    message = 123456;``

Los lenguajes de programación que permiten estas cosas, como JavaScript, se denomina “dinámicamente tipados”, lo que significa que allí hay tipos de datos, pero las variables no están vinculadas rígidamente a ninguno de ellos.

**Hay ocho tipos de datos básicos en JavaScript.** 

### Number

    Number
    let n = 123;
    n = 12.345; ``

El tipo number representa tanto números enteros como de punto flotante.
Hay muchas operaciones para números. Por ejemplo, multiplicación *, división /, suma +, resta -, y demás.
Además de los números comunes, existen los llamados **“valores numéricos especiales”** que también pertenecen a este tipo de datos: Infinity, -Infinity y NaN.

**• Infinity** representa el Infinito matemático ∞. Es un valor especial que es mayor que cualquier número.
Podemos obtenerlo como resultado de la división por cero:

    alert( 1 / 0 ); 
    // Infinity``

O simplemente hacer referencia a él directamente:

    alert( Infinity ); 
    // Infinity``

**• NaN** representa un error de cálculo. 
Es el resultado de una operación matemática incorrecta o indefinida
por ejemplo:

    alert( "no es un número" / 2 );
    // NaN, tal división es errónea

Cualquier otra operación sobre NaN devuelve NaN:

    alert( NaN + 1 ); 
    // NaN alert( 3 * NaN ); 
    // NaN alert( "not a number" / 2 - 1 ); 
    // NaN ``

Por lo tanto, si hay un NaN en alguna parte de una expresión matemática, se propaga a todo el resultado (con una única excepción: NaN ** 0 es 1).

[Números](https://es.javascript.info/number).


### BigInt

En JavaScript, el tipo “number” no puede representar de forma segura valores enteros mayores que (2^53-1) (eso es 9007199254740991), o menor que -(2^53-1) para negativos.

Para ser realmente precisos, el tipo de dato “number” puede almacenar enteros muy grandes (hasta 1.7976931348623157 * 10308), pero fuera del rango de enteros seguros ±(2^53-1) habrá un error de precisión, porque no todos los dígitos caben en el almacén fijo de 64-bit. Así que es posible que se almacene un valor “aproximado”.

Por ejemplo, estos dos números (justo por encima del rango seguro) son iguales:

    console.log(9007199254740991 + 1); 
    // 9007199254740992 console.log(9007199254740991 + 2); 
    // 9007199254740992

Se puede decir que ningún entero impar mayor que (2^53-1) puede almacenarse en el tipo de dato “number”.
Para la mayoría de los propósitos, el rango ±(2^53-1) es suficiente, pero a veces se necesitan números realmente grandes; por ejemplo, para criptografía o marcas de tiempo de precisión de microsegundos.

BigInt se agregó recientemente al lenguaje para representar enteros de longitud arbitraria.

Un valor BigInt se crea agregando n al final de un entero:

    // la "n" al final significa que es un BigInt 
    const bigInt = 1234567890123456789012345678901234567890n; 

### String

Una  string en JavaScript es una cadena de caracteres y debe colocarse entre comillas.

    let str = "Hola";
    let str2 = 'Las comillas simples también están bien';
    let phrase = `se puede incrustar otro ${str}`; ``

En JavaScript, hay 3 tipos de comillas.

        1. Comillas dobles:`` "Hola"``.
        2. Comillas simples: ``'Hola'``.
        3. Backticks (comillas invertidas): ``Hola``.

Las comillas dobles y simples son comillas “sencillas” (funcionan igual).

Los backticks son comillas de “funcionalidad extendida”. Nos permiten incrustar variables y expresiones en una cadena de caracteres encerrándolas en ${...}, por ejemplo:

    let name = "John";
    // incrustar una variable
    alert( `Hola, ${name}!` ); // Hola, John!
   // incrustar una expresión
   alert( `el resultado es ${1 + 2}` ); //el resultado es 3 ``

La expresión dentro de ${...} se evalúa y el resultado pasa a formar parte de la cadena. 
Se puede poner cualquier cosa ahí dentro: una variable como name, una expresión aritmética como 1 + 2, o algo más complejo. Esto sólo se puede hacer con los backticks. 

    alert( "el resultado es ${1 + 2}" ); 
    // el resultado es ${1 + 2} (las comillas dobles no hacen nada) ``

### Boolean (tipo lógico)

El tipo boolean tiene sólo dos valores posibles: true y false.
Este tipo se utiliza comúnmente para almacenar valores de sí/no: true significa “sí, correcto, verdadero”, y false significa “no, incorrecto, falso”.

Por ejemplo:

    let nameFieldChecked = true; 
    // sí, el campo name está marcado
    let ageFieldChecked = false; // no, el campo age no está marcado ``

Los valores booleanos también son el resultado de comparaciones:

    let isGreater = 4 > 1;
    alert( isGreater ); 
    // verdadero (el resultado de la comparación es "sí")


### El valor “null” (nulo)

El valor especial null no pertenece a ninguno de los tipos descritos anteriormente.
Forma un tipo propio separado que contiene sólo el valor null:

    let age = null;

En JavaScript, null no es una “referencia a un objeto inexistente” o un “puntero nulo” como en otros lenguajes.
Es sólo un valor especial que representa “nada”, “vacío” o “valor desconocido”.
El código anterior indica que el valor de age es desconocido o está vacío por alguna razón.

### El valor “undefined” (indefinido)

El valor especial undefined también se distingue. Hace un tipo propio, igual que null.
El significado de undefined es “valor no asignado”.
Si una variable es declarada, pero no asignada, entonces su valor es undefined:


    let age; 
    alert(age); // muestra "undefined"``


Técnicamente, es posible asignar undefined a cualquier variable:


    let age = 100;
   // cambiando el valor a undefined
   age = undefined; 
   alert(age); // "undefined"``


### Object y Symbol

El tipo object (objeto) es especial.

Todos los demás tipos se llaman “primitivos” porque sus valores pueden contener una sola cosa (ya sea una cadena, un número, o lo que sea). 

Los objetos se utilizan para almacenar colecciones de datos y entidades más complejas. El tipo symbol se utiliza para crear identificadores únicos para los objetos. 

### El operador typeof
El operador typeof devuelve el tipo de dato del operando. 
Es útil cuando se quiere procesar valores de diferentes tipos de forma diferente o simplemente se quiere hacer una comprobación rápida.

La llamada a typeof x devuelve una cadena con el nombre del tipo:

        typeof undefined // "undefined"
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

**Enlaces de interés**

[javascript.info](https://es.javascript.info/types#resumen)
[hubspot](https://blog.hubspot.es/website/tipos-de-datos-javascript)


## ¿Cuáles son las tres funciones de String en JS?

### longitud
La propiedad length devuelve la longitud de la cadena.

    const empresa = "GeekFlare";console.log(empresa.longitud);


### toUpperCase()
El método toUpperCase convierte cada carácter de la cadena a mayúsculas y lo devuelve. No cambia la cadena original.

    const empresa = "GeekFlare";
    const empresaMayúsculas = empresa.toUpperCase();
    console.log(empresaMayúsculas);''

### toLowerCase()
El método toLowerCase convierte cada carácter de la cadena a minúscula y lo devuelve. No cambia la cadena original.

    const empresa = "GeEkFlaRe";
    const minúsculasEmpresa = empresa.aMinúsculas();
    console.log(minúsculasEmpresa);

### recortar()
El método trim elimina los espacios en blanco iniciales y finales de la cadena. Es una operación in situ, es decir, actualiza la cadena original.

        const empresa = " Geek Flare ";

        console.log(empresa);
        console.log(empresa.recortar());

### charAt(índice)
El método charAt devuelve el carácter en el índice dado. Devuelve una cadena vacía si el índice no es válido.

        const empresa = "GeekFlare";

        console.log(empresa.charAt(2));
        console.log(empresa.charAt(10));

### charCodeAt(índice)
El método charCodeAt devuelve el código ASCII del carácter en el índice dado. Devuelve NaN si el índice no es válido.

        const empresa = "GeekFlare";

        console.log(empresa.charCodeAt(2));
        console.log(empresa.charCodeAt(10));

### slice(startIndex, endIndex)
El método slice devuelve la subcadena de la cadena desde startIndex hasta endIndex (sin incluir). El string.slice(0, 6) devuelve la subcadena desde el índice 0 hasta el índice 5.

        const empresa = "GeekFlare";
        console.log(empresa.slice(0, 4));

El método slice también aceptará un único argumento. Si pasa un único argumento al método slice, éste devolverá la subcadena desde el índice dado hasta el final de la cadena.

        const empresa = "GeekFlare";
        console.log(empresa.slice(4));

El método slice también aceptará índices negativos. Los índices negativos se cuentan desde el final de la cadena. 
Dada la cadena GeekFlare, los índices negativos son

        G = -9, e = -8, e = -7, k = -6 y así sucesivamente…
        
El código string.slice(-9, -5) devolverá Geek para el ejemplo anterior.
        
        const empresa = "GeekFlare";
        console.log(empresa.slice(-9, -5));
        

El código string.sl ice(-5) devolverá Flare para el ejemplo anterior.

        const empresa = "GeekFlare";
        console.log(empresa.slice(-5));


### El método substr(inicioIndice, longitud) 
Es similar al método slice. La única diferencia es que el método substr acepta la longitud de la subcadena que debe extraerse de la cadena original.
        const empresa = "GeekFlare";
        console.log(empresa.substr(4, 5));

Existe otro método llamado substring que es similar al método slice. Pero, el método substring no acepta índices negativos. 

### replace(substring, newSubstring)
El método replace sustituye la primera instancia de la subcadena por la nuevaSubcadena.

        const enunciado = "Visite el sitio Google";
        console.log(statement.replace("Google", "GeekFlare"));

### indexOf(substring)
El método indexOf devuelve el índice inicial de un carácter dado de la cadena. Devolverá -1 si el carácter no está presente en la cadena.

        const empresa = "GeekFlare";
        console.log(empresa.indexOf("Flare"));
        console.log(empresa.indexOf("O"));

El método indexOf aceptará el segundo argumento, que es un índice a partir del cual comienza la búsqueda de la subcadena dada.

        const empresa = "GeekFlare";
        console.log(empresa.indexOf("e"));
        console.log(empresa.indexOf("e", 5));

Existe otro método llamado lastIndexOf que es similar al método indexOf. La única diferencia es que el método lastIndexOf busca el carácter desde el final de la cadena y devuelve el índice de la primera instancia del carácter.

### split(subcadena)
El método split divide la cadena dada en la subcadena y devuelve las partes como una matriz.

        const statement = "Visite, el, sitio, GeekFlare";
        console.log(statement.split(" "));
        console.log(statement.split(", "));
        

**Enlaces de interés**

[desarrolloweb.com](https://desarrolloweb.com/articulos/objetos-string-javascript.html)
[MDN.org](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Functions)
[Objects_indexOf](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)

## ¿Qué es un condicional?

JavaScript cuenta con 4 tipos de declaraciones para el uso de condicionales.

1. Declaración If.
2. Declaración Else.
3. Declaración Else if.
4. Declaración Switch.
   

### 1. Declaración If
En JavaScript, la declaración if se usa para evaluar una expresión. Si la expresión dentro de esta condición es evaluada como verdadera, se ejecutará la instrucción definida dentro del bloque if; en caso contrario, si la expresión es falsa, la instrucción no se ejecutará. Es una forma de introducir lógica condicional en el código, permitiendo que ciertas acciones se realicen solo cuando se cumplen ciertas condiciones.

        const n = parseInt(prompt("choose number"));
        if(n % 2 == 0){
          console.log("The number is even");
        }
Es importante señalar que la declaración condicional if en JavaScript realiza una conversión automática a booleano de la expresión proporcionada. 
Esto implica que si se le pasa un valor almacenado en una variable, es crucial tener en cuenta los tipos de datos considerados como falsos.

En JavaScript, hay ciertos tipos de datos que se consideran automáticamente como valores falsos. Estos incluyen:
1. false - El valor booleano false.
2. null - El valor nulo.
3. undefined - El valor indefinido.
4. 0 - El número entero cero.
5. -0 - El número entero negativo cero.
6. NaN - El valor Not-a-Number.
7. '' - La cadena vacía.
8. [] - El array vacío.
9. {} - El objeto vacío.
    
### 2. Declaración Else
En JavaScript, la declaración else se utiliza en conjunto con una declaración if. La declaración else se ejecuta únicamente si la condición evaluada por la declaración if resulta ser falsa. 
Cuando la instrucción dentro del if no se ejecuta debido a que la condición es falsa, entonces la instrucción dentro del bloque else es la que se ejecuta. 
Esto proporciona una bifurcación en la lógica del programa, permitiendo definir acciones alternativas cuando la condición inicial no se cumple.


        const n = parseInt(prompt("choose number"));
        if(n % 2 == 0){
          console.log("The number is even");
        } else {
          console.log("The number is odd");
        }
        
### 3. Declaración Else if
En JavaScript, la declaración else if se emplea para especificar condiciones adicionales dentro de la estructura de un bloque if. 
Si la primera condición en el bloque if resulta ser falsa, el programa procederá a verificar la siguiente condición dentro de else if.

La declaración else if es útil para añadir casuísticas adicionales a la evaluación, permitiendo así gestionar múltiples condiciones de manera organizada. 
Es importante destacar que es posible anidar varias declaraciones else if según la necesidad y criterio. 
Esto proporciona flexibilidad en la lógica del programa al permitir manejar diferentes escenarios en función de las condiciones evaluadas.

        const aliceAge = parseInt(prompt("choose number"));
        if (aliceAge < 18) {
          console.log("Alice is minor than 18 years.");
        } else if (aliceAge >= 18 && aliceAge <= 21) {
          console.log("Alice has between 18 and 21 years.");
        } else {
          console.log("Alice has more than 21 years.");
        }
        
### 4. Declaración Switch
A diferencia de las declaraciones previamente mencionadas, la estructura switch se enfoca en realizar comparaciones precisas de casos. 
En un bloque switch, se evalúa un valor contra diferentes casos hasta encontrar una coincidencia.
En lugar de utilizar expresiones booleanas como en if o else if, switch compara directamente el valor proporcionado con los casos definidos. 
Esto puede hacer que el código sea más legible y fácil de entender cuando se necesita comprobar una variable contra múltiples valores específicos. 
Switch permite ejecutar diferentes bloques de código según el caso coincidente, proporcionando una forma alternativa y estructurada de gestionar múltiples condiciones.

        const currentDay = new Date().getDay();
        let day;
        switch (currentDay) {
          case 0:
            day = "Sunday";
            break;
          case 1:
            day = "Monday";
            break;
          case 2:
            day = "Tuesday";
            break;
          case 3:
            day = "Wednesday";
            break;
          case 4:
            day = "Thursday";
            break;
          case 5:
            day = "Friday";
            break;
          case 6:
            day = "Saturday";
            break;
        }
        console.log(`Today is ${day}`);

**Enlaces de interés**

[sessionstrack](https://medium.com/sessionstack-blog/how-javascript-works-the-different-types-of-conditional-statements-3-best-practices-756e7d3e275a)
[JS-if-else-switch](https://medium.com/@diego.coder/condicionales-en-javascript-if-if-else-y-switch-3f833b664bff)
[MDN](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/if...else)


## ¿Qué es un operador ternario?

El operador ternario es una alternativa al condicional if/else de una forma mucho más compacta y breve, que en muchos casos resulta más legible. 

La sintaxis de un operador ternario es la siguiente:
        
        condición ? valor verdadero : valor falso;


        let nota = 7;
        console.log("He realizado mi examen. Mi resultado es el siguiente:");

        if (nota < 5) {
          // Acción A: nota es menor que 5
          calificacion = "suspendido";
        } else {
          // Acción B: Cualquier otro caso diferente a A (nota es mayor o igual que 5)
          calificacion = "aprobado";
        }

        console.log("Estoy", calificacion);
        
Utilizando un operador ternario:

        
        let nota = 7;
        console.log("He realizado mi examen. Mi resultado es el siguiente:");

        // Operador ternario: (condición ? verdadero : falso)
        let calificacion = nota < 5 ? "suspendido" : "aprobado";

        console.log("Estoy", calificacion);

**Operador ternario anidado**

Cuando se trata de if muy pequeños. Si intentasemos realizar una comprobación de if múltiples con el operador ternario, la sintaxis puede resultar compleja y difícil de leer. Observa el siguiente ejemplo con múltiples if / else:

        let nota = 7;
        console.log("He realizado mi examen.");

        if (nota < 5) {
          calificacion = "Insuficiente";
        } else if (nota < 6) {
          calificación = "Suficiente";
        } else if (nota < 8) {
          calificacion = "Bien";
        } else if (nota <= 9) {
          calificacion = "Notable";
        } else {
          calificacion = "Sobresaliente";
        }

        console.log("He obtenido un", calificacion);
        
Utilizando operadores ternarios anidados:
        
        let nota = 7;
        console.log("He realizado mi examen.");

        let calificacion =
          nota < 5 ? "Insuficiente" :
          nota < 6 ? "Suficiente" :
          nota < 8 ? "Bien" :
          nota <= 9 ? "Notable" :
          "Sobresaliente";

        console.log("He obtenido un", calificacion);
        
Son múltiples operadores ternarios anidados uno dentro de otro. El "valor falso" del primer operador ternario, es un nuevo operador ternario, que a su vez su valor falso es un nuevo operador ternario, y así con varios casos más.


**Enlaces de interés**

[operador-ternario](https://lenguajejs.com/fundamentos/estructuras-de-control/operador-ternario/)
[operador-ternario-js](https://desarrolloweb.com/articulos/operador-ternario-javascript)

## ¿Cuál es la diferencia entre una declaración de función y una expresión de función?

Las declaraciones de funciones están elevadas, lo que significa que se pueden utilizar antes de declarar la función. 
Se inicializan en tiempo de compilación mientras no se genera una expresión de función, solo se pueden llamar después de que el intérprete declara y lee la función.

JavaScript al ser un lenguaje dinámico tiene ciertos mecanismos para garantizar que la ejecución de nuestro código sea la más óptima y correcta.

En JavaScript se tiene dos maneras principales de definir funciones, como una declaración o como una expresión.

        // declaraciones de función // Función con nombre function suma1(a, b) { return a + b } // 
        
        // expresiones de función // Función anónima var suma2 = function(a, b) { return a + b } 
        // Función con nombre var suma2 = function suma2(a, b) { return a + b } 
        // Función de flecha (anónima por defecto) var suma2 = (a, b) => { return a + b }
        // declaraciones de función

        // Función con nombre
        function suma1(a, b) {
          return a + b
        }

        // expresiones de función

        // Función anónima
        var suma2 = function(a, b) {
          return a + b
        }

        // Función con nombre
        var suma2 = function suma2(a, b) {
          return a + b
        }

        // Función de flecha (anónima por defecto)
        var suma2 = (a, b) => {
          return a + b
        }
        
**Las diferencias de sintaxis** 
son claras, las expresiones de funciones principalmente están a la DERECHA del símbolo igual, y las declaraciones NO. 
Se puedee llamar a una declaración de función antes de la declaración en sí y con las expresiones no. 

**Hoisting**
Cuando el código JavaScript se ejecuta, el intérprete mueve todas las declaraciones del programa al inicio. 

Ejemplo:

        var nombre = "Rick" var apellido = "Sanchez" function nombreCompleto(primero, segundo) { return `${primero} ${segundo}` } 
        var pintarEdad = function (numero) { console.log(`la edad es de ${numero} años`) }
        var nombre = "Rick"
        var apellido = "Sanchez"
        function nombreCompleto(primero, segundo) {
          return `${primero} ${segundo}`
        }
        var pintarEdad = function (numero) {
          console.log(`la edad es de ${numero} años`)
        }
        
Declaraciones de variables, como asignaciones de valores; y ambas cosas pasan en momentos separados.
El intérprete de JavaScript lo que realmente hace es declarar todas las variables y funciones primero antes de asignar y ejecutar cualquier otro valor. 
Si se quisiese ver el orden real en el que se va ejecutando cada cosa, sería algo así:

        // declaraciones primero var nombre; var apellido; function nombreCompleto(primero, segundo) { return `${primero} ${segundo}` } 
        var pintarEdad; // asignaciones después nombre = "Rick" apellido = "Sanchez" pintarEdad = function(numero) { console.log(`la edad es de ${numero} años`)
        // declaraciones primero
        var nombre;
        var apellido;
        function nombreCompleto(primero, segundo) {
    r        eturn `${primero} ${segundo}`
        }
                var pintarEdad;

        // asignaciones después
        nombre = "Rick"
        apellido = "Sanchez"
        pintarEdad = function(numero) {
            console.log(`la edad es de ${numero} años`)

A este "reorden" se le llama Hoisting. La declaración y la inicialización de una variable o función ocurren en momentos distintos, incluso cuando los escribes en la misma línea.

**Diferencias**

• Las declaraciones de funciones pueden ser ejecutadas antes de su definición.
• Declaraciones a la derecha, expresiones a la izquierda.
• Las expresiones son más difíciles de inspeccionar.

        nuevaFuncion() function nuevaFuncion() { console.log("Hola Mundo!") } // Hola Mundo!
        nuevaFuncion()

        function nuevaFuncion() {
          console.log("Hola Mundo!")
        }

        // Hola Mundo!

En cambio, esto no es posible con las expresiones de funciones, ya que no se sabe el valor que va a tener la variable previamente declarada.

        nuevaFuncion() var nuevaFuncion = function nuevaFuncion() { console.log("Hola Mundo!") } // TypeError: nuevaFuncion is not a function
        nuevaFuncion()

        var nuevaFuncion = function nuevaFuncion() {
          console.log("Hola Mundo!")
        }

        //  TypeError: nuevaFuncion is not a function
        
**Declaraciones a la Izquierda, Expresiones a la Derecha**

**La palabra reservada function** 
se puede usar tanto al lado izquierdo como al lado derecho del signo =. Lo interesante de esto es que siguen diferentes reglas dependiendo de dónde se escriban.

Cuando se usan  al lado izquierdo, se está creando una declaración de función y es obligatorio asignar un nombre.
En cambio, si se usa  a la derecha del símbolo igual, hablamos de una expresión de función.

        // declaración de función function soyUnaDeclaracion() { // ... } // expresión de función var soyUnaExpresion = function() { // ... }
        // declaración de función
        function soyUnaDeclaracion() {
          // ...
        }

        // expresión de función
        var soyUnaExpresion = function() {
          // ...
        }

***Curiosidad:*** En las expresiones de funciones darle nombre a la función es opcional. En cambio para las declaraciones es obligatorio.
En este último caso, la función pasa a ser una función anónima, algo conveniente ya que el programa sigue funcionando sin problemas, pero puede tener algunas implicaciones a la hora de inspeccionar la cola de ejecución del programa.


**Enlaces de interés**

[Expresiones-de-funciones](https://www.escuelafrontend.com/declaraciones-de-funciones-y-expresiones-de-funciones)
[Functions](https://ui.dev/arrow-functions/)


## ¿Qué es la palabra clave "this" en JS?

Una de las formas más comunes en las que se utiliza la palabra clave this en JavaScript es en las clases. 
Propiedades de una clase. En vez de utilizar el nombre del objeto, se utiliza this. Esto es muy útil cuando se quiere  cambiar el nombre del objeto o este no tiene un nombre específico.

Ejemplo con dos formas de utilizar la palabra clave this en JavaScript. 

        Array.prototype.shuffle = function ( ) => {

        var i = this.length, j, temp;

        if (i == 0) return this;

        while ( –i ) {

        j = Math.floor (Math.random ( ) * (i + 1) );

        temp = this [i]

        this [i] = this [j];

        this [j] = temp;

        }

        return this;

        }

        }

En este contexto, se está alterando el prototipo del objeto, la palabra clave this hace referencia a un array. Por ello, se utiliza la palabra clave this para poder acceder a sus propiedades. 
En la segunda línea de código de este método, se puede ver escrito this.length. Se usa this para acceder a la propiedad de longitud del array en cuestión. Atribuyendo esta propiedad a la variable i.

Del mismo modo, se está utilizando la palabra clave this como resultado de la función, se pone después de la palabra clave return. 
Se está diciendo, después de la función, el programa nos devolverá el array que se está manipulando.

Cuando se utiliza this fuera de un objeto, clase o función, su valor es igual al objeto global. 


**Enlaces de interés**

[freecodecamp](https://www.freecodecamp.org/espanol/news/como-usar-la-palabra-clave-this-en-javascript/)
[keepcoding](https://keepcoding.io/blog/que-es-this-en-javascript/)
[MDSN](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Operators/this)
[wmedia](https://wmedia.es/aprender-usar-this-javascript/)


