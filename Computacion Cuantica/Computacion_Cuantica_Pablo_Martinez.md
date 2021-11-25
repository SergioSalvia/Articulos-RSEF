---
layout: post
categories: blog Divulgación
title:  "La computación cuántica del hoy"
date:  
author: Pablo Martínez Crespo
redirect-from:
---

La Computación Cuántica promete resolver algunos de los problemas más relevantes de nuestra era, así como hacer nuestras comunicaciones mucho más seguras. Todavía estamos alejados de este punto, ya que los ordenadores cuánticos actuales no están suficientemente desarrollados, pero entonces, ¿cómo está afectando la computación cuántica a nuestra tecnología?  Veamos cómo funcionan los ordenadores cuánticos y qué nos pueden ofrecer a corto plazo.

### Hardware cuántico

Las piezas o componentes que forman un ordenador cuántico son muy diferentes de las que se utilizan en los ordenadores actuales, los clásicos. Esto se debe a la naturaleza tan diferente de la unidad fundamental de información de cada uno de ellos: el qubit (*quantum bit*) y el bit, respectivamente. Un bit (clásico) puede tomar dos valores: 0 o 1. Podemos entender esto como apagar o encender un interruptor (de hecho los símbolos que aparecen en los botones de las regletas se deben a esto), pero prefiero asociarlo a una flecha que apunta hacia arriba o hacia abajo. Pues bien, en el caso del qubit... ¡esta flecha puede apuntar en cualquier dirección del espacio! Esto cambia totalmente la forma de razonar a la hora de diseñar algoritmos, y es consecuencia de la naturaleza cuántica del qubit. 

![Fig1](1.png)<br/>
<br/><a name="Fig1">**Figura 1**</a>: La esfera de Bloch es donde se representan los posibles estados |ψ⟩ en los que puede estar un qubit, definidos por los ángulos θ y φ.

Mientras que un bit puede construirse con un condensador de escala nanométrica que se carga o descarga según queramos codificar un 1 o un 0, un qubit debe construirse con un dispositivo que sea inherentemente cuántico. Esto hace que un bit esté mucho más fortalecido que un qubit, en el sentido de que **es más difícil que en un proceso de computación clásica un bit tome un valor erróneo a que un qubit se encuentre en un estado que no le correspondía**. Una forma fácil de entender esto es pensar que para cargar un condensador se necesita un número grande de electrones, por lo que el bit *no se entera* si un electrón se escapa. En cambio, el caso del qubit es más similar a tener un único electrón confinado (de hecho, esta es una forma de crear qubits), por lo que aquí la diferencia es fundamental, y la base del qubit en sí mismo. Hoy en día se están investigando varias posibilidades para fabricar qubits. Destacan especialmente los qubits de circuitos superconductores, que son los más ampliamente usados en los computadores cuánticos actuales<sup name="f1">[1](#foot1)</sup>. 


![Fig2](7qubit_chip2.png)<br/>
<br/><a name="Fig2">**Figura 2**</a>: Procesador cuántico de siete qubits superconductores construido por IBM para simular una molécula de BeH<sub>2</sub> <a href="#Ref1">[1]</a>.
<br/>

Sea cual sea el diseño para nuestros qubits, los desafíos que se tratan de superar van asociados a ser capaces de evitar que éstos cambien su estado sin que se lo pidamos, intentando aumentar lo que llamamos su tiempo de coherencia. Este tiempo de coherencia se define como el tiempo que tarda la interacción entre el qubit y el entorno en cambiar el estado del qubit sin que se lo pidamos, motivo por el que los ordenadores cuánticos se mantienen a temperaturas muy bajas, unos pocos centikelvin (-273 grados centígrados aproximadamente), ya que a temperaturas muy bajas los átomos que puedan estar al rededor del qubit empezarán a moverse cada vez más lento, haciendo la interacción más débil.

Como hemos comentado, todo lo que pueda interactuar con nuestro qubit será susceptible de fastidiar nuestro tiempo de coherencia. Es por esto que controlar el estado de un qubit se vuelve un problema aún mayor cuando tenemos varios qubits juntos, ya que pueden influirse los unos a los otros. Esto frena el desarrollo de los ordenadores cuánticos actuales, por lo que la mayoría de los disponibles hoy en día tienen del orden de 50 qubits<sup name="f2">[2](#foot2)</sup> (frente a los millones de bits con los que opera un ordenador clásico), y siempre es posible que alguno de estos qubits cambie de estado *sin avisar* en el proceso de un algoritmo. Por todo esto, nos referimos a los ordenadores cuánticos disponibles actualmente y en el futuro cercano como Dispositivos Cuánticos Ruidosos de Escala Intermedia, aunque si quieres saber más sobre estos es mejor que busques por sus siglas en inglés: NISQs (*Noisy Intermediate-Scale Quantum devices*).

![Fig3](IBM-Building-Quantum-Computers-for-Business-and-Science-IBM-Q-1-768x479.jpg)<br/>
<br/><a name='Fig3'>**Figura 3**</a>: Imágenes de un refrigerador de dilución que enfría procesadores cuánticos superconductores. La foto de la izquierda muestra el exterior, mientras que la de la derecha muestra el cableado con las temperaturas correspondientes en cada zona <a href="#Ref2">[2]</a>.
<br/>

### Lógica cuántica y algoritmos híbridos

En este punto te estarás preguntando: si los qubits son tan diferentes de los bits, ¿cómo se hacen algoritmos con ellos? De nuevo, recurrimos al análogo clásico. Hay varias operaciones que podemos realizar sobre un bit. Si volvemos a nuestro ejemplo de la flecha que solo puede estar hacia arriba o hacia abajo (es decir, el bit clásico) lo único que podemos hacer es dejarla igual o girarla 180 grados. En el caso de los qubits nuestras posibilidades aumentan, y también tenemos varias operaciones correspondientes a cómo podemos rotar una flecha en 3D a diferentes ángulos, las llamadas puertas cuánticas (*quantum gates*). Pero esto no es lo único que diferencia a los qubits. Lo más especial de ellos es que presentan tres propiedades puramente cuánticas: **superposición**, **interferencia** y **entrelazamiento**.

Podemos ilustrar cómo entran en juego estas propiedades comparando la forma en que un ordenador clásico y uno cuántico hacen cálculos. Básicamente, un ordenador clásico necesita comprobar qué bits valen 0 y 1 al final de una serie de operaciones; es decir, necesita realizar una **medida**. Esto también es así en el caso cuántico: obtendremos un 0 ó un 1 al medir sobre un qubit. Sin embargo, mientras que un bit tiene su valor determinado antes de que lo comprobemos, el qubit *lo decide* en el momento. Esta es la forma en la que se manifiesta la **superposición**: permite que un qubit pueda ser de alguna forma un 0 y un 1 a la vez **antes de medir**. Decimos que el qubit *colapsa* al medir, o sea, al decidir si es un 0 ó un 1. Esto tiene un gran potencial, ya que al poder tomar nuestro qubit cualquiera de los dos valores, estamos teniendo en cuenta ambas posibilidades en el proceso de un algoritmo, aumentando la velocidad de cómputo en algunos casos concretos.
  
La probabilidad de que el qubit colapse a un valor u otro sí que está definida antes de medir, y se determina en función de las operaciones que se hayan ejecutado sobre los qubits. Estas operaciones presentan dos propiedades especiales. La primera es que se pueden ligar las probabilidades de dos qubits distintos, de forma que medir sobre un qubit obligue a otro a tomar un valor concreto. En esto consiste el **entrelazamiento**. La segunda, la **interferencia**, consiste en que, aunque dos qubits distintos puedan estar aparentemente en el mismo estado (o sea, que tengan las mismas probabilidades de valer 0 o 1), aplicar la misma operación a cada uno de ellos puede hacer que uno solo pueda valer 0 y el otro solo pueda valer 1. Como puedes ver, esto es bastante distinto a lo que podemos hacer con un bit, y nos proporciona un amplio abanico de posibilidades a la hora de diseñar algoritmos.

### Aplicaciones a corto plazo

Hasta ahora parece que tenemos un balance: por un lado, las propiedades cuánticas de los qubits presentan un gran potencial, pero al mismo tiempo tenemos el problema del tiempo de coherencia. A pesar de las limitaciones actuales, la creatividad del personal investigador ha permitido encontrar formas de aprovechar los NISQs (Dispositivos Cuánticos Ruidosos de Escala Intermedia) para poner la computación cuántica al servicio de la resolución de problemas reales. Para ello, se diseñan algoritmos en los que un ordenador clásico y uno cuántico cooperan: algoritmos híbridos. En ellos, los recursos de cada parte se utilizan en la tarea más apropiada para ella.

Pero, ¿qué problemas actuales se están tratando de resolver con estos algoritmos híbridos? Antes de que la emoción nos desborde, vamos a mantener los pies en la tierra: no existe ningún algoritmo cuántico para NISQs que haya sido capaz de superar a un algoritmo clásico en problemas del mundo real, alcanzando lo que se llama *ventaja cuántica*. Por ahora, los métodos clásicos siguen siendo más efectivos. Aun así, podemos utilizar los algoritmos cuánticos que tenemos como plataforma de prueba y exploración de qué condiciones se tienen que dar para conseguir esa ventaja. 

El tipo de problemas en que la computación cuántica tiene mayor potencial de ser ventajosa es en problemas de combinatoria. Este tipo de problemas dependen del orden en el que se colocan una serie de objetos. Cuantos más objetos tenemos, el número de formas de ordenarlos aumenta exponencialmente; es decir, la dificultad de encontrar una solución óptima crece de forma muy rápida. La computación cuántica explota superposición, interferencia y entrelazamiento para explorar más de una combinación al mismo tiempo, en lugar de tener que probarlas todas una a una. 

Hay cuestiones de muchos campos que pueden reducirse a problemas combinatorios, desde la química o la ciencia de materiales hasta las finanzas o la criptografía. Las propiedades de una molécula, por ejemplo, dependen de qué átomos la conformen, y estos átomos además pueden organizarse de diversas formas. Encontrar qué combinación de átomos es la más óptima para conseguir ciertas propiedades es un gran problema de combinatoria. Ya hay empresas<sup name="f3">[3](#foot3)</sup> que invierten en solucionar estos problemas con NISQs para estar preparadas el día que aparezca ventaja cuántica en algún campo de su interés. Entre ellas, encontramos bancos tratando de hacer más eficientes sus finanzas, empresas de ciberseguridad o desarrolladoras de materiales. 

### Conclusiones

Aunque los ordenadores cuánticos que revolucionarán el mundo tal y como lo conocemos aún estén lejos, el desarrollo de algoritmos cuánticos ha ayudado a mejorar nuestra comprensión de estos problemas combinatorios de gran escala. Solo por eso, podemos decir que la computación cuántica ya está transformando nuestro mundo. Por otro lado, no se debe perder de vista que la importancia de los NISQs no se debe solo a las aplicaciones que puedan tener en el presente y el futuro cercano. Estos también son una herramienta para la exploración y la investigación del funcionamiento de la computación cuántica desde el nivel más fundamental. Aún hay cosas que se nos escapan y efectos que no comprendemos del todo. Tener hardware cuántico en el que ir probando algoritmos e indagar en qué formas se pueden controlar más eficientemente los qubits, aparte de representar un gran logro, nos permite acercarnos cada vez más a los ordenadores cuánticos de gran escala, así como seguir mejorando los propios NISQs para aprovechar cuanto antes las posibilidades que ofrecen.

---
<a name="foot1">1</a>: Concretamente, el transmón es el qubit superconductor más extendido, dejamos esta referencia si quieres entender cómo funciona: [https://arxiv.org/abs/cond-mat/0703002].

<a name="foot2">2</a>: Recientemente, IBM ha puesto en funcionamiento el procesador cuántico Eagle con 127 qubits, el máximo hasta la fecha y primero en superar los 100 qubits. Pretenden alcanzar los 400 qubits en 2022 y los 1000 en 2023.

<a name="foot3">3</a>: OTI Lumionics, CogniFrame o Solid State AI, por dar nombres: [https://dx.doi.org/10.1140/epjqt/s40507-021-00091-1].

### Referencias
<a name="Ref1">[1]</a>: IBM Blog [https://www.ibm.com/blogs/research/2017/09/quantum-molecule/]<br/>
<a name="Ref2">[2]</a>: IBM Blog [https://www.ibm.com/blogs/research/2020/01/quantum-limited-amplifiers/]<br/>
