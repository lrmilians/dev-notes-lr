# Apuntes de Typescript

## 🔵 Typescript #1 – ¿Qué es y por qué usarlo?

JavaScript con superpoderes. Añade tipado estático, herramientas de desarrollo más sólidas y detección temprana de errores… pero al final se compila a JavaScript puro, el que entienden todos los navegadores.

🔑 ¿Por qué deberías usarlo?

🛡️ Menos errores en producción → El compilador detecta fallos antes de que el código llegue a ejecutarse.

📖 Mejor documentación implícita → Los tipos funcionan como contrato entre devs, el código se entiende más rápido.

🚀 Productividad en equipo → Autocompletado, refactors seguros y tooling más inteligente.

🌍 Ecosistema → TypeScript ya es estándar en proyectos grandes de React, Angular, Node.js, etc.

En resumen, escribir menos bugs, entender mejor el código y trabajar más cómodo en equipo.

Y lo mejor, puedes adoptarlo poco a poco en cualquier proyecto JS.

📌 En el siguiente post veremos cómo configurar un proyecto con TypeScript desde cero.

---

## 🔵 TypeScript #2 – Instalación y primeros pasos

Ya sabemos qué es TypeScript y por qué usarlo.
Ahora toca ponerlo en marcha

🔧 Instalación

Con un único comando instalas el compilador de TypeScript
Esto añade el comando tsc (TypeScript Compiler) a tu sistema para compilar archivos .ts a .js.

📂 Primer archivo

1️⃣ Crea un archivo hello.ts.
2️⃣ Compílalo con tsc.
3️⃣ Ejecuta el resultado con Node.

💡 Lo interesante

Si intentas pasar un número donde esperaba un string, TypeScript avisa antes de ejecutar

En resumen, con solo instalarlo ya puedes ver el valor de los tipos en acción.

📌 En el siguiente post configuraremos tsconfig.json, el corazón de cualquier proyecto con TypeScript.

![Instalación](../../img/typescript/ts-01.jpg)

---

## 🔵 TypeScript #3 – tsconfig.json (Parte 1): lo esencial

Cuando un proyecto crece, compilar archivos sueltos con tsc no es suficiente.
Aquí entra en juego tsconfig.json, el archivo que define cómo funciona TypeScript en tu proyecto.

🔑 ¿Qué es?

Es un archivo de configuración en formato JSON que indica al compilador:

✅ Dónde buscar archivos (include, exclude).
✅ Cómo compilarlos (compilerOptions).
✅ Qué nivel de comprobaciones aplicar. 

✨ Lo esencial:

target → La versión de JS resultante (ej: ES5, ES6…).
module → El sistema de módulos (commonjs, esnext, etc.).
strict → Activa todas las comprobaciones estrictas (¡muy recomendable!).

En resumen, tsconfig.json es el cerebro de TypeScript, controla desde el nivel de seguridad hasta la compatibilidad con distintos entornos.

📌 En el siguiente post veremos más opciones útiles de tsconfig.json para proyectos reales.

![tsconfig](../../img/typescript/ts-02.jpg)

---

## 🔵 TypeScript #4 – tsconfig.json (Parte 2): calidad y DX

En el post anterior vimos lo básico de tsconfig.json.
Ahora vamos a llevarlo un paso más allá para mejorar la calidad de código y la experiencia de desarrollo (DX). 

🔧 Opciones clave

🔷 strictNullChecks
Evita usar null o undefined sin control. 

🔷 noImplicitAny
Impide variables sin tipo explícito. Te obliga a ser claro. 

🔷 noUnusedLocals / noUnusedParameters
Detecta variables o parámetros que no se usan → código más limpio.

🔷 noImplicitReturns
Te avisa si una función no devuelve en todos los caminos posibles.

🔷 esModuleInterop
Facilita importar librerías con import x from "lib" aunque no usen ESModules. 

✨ En resumen, estas opciones ayudan a:

✅ Encontrar errores antes.
✅ Mantener un código más claro.
✅ Mejorar la autocompletación y refactors.

📌 En el siguiente post veremos opciones para integrar TypeScript en proyectos reales y trabajar en equipo.

![ts-03](../../img/typescript/ts-03.jpg)

---

## 🔵 TypeScript #5 – De TS a JS: qué emite y cómo integrarlo

TypeScript no se ejecuta directamente.
Siempre se transpila a JavaScript, el único lenguaje que entienden los navegadores y Node.

🔑 ¿Qué emite el compilador?

🔷 Archivos .js listos para producción.
🔷 Archivos .d.ts (si los activas) → solo tipos, útiles para compartir librerías.
🔷 Mapas de código (.map) → para debuggear en el navegador como si ejecutaras TS.

⚙️ Integración según proyecto

🔷 Node.js → compilas .ts a .js y ejecutas con node.
🔷 React → la mayoría de toolchains (Vite, CRA, Next.js) ya soportan TS de serie.
🔷 Librerías → exportas tipos con .d.ts para que otros devs tengan autocompletado.

‼️ Lo importante

TypeScript es una capa de desarrollo.
En producción, siempre acabas sirviendo JavaScript puro y optimizado.

En resumen, TS no sustituye a JS, lo potencia en el desarrollo y lo convierte en un código más seguro y mantenible.

📌 En el siguiente post empezaremos a explorar los tipos básicos en TypeScript.

![ts-05](../../img/typescript/ts-05.jpg)

---

## 🔵 TypeScript #6 – Tipos primitivos en TS

En JavaScript todo tiene un tipo, pero no siempre está claro.
Con TypeScript podemos definir explícitamente los tipos primitivos y evitar sorpresas.

🔑 Principales tipos primitivos

🔷 string → cadenas de texto.
🔷 number → enteros y decimales.
🔷 boolean → valores true o false.
🔷 null y undefined → ausencia de valor.
🔷 any → desactiva el tipado (no recomendable salvo casos muy concretos).

💡 Con estos tipos, TypeScript puede detectar usos incorrectos antes de ejecutar.

En resumen, los tipos primitivos son la base del tipado estático, y nos ayudan a que el código sea más predecible y robusto.

📌 En el siguiente post veremos las diferencias entre any, unknown y never y cuando usarlos.

![ts-06](../../img/typescript/ts-06.jpg)

---

## 🔵 TypeScript #7 – any vs unknown vs never

En TypeScript existen algunos tipos especiales que marcan la diferencia en cómo manejamos la seguridad del código.

🔑 Diferencias clave

🔷 any
Desactiva el tipado. Puedes asignarle cualquier cosa y usarlo como quieras → peligro de perder la seguridad.

🔷 unknown
También acepta cualquier valor, pero exige validar o hacer un type check antes de usarlo. Mucho más seguro que any.

🔷 never
Representa un valor que nunca ocurre.
Ejemplo: funciones que siempre lanzan error o que nunca terminan.

✨ En resumen:

✅ Usa any solo si no hay alternativa.
✅ Prefiere unknown cuando el tipo no está claro, pero necesitas comprobarlo.
✅ never aparece en casos muy concretos para indicar que algo es imposible.

📌 En el siguiente post veremos inferencia de tipos en TypeScript.

![ts-07](../../img/typescript/ts-07.jpg)

---

## 🔵 TypeScript #8 – Inferencia de tipos

Una de las ventajas de TypeScript es que no siempre tienes que declarar los tipos explícitamente.

El compilador es capaz de inferirlos automáticamente a partir del valor inicial.

🔑 ¿Qué significa esto?
Si declaras una variable con un valor, TypeScript deduce su tipo y lo mantiene.

✨ Beneficios:

✅ Menos código repetitivo.
✅ Autocompletado inteligente sin escribir los tipos a mano.
✅ Seguridad garantizada: el compilador no permitirá cambiar el tipo más adelante.

En resumen, la inferencia hace el código más limpio sin perder tipado.

📌 En el siguiente post veremos objetos tipados en Typescript.

![ts-08](../../img/typescript/ts-08.jpg)

---

## 🔵 TypeScript #9 – Objetos tipados

En JavaScript los objetos son muy flexibles… a veces demasiado 😅.
Con TypeScript podemos definir la forma exacta que debe tener un objeto, asegurándonos de que siempre cumpla un contrato.

🔑 ¿Por qué tipar objetos?

🔷 Define qué propiedades son obligatorias.
🔷 Evita errores por nombres mal escritos.
🔷 Facilita el autocompletado y la refactorización.

En resumen, tipar objetos nos da claridad y seguridad al trabajar con estructuras de datos.

📌 En el siguiente post veremos tipados de arrays en Typescript.

![ts-09](../../img/typescript/ts-09.jpg)

---

## 🔵 TypeScript #10 – Arrays y Tuplas

En TypeScript no solo podemos tipar variables u objetos, también colecciones de datos.
Esto nos permite trabajar con más precisión y seguridad.

🔑 Arrays
Un array debe contener siempre elementos del mismo tipo.

🔑 Tuplas
Son como arrays, pero con longitud fija y tipos específicos en cada posición.

✨ Beneficios:

✅ Evitan mezclar tipos en un array sin querer.
✅ Con las tuplas, cada posición tiene un propósito claro.

En resumen, arrays y tuplas nos ayudan a estructurar colecciones de datos con reglas claras.

📌 En el siguiente post veremos las funciones tipadas en Typescript.

![ts-10](../../img/typescript/ts-10.jpg)

---

## 🔵 TypeScript #11 – Funciones tipadas

En JavaScript podemos crear funciones sin pensar en los tipos… y eso a veces pasa factura 😅.
Con TypeScript podemos tipar tanto los parámetros como el valor de retorno, lo que hace que el código sea más predecible y seguro.

🔑 ¿Por qué tipar funciones?

✅ Dejas claro qué recibe y qué devuelve.
✅ Mejor autocompletado y refactors sin miedo.
✅ Evitas errores por valores inesperados.

En resumen, las funciones tipadas ayudan a definir contratos claros en tu código.

📌 En el siguiente post veremos cómo trabajar con parámetros opcionales y valores por defecto en funciones.

![ts-11](../../img/typescript/ts-11.jpg)

---

## 🔵 TypeScript #12 – Parámetros opcionales y valores por defecto

No todas las funciones necesitan todos los parámetros siempre.
Con TypeScript podemos definir parámetros opcionales y valores por defecto para dar flexibilidad sin perder seguridad.

🔑 Parámetros opcionales (?)

🔷 El parámetro puede estar o no estar presente.
🔷 TypeScript te obliga a comprobarlo antes de usarlo.

🔑 Valores por defecto

🔷 Si no se pasa un argumento, se usa el valor definido por defecto.
🔷 Garantiza que siempre haya un valor válido.

En resumen, puedes diseñar funciones más flexibles sin comprometer la claridad ni el tipado.

📌 En el siguiente post veremos el concepto de alias en los tipos

![ts-12](../../img/typescript/ts-12.jpg)

---

## 🔵 TypeScript #13 – Alias de tipos

Cuando un objeto o estructura se repite mucho, escribir el tipo completo una y otra vez puede ser pesado.

Para eso existen los type aliases, un nombre que representa un tipo.

🔑 ¿Por qué usar alias de tipos?

🔷 Reutilizas definiciones en varios sitios.
🔷 Mantienes el código más limpio y legible.
🔷 Facilitas cambios: actualizas el alias y se refleja en todas partes.

En resumen, los alias permiten dar un nombre a un tipo y usarlo como si fuera propio.

📌 En el siguiente post hablaremos sobre inmutabilidad.

![ts-13](../../img/typescript/ts-13.jpg)

---

## 🔵 TypeScript #14 – Const assertions (as const)

A veces necesitamos que TypeScript trate un valor como completamente inmutable y literal.
Para eso existe as const: una forma de decirle al compilador “esto no va a cambiar”.

🔑 ¿Qué hace as const?

🔷 Convierte un valor en readonly.
🔷 Cambia el tipo a su valor literal exacto (ej: "red" en vez de string).
🔷 Muy útil en arrays y objetos que definen configuraciones o constantes.

En resumen, as const ayuda a proteger valores y a trabajar con mayor precisión en enums, configs y props.

📌 En el siguiente post veremos un ejercicio práctico de tipos básicos.

![ts-14](../../img/typescript/ts-14.jpg)

---

## 🔵 TypeScript #15 – Ejercicios prácticos de tipos básicos

Ya hemos visto los tipos primitivos, objetos, arrays, tuplas y funciones.
Ahora toca ponerlo en práctica con pequeños ejercicios.

🔑 ¿Por qué hacer ejercicios?

🔷 Refuerzas la teoría con práctica real.
🔷 Te acostumbras a los errores del compilador.
🔷 Aprendes a pensar en términos de contratos de tipos.

Os propongo los siguientes:

1️⃣ Declara una variable de tipo string y otra de tipo number. 
2️⃣ Crea una función que reciba un boolean y devuelva un string. 
3️⃣ Define un objeto Product con nombre (string) y precio (number). 
4️⃣ Haz un array de números y calcula su suma. 
5️⃣ Declara una tupla con nombre (string) y edad (number). 

📣 En el resumen de esta semana os pondré la propuesta de soluciones.

Practicar es la mejor forma de interiorizar el tipado estático.

📌 En el siguiente post veremos qué son las interfaces y para qué sirven.

![ts-15](../../img/typescript/ts-15.jpg)

---

## 🔵 TypeScript #16 – Interfaces: definición y extensiones

Las interfaces son una forma de definir la estructura de un objeto y garantizar que cumpla un contrato.
Son muy similares a los alias, pero con algunas ventajas cuando se trata de extender y reutilizar.

🔑 ¿Por qué usar interfaces?

🔷 Definen la forma exacta de un objeto.
🔷 Se pueden extender para crear variantes sin duplicar código.
🔷 Mejoran el autocompletado y la legibilidad en proyectos grandes.

En resumen, las interfaces ayudan a modelar datos y mantener el código más organizado.

📌 En el siguiente post compararemos type vs interface para ver cuándo elegir cada uno.

![ts-16.1](../../img/typescript/ts-16.1.jpg)
![ts-16.2](../../img/typescript/ts-16.2.jpg)

---

## 🔵 TypeScript #17 – Types vs Interfaces

En TypeScript tenemos dos formas muy parecidas de definir la forma de los datos: type e interface. A primera vista parecen lo mismo, pero tienen diferencias importantes.

🔑 ¿Qué tienen en común?

🔷 Sirven para describir objetos.
🔷 Mejoran autocompletado y legibilidad.
🔷 Se pueden reutilizar en varios sitios.

🔑 ¿En qué se diferencian?

🔷 interface → pensada para describir objetos y permite extender otras interfaces.
🔷 type → más flexible: puede definir uniones (|), tipos primitivos, funciones, etc.
🔷 conflictos: las interfaces pueden mergearse si se declaran varias veces, los types no.

✨ Regla práctica:

✅ Usa interface si defines la forma de un objeto que puede crecer o extenderse.
✅ Usa type si necesitas más flexibilidad o definir uniones de tipos.

📌 En el siguiente post veremos tipos literales y union types.

![ts-17](../../img/typescript/ts-17.jpg)

---

## 🔵 TypeScript #18 – Uniones e intersecciones

En TypeScript podemos combinar tipos para hacer el código más flexible o más estricto.
Ahí entran en juego las uniones (|) y las intersecciones (&).

🔑 Union types (|)

🔷 Permiten que algo sea de uno u otro tipo.
🔷 Muy útiles cuando una variable puede tener varios formatos válidos.

🔑 Intersection types (&)

🔷 Combinan tipos para crear uno que cumpla todos a la vez.
🔷 Perfecto para extender entidades con nuevas propiedades.

En resumen:

👉 Union = uno u otro.
👉 Intersection = todo junto.

📌 En el siguiente post veremos tipos literales y cómo se usan con uniones.

![ts-18](../../img/typescript/ts-18.jpg)

---

## 🔵 TypeScript #19 – Type Narrowing

Cuando usamos uniones, a veces necesitamos que TypeScript entienda qué tipo concreto tiene una variable en cada momento. Eso es lo que se conoce como Type Narrowing (estrechar el tipo).

🔑 ¿Cómo funciona?

El compilador analiza el flujo del programa y reduce el tipo según las comprobaciones que hagas.

🔑 Formas comunes de narrowing:

🔷 typeof → para tipos primitivos.
🔷 in → para comprobar si una propiedad existe.
🔷 instanceof → para validar instancias de clases.
🔷 Chequeos personalizados con type predicates.

En resumen, narrowing permite que las uniones sean seguras y prácticas de usar.

📌 En el siguiente post veremos tipos literales y cómo aprovecharlos con uniones.

![ts-19](../../img/typescript/ts-19.jpg)

---

## 🔵 TypeScript #20 – Enums vs Literal Types

En TypeScript podemos restringir valores a un conjunto específico de opciones.
Para eso existen dos enfoques: Enums y Literal Types.

🔑 Enums

🔷 Definen un conjunto de valores con nombre.
🔷 Pueden ser numéricos o de strings.
🔷 Son más verbosos, pero muy claros en grandes proyectos.

🔑 Literal Types + Uniones

🔷 Usan valores literales unidos con |.
🔷 Más ligeros, sin generar código extra.
🔷 Ideales cuando las opciones son pocas.

✨ Regla práctica:

✅ Usa Literal Types para casos simples y ligeros.
✅ Usa Enums si necesitas un set reutilizable y más expresivo.

📌 En el siguiente post veremos propiedades opcionales y nullables.

![ts-20](../../img/typescript/ts-20.jpg)

---

## 🔵 TypeScript #21 – Index Signatures y tipos dinámicos

En JavaScript es común tener objetos con claves dinámicas, como un diccionario o un mapa simple.
Con TypeScript podemos tiparlos usando index signatures.

🔑 ¿Qué es una index signature?

🔷 Definición: forma de indicar el tipo de las claves de un objeto.
🔷 Uso: permite que las claves sean dinámicas (string, number, symbol).
🔷 Ventaja: garantiza que todos los valores cumplan un contrato.

En resumen, con index signatures podemos crear objetos flexibles pero seguros.

📌 En el siguiente post veremos cómo usar keyof y typeof en tipos.

![ts-21](../../img/typescript/ts-21.jpg)

---

## 🔵 TypeScript #22 – keyof y typeof en tipos

TypeScript nos permite trabajar con los tipos de forma dinámica, reutilizando estructuras y asegurando que las referencias sean correctas.
Dos herramientas clave para esto son keyof y typeof.

🔑 ¿Qué es keyof?

🔷 Definición: obtiene las claves de un tipo como unión de strings.
🔷 Uso: útil para limitar valores a las propiedades de un objeto.
🔷 Ventaja: evita errores de propiedades mal escritas.

🔑 ¿Qué es typeof?

🔷 Definición: obtiene el tipo a partir de un valor ya declarado.
🔷 Uso: permite reutilizar tipos sin definirlos manualmente.
🔷 Ventaja: mantiene sincronizados valores y tipos.

En resumen, keyof y typeof nos ayudan a hacer metaprogramación con tipos, generando estructuras más consistentes.

📌 En el siguiente post veremos inferencia avanzada de tipos.

![ts-22](../../img/typescript/ts-22.jpg)

---

## 🔵 TypeScript #23 – Inferencia avanzada de tipos

Ya vimos que TypeScript puede deducir tipos automáticamente sin que tengamos que escribirlos. En casos más complejos, entra en juego la inferencia avanzada, donde TS analiza valores, funciones y objetos para determinar sus tipos.

🔑 ¿Qué es la inferencia avanzada?

🔷 Definición: capacidad del compilador para deducir el tipo sin declaración explícita.
🔷 Uso: variables, funciones, retornos y estructuras complejas.
🔷 Ventaja: menos código repetitivo y tipado más expresivo.

En resumen, la inferencia avanzada hace que el código sea más limpio y seguro, porque TS entiende el contexto.

📌 En el siguiente post veremos Type Compatibility y Structural Typing.

![ts-23](../../img/typescript/ts-23.jpg)

---

## 🔵 TypeScript #24 – Type Compatibility & Structural Typing

TypeScript no compara tipos por su nombre, sino por su estructura.
Esto se llama Structural Typing y es la base del sistema de tipos en TS.

🔑 ¿Qué es la compatibilidad de tipos?

🔷 Definición: dos tipos son compatibles si sus estructuras coinciden.
🔷 Uso: permite asignar objetos distintos siempre que tengan las mismas propiedades requeridas.
🔷 Ventaja: más flexibilidad y menos código repetitivo.

📌 En el siguiente post veremos ejercicios prácticos de tipado intermedio para aplicar todo lo aprendido.

![ts-24](../../img/typescript/ts-24.jpg)

---

## 🔵 TypeScript #25 – Ejercicios prácticos de tipado intermedio

Hemos aprendido sobre index signatures, keyof/typeof, inferencia avanzada y compatibilidad estructural. Ahora toca ponerlo en práctica con algunos ejercicios.

🔑 ¿Qué conseguimos practicando?

🔷 Definición: afianzar los conceptos de tipado intermedio.
🔷 Uso: resolver casos más realistas con objetos y funciones.
🔷 Ventaja: consolidar lo aprendido y detectar dudas antes de pasar a generics.

Os propongo los siguientes:

1️⃣ Declara un objeto Dictionary que permita cualquier clave string con valores number. 
2️⃣ Crea una función que acepte solo claves válidas de User. 
3️⃣ Reutiliza el tipo a partir de una constante. 
4️⃣ Asigna un objeto con más propiedades a una interfaz más simple. 

📣 En el resumen de esta semana os pondré la propuesta de soluciones.

📌 En el siguiente post comenzaremos con Generics en TypeScript 🚀.

![ts-25](../../img/typescript/ts-15.jpg)

---

## 🔵 TypeScript #26 – Introducción a Generics

Hasta ahora hemos trabajado con tipos estáticos y estructuras definidas.
Pero, ¿qué pasa cuando queremos que una función, interfaz o clase funcione con distintos tipos sin perder seguridad?
Ahí entran en juego los Generics.

🔑 ¿Qué son los generics?

🔷 Definición: permiten crear componentes de código reutilizables que aceptan diferentes tipos como parámetros.
🔷 Uso: se escriben con <T> (o más letras si hay varios).
🔷 Ventaja: flexibilidad sin sacrificar el tipado estático.

En resumen, los generics son como variables para los tipos: nos permiten escribir código que se adapta a distintos escenarios sin duplicar.

📌 En el siguiente post veremos cómo usar Generics en funciones.

![ts-26](../../img/typescript/ts-26.jpg)

---

## 🔵 TypeScript #27 – Generics en funciones

Los generics brillan especialmente en funciones, porque permiten que sean reutilizables y seguras sin importar el tipo de dato que reciban.

🔑 ¿Qué aportan en funciones?

🔷 Definición: parametrizar los tipos de entrada y salida.
🔷 Uso: se añaden con <T> junto al nombre de la función.
🔷 Ventaja: evitan repetir la misma función para cada tipo.

En resumen, los generics en funciones nos dan flexibilidad con tipado fuerte.

📌 En el siguiente post veremos Generics en interfaces y clases.

![ts-27](../../img/typescript/ts-27.jpg)

---

## 🔵 TypeScript #28 – Generics en interfaces y clases

Los generics no solo se usan en funciones.
También podemos aplicarlos en interfaces y clases para crear estructuras reutilizables y tipadas sin duplicar código.

🔑 ¿Qué aportan en interfaces y clases?

🔷 Definición: parametrizar el tipo de datos en estructuras más grandes.
🔷 Uso: se declaran como <T> junto al nombre de la interface o clase.
🔷 Ventaja: reutilizar la misma lógica con distintos tipos.

En resumen, los generics permiten diseñar abstracciones potentes y flexibles.

📌 En el siguiente post veremos constraints en generics (extends).

![ts-28.1](../../img/typescript/ts-28.1.jpg)
![ts-28.2](../../img/typescript/ts-28.2.jpg)
![ts-28.3](../../img/typescript/ts-28.3.jpg)

---

## 🔵 TypeScript #29 – Constraints en Generics

Los generics son muy flexibles, pero a veces necesitamos limitarlos para que solo acepten ciertos tipos.
Para eso usamos los constraints con extends.

🔑 ¿Qué son los constraints?

🔷 Definición: una forma de restringir qué tipos puede aceptar un genérico.
🔷 Uso: T extends Tipo → el genérico debe cumplir esa condición.
🔷 Ventaja: más seguridad al definir funciones y estructuras.

En resumen, los constraints nos dan lo mejor de la flexibilidad con la seguridad del tipado.

📌 En el siguiente post veremos default generics para dar valores por defecto a los genéricos.

![ts-29](../../img/typescript/ts-29.jpg)

---

## 🔵 TypeScript #30 – Default Generics

Cuando usamos generics, a veces queremos que tengan un valor por defecto si no se especifica ninguno.
Esto es posible con los default generics usando =.

🔑 ¿Qué son los default generics?

🔷 Definición: permiten asignar un tipo por defecto a un genérico.
🔷 Uso: T = TipoPorDefecto.
🔷 Ventaja: simplifican el código y hacen las APIs más fáciles de usar.

En resumen, los default generics son como valores por defecto en funciones, pero para tipos.

📌 En el siguiente post veremos Utility Types comunes (Partial, Pick, Omit).

![ts-30](../../img/typescript/ts-30.jpg)

---

## 🔵 TypeScript #31 – Utility Types comunes (Partial, Pick, Omit)

TypeScript incluye una serie de utilidades que nos permiten transformar tipos existentes sin reescribirlos. Hoy veremos tres de las más usadas: Partial, Pick y Omit.

🔑 ¿Qué son los Utility Types comunes?

🔷 Definición: tipos genéricos que modifican otros tipos existentes.
🔷 Uso: se aplican sobre interfaces o type aliases.
🔷 Ventaja: reducen duplicación y mejoran la mantenibilidad.

En resumen, estos utilitarios te ayudan a crear versiones personalizadas de tus tipos con un esfuerzo mínimo.

📌 En el siguiente post veremos los Utility Types avanzados (Record, Extract, Exclude, ReturnType).

![ts-31](../../img/typescript/ts-31.jpg)

---

## 🔵 TypeScript #32 – Utility Types avanzados (Record, Extract, Exclude, ReturnType)

Después de ver los utility types más comunes, toca dar un paso más.
TypeScript incluye otros utilitarios que nos ayudan a crear, filtrar o derivar tipos de forma más potente.

🔑 ¿Qué son los Utility Types avanzados?

🔷 Definición: tipos genéricos que permiten generar nuevos tipos basados en otros.
🔷 Uso: combinan generics y metaprogramación.
🔷 Ventaja: ideales para modelos complejos o librerías tipadas.

En resumen, estos utilitarios te ayudan a transformar tipos dinámicamente con precisión.

📌 En el siguiente post veremos Template Literal Types, una de las features más creativas de TS.

![ts-32](../../img/typescript/ts-32.jpg)

---

## 🔵 TypeScript #33 – Template Literal Types
Construcción de tipos con strings

TypeScript no solo trabaja con tipos tradicionales: también puede crear nuevos tipos a partir de strings. Eso es lo que hacen los Template Literal Types, una de las features más potentes y creativas del lenguaje.

🔑 ¿Qué son los Template Literal Types?

🔷 Definición: permiten combinar string literals y union types para generar tipos dinámicos.
🔷 Uso: se construyen usando template strings (${}) dentro del tipo.
🔷 Ventaja: generan combinaciones de cadenas tipadas sin perder seguridad.

En resumen, esta feature te permite crear sistemas de nombres, rutas o etiquetas tipadas directamente desde el propio tipo.

📌 En el siguiente post veremos los Conditional Types, otra herramienta de metaprogramación avanzada.

![ts-33](../../img/typescript/ts-33.jpg)

---

## 🔵 TypeScript #34 – Tipos condicionales con extends ? :

Los Conditional Types permiten que un tipo dependa de otro.
Son como los if/else del sistema de tipos: si una condición se cumple, el tipo será uno; si no, será otro.

🔑 ¿Qué son los Conditional Types?

🔷 Definición: permiten definir un tipo basado en una condición entre tipos.
🔷 Uso: T extends U ? X : Y.
🔷 Ventaja: añaden lógica y flexibilidad al tipado avanzado.

En resumen, los conditional types son el equivalente tipado a un operador ternario dentro de TypeScript.

📌 En el siguiente post veremos ejercicios prácticos con generics y conditional types.

![ts-34](../../img/typescript/ts-34.jpg)

---

## 🔵 TypeScript #35 – Ejercicios con Generics

Ya conocemos los generics, los constraints, los defaults y los conditional types.
Ahora toca ponerlos a prueba 💪 con algunos ejercicios prácticos.

🔑 ¿Por qué practicar generics?

1. 🔷 Definición: ayudan a entender cómo los tipos fluyen en funciones y estructuras.
2. 🔷 Uso: permiten escribir código genérico reutilizable y seguro.
3. 🔷 Ventaja: son la base del tipado avanzado de librerías como React, Axios o React Query.

Os propongo los siguientes: 

1. Crea una función wrapInArray que reciba un valor de tipo T y lo devuelva dentro de un array. 
2. Define una función getId que acepte solo objetos con propiedad id. 
3. Crea una clase Box con tipo por defecto string. 
4. Haz un tipo IsArray<T> que devuelva "Sí" si T es array o "No" si no lo es. 
5. Crea un Repository<T> con método add() y getAll(), tipado genéricamente. 

📣 En el resumen de esta semana os pondré la propuesta de soluciones.

📌 En el siguiente post veremos algunos tips de de optimización.

![ts-35](../../img/typescript/ts-15.jpg)

---

## 🔵 TypeScript #36 – Tipado de librerías y dependencias externas

TypeScript brilla cuando todo está tipado, pero… ¿qué pasa con las librerías de terceros?
Muchas ya incluyen sus propios tipos, pero otras no. Hoy veremos cómo añadir, extender o crear tipos para dependencias externas.

🔑 ¿Cómo se tipan las librerías externas?

🔷 @types/ → Los paquetes de DefinitelyTyped proporcionan tipos oficiales.
🔷 declare module → Sirve para tipar librerías sin soporte o módulos propios.
🔷 Augmentation → Permite extender tipos ya existentes sin sobrescribirlos.

En resumen, el ecosistema de TypeScript te permite tipar casi cualquier cosa, incluso librerías que no nacieron pensando en TS.

📌 En el siguiente post veremos cómo tipar proyectos React, desde props hasta hooks personalizados.

![ts-36](../../img/typescript/ts-36.jpg)

---

## 🔵 TypeScript #37 – Tipos en React: Props

React y TypeScript hacen una dupla perfecta. El tipado de props permite detectar errores antes de renderizar y documentar el componente sin escribir una línea extra.

🔑 ¿Cómo tipar las props en React?

🔷 interface: ideal para definir estructuras claras y extensibles.
🔷 type: perfecto para props simples o cuando se usan uniones.
🔷 React.FC: facilita el tipado del componente completo, incluyendo children.

En resumen, tipar las props mejora la legibilidad, autocompletado y seguridad de tus componentes.

📌 En el siguiente post veremos cómo tipar hooks y estado en React.

![ts-37](../../img/typescript/ts-37.jpg)

---

## 🔵 TypeScript #38 – Tipos en React: Hooks y State

Uno de los puntos fuertes de TypeScript en React es el tipado de hooks y estado.
Permite detectar errores de uso antes de que lleguen al navegador y mejorar la DX con autocompletado y validación automática.

🔑 ¿Cómo tipar hooks y estado en React?

🔷 useState → se puede tipar de forma explícita o inferida.
🔷 useRef → requiere tipo explícito (especialmente para elementos DOM o valores mutables).
🔷 useEffect → no necesita tipado directo, pero puede beneficiarse del tipo de dependencias.
🔷 Custom hooks → usan generics para ser reutilizables y seguros.

En resumen, tipar los hooks garantiza consistencia, seguridad y mejor autocompletado.

📌 En el siguiente post veremos tipado en React Query, para manejar datos y errores de API con total control.

![ts-38](../../img/typescript/ts-38.jpg)

---

## 🔵 TypeScript #39 – Tipos en React Query

Cuando trabajamos con datos asíncronos, React Query nos facilita la vida.
Y con TypeScript, podemos tipar las respuestas, errores y variables para tener total seguridad en nuestras queries y mutations.

🔑 ¿Cómo tipar React Query?

🔷 useQuery: define los tipos de datos y errores esperados.
🔷 useMutation: tipa las variables de entrada y el resultado.
🔷 QueryFn y MutationFn: funciones fuertemente tipadas que garantizan consistencia.

En resumen, el tipado en React Query hace que trabajar con APIs sea más seguro y predecible.

📌 En el siguiente post veremos tipos en Axios y servicios, para llevar el tipado a la capa de red.

![ts-39.1](../../img/typescript/ts-39.1.jpg)
![ts-39.2](../../img/typescript/ts-39.2.jpg)
![ts-39.3](../../img/typescript/ts-39.3.jpg)

---

## 🔵 TypeScript #40 – Tipos en Axios y servicios

Una API tipada no solo evita errores: también mejora el autocompletado y la consistencia en todo el proyecto. Hoy veremos cómo tipar peticiones con Axios y crear servicios reutilizables en TypeScript.

🔑 ¿Cómo tipar servicios con Axios?

🔷 Response Data: usa genéricos (AxiosResponse<T>) para tipar la respuesta.
🔷 Request Body: define interfaces para el payload de entrada.
🔷 Servicios genéricos: centraliza llamadas a API con tipos reutilizables.

En resumen, el tipado en Axios convierte las peticiones HTTP en código predecible, mantenible y seguro.

📌 En el siguiente post veremos tipado en formularios y validaciones.

![ts-40.1](../../img/typescript/ts-40.1.jpg)
![ts-40.2](../../img/typescript/ts-40.2.jpg)

---

## 🔵 TypeScript #41 – Manejo de errores y tipado de excepciones

Los errores forman parte del flujo de cualquier aplicación. Con TypeScript, podemos tiparlos correctamente para detectar problemas antes de tiempo y manejarlos de forma más segura.

🔑 ¿Cómo tipar los errores en TypeScript?

🔷 unknown: el tipo más seguro para catch — evita asumir que el error es una instancia de Error.
🔷 instanceof Error: permite refinar y acceder a propiedades como message o cause.
🔷 Custom Errors: define tus propias clases de error para tener contexto y control.

En resumen, manejar errores con tipos explícitos mejora la resiliencia y depuración del código.

📌 En el siguiente post veremos cómo aplicar tipado en formularios y validaciones.

![ts-41](../../img/typescript/ts-41.jpg)

---

## 🔵 TypeScript #42 – Tipos en Formularios

Los formularios son una de las partes más delicadas de cualquier aplicación.
Con TypeScript, podemos tipar inputs, eventos y validaciones para evitar errores comunes y ganar confianza al manipular datos.

🔑 ¿Cómo tipar formularios en React?

🔷 FormEvent: para manejar el envío del formulario (onSubmit).
🔷 ChangeEvent: para inputs y selects controlados (onChange).
🔷 Validaciones: puedes combinar TypeScript con librerías como Zod o Yup para validar esquemas.

En resumen, tipar formularios te ayuda a controlar el flujo de datos y prevenir errores de tipo en tiempo real.

📌 En el siguiente post veremos cómo tipar eventos del DOM y manejadores genéricos en React.

![ts-42](../../img/typescript/ts-42.jpg)

---

## 🔵 TypeScript #43 – Tipos en eventos DOM

En React, los eventos del navegador se manejan a través de SyntheticEvent, una capa que unifica el comportamiento entre navegadores.
Tiparlos correctamente mejora la autocompletación y evita errores al acceder a propiedades del evento.

🔑 ¿Cómo tipar eventos en React?

🔷 SyntheticEvent: el tipo base para todos los eventos.
🔷 Eventos específicos: MouseEvent, KeyboardEvent, ChangeEvent, ClipboardEvent, etc.
🔷 Handlers tipados: también puedes usar React.MouseEventHandler<HTMLButtonElement> o similares.

En resumen, tipar los eventos del DOM te da seguridad y control total sobre la interacción del usuario.

📌 En el siguiente post veremos cómo tipar React Router, incluyendo params, loaders y rutas dinámicas.

![ts-43](../../img/typescript/ts-43.jpg)

---

## 🔵 TypeScript #44 – Tipos en React Router

React Router es una de las piezas centrales en cualquier SPA y con TypeScript podemos tipar rutas, parámetros, loaders y datos para tener una navegación totalmente segura.

🔑 ¿Cómo tipar React Router?

🔷 useParams: define el tipo esperado de los parámetros dinámicos.
🔷 useLoaderData: asocia tipos a los datos cargados por un loader.
🔷 RouteObject: puedes tipar tus rutas para mantener la estructura consistente.

En resumen, el tipado en React Router mejora la seguridad de la navegación y evita errores al acceder a parámetros o datos.

📌 En el siguiente post aplicaremos todo lo aprendido en un mini-proyecto completo.

![ts-44.1](../../img/typescript/ts-44.1.jpg)
![ts-44.2](../../img/typescript/ts-44.2.jpg)

---

## 🔵 TypeScript #45 – Mini-proyecto aplicado (JSONPlaceholder)

Cerramos el bloque práctico integrando componentes + hooks + React Query + Axios + formularios + rutas tipadas, usando la API pública de JSONPlaceholder https://lnkd.in/eycgSKC2

🔑 ¿Qué incluye este mini-proyecto?

🔷 Modelo tipado de User según JSONPlaceholder.
🔷 Servicios HTTP con Axios y genéricos.
🔷 React Query para getAll y create.
🔷 Formulario controlado con validación mínima.
🔷 Página de listado que se actualiza al crear.

En resumen, un flujo listado → alta → refresco totalmente tipado.
Os propongo la estructura de la imagen.

📣 En el resumen de esta semana os compartiré un repositorio con la solución propuesta.

📌 Próximo bloque: buenas prácticas y patrones con TypeScript.

![ts-45](../../img/typescript/ts-45.jpg)

---

## 🔵 TypeScript #46 – Migrando de JavaScript a TypeScript

Adoptar TypeScript no significa reescribirlo todo desde cero. La clave está en migrar de forma progresiva, integrando el tipado poco a poco y sin romper tu flujo actual.

🔑 ¿Cómo migrar de JS a TS sin morir en el intento?

🔷 Empieza por lo esencial: renombra archivos .js a .ts o .tsx y corrige solo los errores más obvios.
🔷 Activa el compilador: añade un tsconfig.json básico y deja que TypeScript analice tu código existente.
🔷 Tipa desde los bordes: empieza por modelos, funciones públicas o APIs externas.
🔷 Usa any con propósito: como transición temporal, no como muleta.
🔷 Divide la migración: módulo a módulo, feature a feature.

En resumen, migrar a TS es más una maratón de mejoras continuas que un sprint de reescritura.

📌 En el siguiente post veremos cómo aplicar patrones de arquitectura y buenas prácticas con TypeScript.

![ts-46](../../img/typescript/ts-15.jpg)

---

## 🔵 TypeScript #47 – Patrones de arquitectura con TS

TypeScript no solo mejora el tipado: también refuerza la arquitectura de los proyectos.
Su sistema de tipos te permite aplicar principios como separación de capas, modularidad y contratos entre módulos de forma natural.

🔑 ¿Qué patrones y enfoques funcionan bien con TypeScript?

🔷 Clean Architecture: separa dominio, infraestructura y presentación con tipos y modelos bien definidos.
🔷 Dependency Injection: pasa dependencias tipadas en lugar de importarlas directamente.
🔷 Interfaces como contratos: cada capa define qué ofrece sin importar su implementación.
🔷 Módulos bien delimitados: evita acoplamiento usando tipos compartidos (types, models).
🔷 Tipado cruzado: los tipos del dominio fluyen hasta el frontend, garantizando coherencia de datos.

En resumen, TypeScript convierte tu arquitectura en autodocumentada, predecible y más fácil de mantener.

📌 En el siguiente post veremos errores comunes al usar TypeScript y cómo evitarlos.

![ts-47](../../img/typescript/ts-47.jpg)

---

## 🔵 TypeScript #48 – Errores comunes en TS

TypeScript te da poder, pero también es fácil caer en malos hábitos.
Hoy repasamos algunos de los errores más comunes al usarlo y cómo evitarlos con buenas prácticas.

🔑 ¿Qué errores deberías evitar?

🔷 Abusar de any: elimina todo el beneficio del tipado.
🔷 Forzar con as sin comprobar: genera falsos positivos y errores silenciosos.
🔷 Ignorar null/undefined: no tipar casos nulos rompe funciones en tiempo de ejecución.
🔷 Tipos mal definidos: declarar interfaces genéricas sin restricciones puede causar inconsistencias.
🔷 Imports circulares o duplicados: confunden al compilador y al autocompletado.

En resumen, TypeScript solo te protege si respetas el sistema de tipos y no lo eludes por comodidad.

📌 En el siguiente post veremos cómo usar TypeScript con testing, integrándolo con Jest o Vitest.

![ts-48](../../img/typescript/ts-48.jpg)

---

## 🔵 TypeScript #49 – Testing con TypeScript

Los tests también se benefician del tipado. Usar TypeScript en tus pruebas detecta errores antes de ejecutar y mejora la autocompletación en mocks, funciones y assertions.

🔑 ¿Cómo aprovechar TypeScript en el testing?

🔷 Configura Jest o Vitest con TS: ambos soportan tipado nativo (ts-jest, vite-node, etc.).
🔷 Tipa los datos de prueba: usa interfaces para los objetos mockeados.
🔷 Tipa los helpers: funciones como render, setup o factory pueden tener tipos genéricos.
🔷 Aprovecha los tipos de expect: obtendrás autocompletado en assertions (toBe, toHaveLength, etc.).

En resumen, probar con TypeScript hace tus tests más fiables y fáciles de mantener .

📌 En el siguiente post cerraremos la serie con una reflexión final sobre cómo TypeScript cambia tu forma de programar.

![ts-49](../../img/typescript/ts-49.jpg)

---

## 🔵 TypeScript #50 – Reflexión final

50 posts después, hemos recorrido juntos todo el ecosistema de TypeScript:
desde los tipos más básicos hasta arquitecturas limpias, testing, librerías y proyectos reales.

Y si algo queda claro tras todo este viaje es que TypeScript va de entender mejor el código, anticipar errores y diseñar sistemas más sólidos y escalables.

🔑 ¿Qué nos deja esta serie?

🔷 El tipado no limita la creatividad: la guía y la amplía.
🔷 Los errores ya no asustan: se vuelven aliados del flujo de trabajo.
🔷 El código se vuelve más expresivo, más legible y más seguro.
🔷 Y lo más importante: tu equipo gana confianza y velocidad.

TypeScript no sustituye a JavaScript.
Lo complementa, lo refuerza y lo convierte en una herramienta profesional de otro nivel.

✨ Tip final:
No hace falta saberlo todo para empezar.
Empieza tipando lo que entiendas, y deja que TypeScript te enseñe el resto.
El compilador será tu mejor mentor 

Gracias por acompañarme en esta serie.
Han sido 50 publicaciones de código, aprendizaje y buenas prácticas

La próxima será de testing con vitest + react-testing-library, tras una semana de descanso para prepararla bien. habrá noticias pronto!

![ts-50](../../img/typescript/ts-15.jpg)

---