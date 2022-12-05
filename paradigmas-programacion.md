# Paradigmas de programación

## Características

### Abstracción

Cuando hablamos de lenguajes de alto o bajo nivel, estamos hablando de hasta que punto el lenguaje utiliza datos o estructuras cuya correspondencia con en **binario (lenguaje máquina)** no es directa.

#### Abstracción de datos

En bajo nivel podemos trabajar, por ejemplo, con número enteros (basta una conversión de decimal a binario como **BCD** para almacenar físicamente en una memoria un número) o con caracteres (basta usar una codificación como **ASCII** o **Unicode**). Estas conversiones son directas (cada número o caracter se corresponde con una codificación binaria).

#### Abstracción de control

Resume las propiedades de la transferencia de control, esto es de la modificación de la estrategia de ejecución de un programa en una situación determinada (p. ej., los bucles, las sentencias condicionales o las llamadas a subprogramas.

### Modularidad

La modularidad consiste en la separación de las funcionalidades de un programa en módulos independientes e intercambiables, de modo que cada módulo contiene todo lo necesario para realizar una determinada tarea.

Un módulo esta definido por su interfaz, esto es: los elementos que recibe y los que devuelve.

La modularidad permite en primera instancia reutilizar código: una serie de sentencias que se repiten en varias partes de un código variando solo los datos sobre los que actuan pueden definirse como una subrutina (un procedimiento o función) que tenga esos datos como interfaz (entradas y salidas).

De este modo, se escriben menos líneas de código en total, se mejora la legibilidad del código y con ello su escalabilidad, mantenimiento; y se reduce el tiempo de desarrollo.

### Ocultación de información

Es un principio de diseño que protege datos del programa de ser modificados por bloques de código que no deban acceder a ellos.

### Separation of Concerns

Principio de diseño que enfatiza que cada subrutina o bloque de código debe encargarse por completo de una determinada funcionalidad o aspecto y solo de esa.

## Paradigmas más relevantes

Un paradigma de programación es es un conjunto de conceptos y técnicas para realizar cómputos y la manera en que se deben estructurar y organizar las tareas que debe llevar a cabo un programa. Ninguno de ellos tiene una definición unánime, precisa o estandarizada; y la mayor parte se superponen en distinto grado en cada lenguaje, dando lugar al concepto de lenguajes **multiparadigma**.

## Programación imperativa

Inicialmente los lenguajes de programación se basaron en el modelo de computación de **Von Neumann**, que propuso que el **programa** fuese **almacenado** en la máquina antes de ejecutarse. De ese modo, el programa es una serie de bytes en memoria que contienen **instrucciones que serán ejecutadas secuencialmente**. De este modo, los programas se fundamentaban en:

- La ejecución secuencial de instrucciones
- El uso de variables para la representación de las posiciones de memorias
- El uso de la asignación para cambiar el valor de las variables.

La programación imperativa se centra en los cambios de **estado del programa** (instrucciones que modifican variables a lo largo de su ejecución).

El concepto de "**instrucción**" se asocia con el lenguaje máquina (o ensamblador), mientras que en lenguajes de alto nivel imperativos, se hablará normalmente de "**sentencias (statements)**". Una sentencia se compila o interpreta  y equivale a varias instrucciones a nivel máquina. En la práctica suelen utilizarse muchas veces indistintamente ambos términos. **Java** utiliza el término sentencia.

### Programación estructurada

Paradigma que busca mejorar la legibilidad (y con ello el tiempo de desarrollo) mediante la utilización exclusiva de:

- Secuencias: ejecución de sentencias secuencialmente (incluyendo llamadas a subprogramas)
- Controles de flujo (if/else)
- Iteraciónes: bucles (while, for)

Se fundamenta en el [teorema de la programación estructurada (1966)](https://es.wikipedia.org/wiki/Teorema_del_programa_estructurado) y el artículo ["Go To Statement considered Harmful" (1968)](https://es.wikipedia.org/wiki/GOTO#Controversia_sobre_el_uso_de_GOTO).

![Patrones básicos de programación estructurada](./img/structured-program-patterns.png)

### Programación procedimental / Programación modular

La programación procedimental (a menudo usado como sinónimo de imperativa) enfatiza el uso de llamadas a **procedimientos** (subrutinas) y es la primera forma de [modularidad](#modularidad). Los procedimientos son una serie de sentencias agrupadas en un **bloque** que es el **ámbito (scope)** en el que una variable es visible. Hoy en día los procedimientos en general han evolucionado a **funciones** (o **métodos** en OOP).

### Programación orientada a objetos (OOP)

Se trata de un paradigma basado en el concepto de "objectos" que pueden contener datos (**campos (fields)**) y código (**métodos**) y que interactúan entre ellos.
Normalmente los métodos están encapsulados en el objeto junto con sus campos y son los que permiten acceder y modificar sus campos.

El primer lenguaje orientado a objetos es Simula (1967) y Smalltalk (1972) el que más desarrolla la teoría de la OOP.

La mayor parte de los lenguajes más populares (**C++, Java, C#, Python, JavaScript, Ruby, Perl, R, PHP, Visual Basic.NET**...) son multiparadigma pero implementan OOP (a menudo como parte central).

Un objeto se puede describir como una colección de posiciones de memoria junto con todas las operaciones que pueden cambiar los valores de dichas posiciones. Un ejemplo muy básico de objeto es una variable con operaciones de asignación de valor y de recogida de su valor.

#### Programación basada en clases

La programación basada en clases es el modelo más popular y desarrollado de OOP. Los objetos son siempre instancias de clases; la clase es el tipo del objeto, de forma análoga a como una variable tiene un determinado tipo. La clase es una definición, un plano, que define la estructura y comportamiento del objeto. Cada clase representa un tipo con un estado (definido por unos campos) y operaciones (métodos) que pueden invocar desde los objetos (instancias) de la clase.



El uso de **herencia** entre clases (unas clases pueden heredar campos y métodos de otras) permite **extender** clases, creando **jerarquías de clases**, y **polimorfismo**, que permite manipular un conjunto de objetos de distinto tipo como algo uniforme sujeto a ciertas restricciones.

Destacan como lenguajes basados en clases **C++ o especialmente Java**.

#### Programación basada en prototipos

La Programación basada en prototipos es un tipo de **OOP** en el cual la reutilización de comportamiento (**herencia**) se desarrolla mediante la reutilización de objetos que sirven como prototipos.

En lugar de definir clases como tipo e instanciar estas clases en objetos, directamente se trabaja con objetos que pueden ser clonados y extendidos. **Casi todos los lenguajes basados en prototipos son interpretados y tienen tipado dinámico**.

El primer lenguaje orientado a prototipos fue **Self** a mediados de los 80. El más destacado es **JavaScript** (aunque también permite definir clases).

## Programación declarativa

En los paradigmas imperativos, el énfasis se pone en el "cómo" (las estructuras de control). Los programas consisten en una serie de ordenes, instrucciones o sentencias. Por contraposición, en los declarativos, el objetivo es describir el problema de forma detallada, declarando propiedades y reglas que deben cumplirse, en lugar de instrucciones. La solución es obtenida mediante mecanismos internos de control (inferencia), sin especificar exactamente cómo encontrarla (tan solo se le indica al sistema qué es lo que se desea obtener o qué es lo que se está buscando).

Entre los elementos que forman parte de este tipo de lenguajes, contaremos con herramientas para describir hechos y reglas, con las que podemos construir una base de conocimientos. Además contaremos con un sistema de inferencia que permite extraer conocimiento a partir de los elementos de representación de un problema.

Como no se describen los pasos a realizar, la programación declarativa permite delegar una mayor optimización al proceso de traducción a código máquina; el traductor podrá elegir el mejor algoritmo y/o paralelizar tareas. Un buen ejemplo sería el planificador de consultas (**Query planner**) de SQL.

Los lenguajes de propósito específico (**DSLs**) como SQL o lenguajes de marcas como XML o HTML se podrían considerar declarativos.

### Programación funcional

Surge paralelamente a la imperativa, con el desarrollo de **LISP** en 1958, primer lenguaje funcional de la historia, enfocado al área de la **inteligencia artificial**. Los lenguajes funcionales están basado en el concepto matemático de función.
En los lenguajes funcionales, los programas son **expresiones** que pueden ser definidas como funciones y pueden recibir parámetros. La evaluación de un programa consiste entonces en evaluar dichas expresiones en base a unos parámetros de entrada. Esto es similar a cómo se comporta una hoja de cálculo.
Además de LISP y sus dialectos más modernos como **Scheme** o **Clojure**, otros lenguajes destacados que implementan este paradigma serían **Haskell**, Miranda o **CAML**.

Durante la última década, algunos elementos de programación funcional han sido incorporados a lenguajes imperativos, como es el caso de las **funciones Lambda** incorporadas a Java en su versión 8.

En la programación funcional, las funciones son tratadas como entidades de primer nivel (**first-class citizen**), igual que cualquier objeto en OOP. Estos significa que **las funciones pueden ser pasadas como argumentos a otras funciones, devueltas como valores o asignadas a variables**.

En la programación funcional, las funciones no deben modificar **estados** (variables o objetos). Las modificaciones en estado son lo que se llama efectos secundarios (**side effects**).

<!-- TODO!!!: Programación funcional, su auge en la última década y su integración en lenguajes tradicionalmente imperativos (destacando su introducción en JAVA 8)-->
<!-- TODO: Efectos secundarios (side effects) y estado en programación imperativa. -->

### Programación lógica

Es un paradigma que aplica el conocimiento proveniente del campo de la lógica matemática al desarrollo de programas. Este paradigma ha sido utilizado sobre todo en el campo de la inteligencia artificial tradicional. El programador define una serie de reglas y hechos, y posteriormente se le pueden plantear al sistema una serie de consultas que resolverá en base a las reglas y hechos proporcionados. En este paradigma destaca el lenguaje **Prolog**.

## Programación concurrente

Es una forma de diseño de programas en la cual estos se construyen como colecciones de **procesos** o **hilos (threads)** que se ejecutan concurrentemente y que interactúan entre ellos. La programación concurrente surge de forma natural en determinadas aplicaciones como aquellas que tienen **interfaz de usuario (UI)**. En aplicaciones no concurrentes, cuando la aplicación está realizando una tarea pesada no es posible interactuar con su interfaz de usuario dado que la aplicación está ocupada haciendo otras cosas. Por eso las aplicaciones con interfaz de usuario suelen ser concurrentes: al menos hay un hilo encargado de recoger la interacción del usuario con la misma, mientras que puede haber otros hilos que estén realizando otras acciones dentro del mismo programa.
Muchos lenguajes incluyen características de programación concurrente. Así, **Java es un lenguaje concurrente orientado a objetos** y Haskell un lenguaje funcional que también soporta concurrencia.

## Programación dirigida por eventos (Event-driven)

La programación dirigida por eventos es un paradigma de programación en el que el flujo de ejecución de los programas va determinado por los sucesos que ocurran en el sistema, definidos habitualmente por acciones del usuario. Un ejemplo sería los eventos que desencadenan los usuarios mediante la interacción con los componentes de las librerías gráficas **Java FX** y **Java Swing**.

## Programación reactiva

Tras la publicación del **Reactive Manifesto** en 2014, se ha ido volviendo muy popular la idea de la programación reactiva. Se trata de una programación orientada a los datos (cambios en datos desencadenan la ejecución de subrutinas) a diferencia de la programación basada en eventos, que es orientada a procesos. Su idea fundamental es que los eventos son datos y los datos son eventos.
