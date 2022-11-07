# Traductores o procesadores de lenguajes

Como ya se introdujo, con la aparición de los lenguajes de alto nivel se hace necesario el uso de traductores que los conviertan a un lenguaje entendible por la máquina.
Un traductor es cualquier *software* que convierte un código fuente escrito en un lenguaje de alto nivel en otro código que está escrito en un lenguaje objeto, que podría ser típicamente el lenguaje máquina o un lenguaje ensamblador, pero también otro lenguaje de alto nivel.

Un traductor podría ser el **ensamblador**, que convierte **código ensamblador** en código máquina.

## Compiladores

Con la aparición de los lenguajes de alto nivel, aparece el concepto de compilador, que es el programa que convierte el **código fuente** (*source code*) en código máquina ejecutable. El código en alto nivel puede utilizarse en varias máquinas, pero **debe ser compilado en cada una con el compilador adecuado para convertirlo al conjunto de instrucciones de la CPU y Sistema operativo correspondiente**.

Cuando un programa se compone de varios ficheros (normalmente), cabe diferenciar entre **código objeto**: el de cada fichero compilado; y **código ejecutable**: el resultante de no solo compilar sino enlazar los ficheros objeto para que el código pueda llamar a subrutinas que están en otros ficheros. Esta tarea la realiza el **enlazador** o linker. Además, el compilador realiza tareas de optimización para que el código ejecutable sea más rápido.

Ejemplos de lenguajes compilados serían C o C++.

Se habla de **cross-compilar** cuando se produce código fuente para un sistema distinto de aquel en el que se ejecuta el compilador (otro hardware o sistema operativo).

### Fases de compilación

El proceso de compilación se compone de las siguientes fases:

1. Análisis o frontend  
   1. Análisis léxico: separación en palabras clave (class, public, int...)
   2. Análisis sintáctico: comprueba que el orden en que se combinan esas palabras se adecúen a las reglas del lenguaje de programación.
   3. Análisis semántico: interpreta el significado de operadores, operandos, variables y demás símbolos para generar el código intermedio.
2. Síntesis o backend
   1. Generación del código máquina
   2. Optimización
   3. Enlazador y generación de código objeto.

## Intérpretes

Son programas que analizan y ejecutan una a una las instrucciones que se encuentran en un código fuente. Por tanto coexisten en la memoria con el programa fuente, de modo que el proceso de traducción se realiza en **tiempo de ejecución (*runtime*)**.

Un compilador en general es más difícil de programar que un interprete, de modo que los programas interpretados son en general **más portables pero presentan un peor rendimiento por tener que realizar el proceso de interpretación en tiempo de ejecución**.

Los lenguajes interpretados facilitan el desarrollo y depuración ya que el tiempo total de traducir el código y ejecutarlo es menor que compilando, pero si lo importante es el tiempo final de ejecución, un programa compilado es, en general, más rápido que uno interpretado.

Los lenguajes interpretados reducen la carga para el programador y aumentan la que recae en el interprete. En general los lenguajes interpretados sirven para trabajar con mayor nivel de abstracción y suelen tener **tipado dinámico**.

Algunos ejemplos serían **Bash**, muchos **LISP** o las primeras versiones de **JavaScript**.

En lenguajes interpretados no existe código objeto, ni binario. Solo código fuente.

Hoy en día, existen pocos interpretes puros, ya que se utilizan estrategias mixtas para llegar a las ventajas de ambos sistemas.

### Lenguajes de scripting

A menudo se utiliza como sinónimo de interpretado, pero "script" tiene la connotación de ser programas cortos de propósito específico (**DSL**) que permiten manipular, personalizar y automatizar funcionalidades de un sistema ya existente.

Por ejemplo, con **Bash** se puede hacer un script que cambie el nombre de todos los ficheros en un directorio siguiendo un patrón.

Otro ejemplo: **JavaScript** en sus inicios era un lenguaje que permitía hacer pequeñas tareas dentro de una página web (aunque hoy en día es un lenguaje con muchos más usos).

**Python**, por su parte, es un lenguaje muy utilizado en el mundo de **Machine Learning** para ejecutar series de tareas, a menudo haciendo uso de **librerías precompiladas en C**.

## Transpiladores

Los transpiladores son traductores que convierten un lenguaje de alto nivel a otro lenguaje también de alto nivel. Por ejemplo, **Kotlin** permite ser compilado a la [**JVM**](#java-virtual-machine-jvm) (por ejemplo para aplicaciones Android) pero también ser transpilado a JavaScript para realizar páginas web.

## Lenguajes de bytecode

En algunos casos, las dos operaciones  recién citadas se han separado por completo, de modo que se tiene un **compilador** que traduce el código a un código intermedio, comúnmente denominado bytecode, y un **intérprete de bytecode** (en general llamado **máquina virtual**, dado que es análogo a un ordenador).

Al igual que los lenguajes interpretados, presentan la **ventaja de la portabilidad**: el mismo **código binario** puede ser ejecutado en diferentes plataformas y arquitecturas. Sin embargo, como el bytecode es en general menos abstracto, más compacto y más orientado a la máquina que un programa pensado para su modificación por humanos, su rendimiento suele ser mejor que el de los lenguajes interpretados.

### Java Virtual Machine (JVM)

En este caso, la ***Java Virtual Machine* (JVM)** es la encargada de traducir bytecode Java, generado por el compilador de Java a partir de un código fuente, a instrucciones en código máquina para la arquitectura hardware sobre la que esté corriendo la MV. En este caso, la JVM se ejecuta como un proceso dentro de un SO. Su objetivo es proporcionar un **entorno de ejecución independiente de la plataforma y del sistema operativo**, que oculte los detalles de la arquitectura y permita que un programa se ejecute siempre de la misma forma sobre cualquier arquitectura y SO.

*Write Once, Run Everywhere* (escribe una vez, ejecuta en cualquier lugar) fue un eslogan creado para ejemplificar los beneficios de Java como **lenguaje multiplataforma (cross-platform)**.

## Compilación Just-In-Time (JIT)

La compilación dinámica o JIT es una técnica para mejorar el rendimiento de programas interpretados. 
Es una estrategia intermedia donde el código se compila durante la ejecución del programa en lugar de antes de ella. Esto permite optimizar el programa más durante su ejecución en lugar de simplemente hacer una interpretación directa.

Por contraposición con el concepto de JIT, la compilación tradicional a código máquina es llamada **ahead-of-time compilation (AOT)**.
Simplificando, la compilación JIT busca combinar la velocidad de ejecución del código compilado con la flexibilidad de la interpretación.

Hoy en día, la **JVM** utiliza un compilador JIT para compilar el bytecode en **código máquina nativo** antes de su ejecución. Del mismo modo, destaca el motor V8 de Google que incorpora un compilador JIT para JavaScript.

## Ejemplos prácticos

[Programa simple en C (compilado), Python (interpretado) y Java (JDK)](https://www.youtube.com/watch?v=qmb6PZLs1Hk)  
- [Descarga MinGW (compilador de C para Windows](https://osdn.net/projects/mingw/downloads/68260/mingw-get-setup.exe/))
