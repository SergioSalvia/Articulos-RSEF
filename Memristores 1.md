---
layout: post
categories: blog 
title:  "Memristores: ¿neuronas para tu ordenador? (Parte I)"
date:  
author: Sergio J Salvía Fernández
redirect-from:
---


# Memristores: ¿neuronas para tu ordenador? (Parte I)

Desde *Blade runner* o la *Saga fundación*, a los humanos siempre nos ha gustado imaginar ordenadores casi humanos, capaces de pensar y aprender de forma independiente y
que se plantean el significado de la vida (normalmente con desastrosas consecuencias). A pesar de ello, llevamos bastante tiempo fallando en nuestras premoniciones distópicas
(sin ir más lejos, ¡Blade Runner se desarrolla en un noviembre de 2019!). A día de hoy el uso de la inteligencia artificial está bastante extendido en distintos ámbitos,
y pese a esto, seguimos sin poder saludar a nuestro jardinero androide cuando vamos a la universidad, por lo que parece que este futuro humanoide está bastante lejos...
¿o tal vez no?

Desde 2008 cientos de científicos trabajan para entender mejor lo que se conoce como **memristores**: dispositivos nanoelectrónicos que intentan imitar el funcionamiento de las neuronas, planteándose como una gran oportunidad de cara al diseño de nuevas estructuras computacionales, y como propulsores de una revolución en el campo de la inteligencia artificial. Son muchas las preguntas que quedan por responder en torno a este tema así que en este artículo, para no extendernos demasiado, vamos a intentar responder las más básicas: ¿cómo? y ¿por qué?.

### ¿Cómo aprende tu cerebro?
En primer lugar ¿por qué nuestros ordenadores no son androides (o algo parecido)?. Al fin y al cabo «inteligencia artificial» ya es algo que suena bastante bien, y contiene la
palabra «inteligencia»... ¿es todo una mentira?, ¿¡por qué se empeñan en engañarnos!? Que no cunda el pánico, veamos qué es lo que hace especial a la inteligencia biológica.

La forma que tiene el cerebro de almacenar información y, en consecuencia, aprender, es haciendo uso de las neuronas, más concretamente las conexiones que se establecen entre
ellas: las sinápsis. En la [Figura 1](#Fig1) se muestra un esquema de su funcionamiento.


![Sinapsis](Sinapsis.png)<br/>
<a name="Fig1">**Figura 1**</a>: Esquema de una sinapsis entre dos neuronas [[1]](#Ref1).


En este esquema podemos distinguir dos partes principales: el **axón terminal** y el **botón dendrítico**. Para no entrar mucho en la parte bioquímica, basta con pensar que el axón terminal es el cable final de una neurona, llamada **neurona presináptica** o emisora, mientras que el botón dendrítico es el cable inicial de la siguiente neurona, llamada **neurona postsináptica** o receptora. Cuando un impulso nervioso llega a la neurona presináptica, provoca que esta libere en el espacio sináptico una serie de neurotransmisores, que alcanzan la neurona postsináptica, pudiendo dar lugar a que el impulso continúe. Esta es la forma que tienen las neuronas de comunicarse entre ellas.

Pero, ¿qué tiene que ver esto con aprender? Cuando dos neuronas se conectan a través de una sinapsis, la concentración de iones de calcio en la neurona postsináptica aumenta muchísimo<sup>[1](#foot1)</sup>, para luego caer rápidamente, en un tiempo del orden de los milisegundos. Sin embargo, si se da otra sinápsis antes de que la concentración haya disminuido demasiado, puede superarse un umbral y que la cantidad de iones se mantenga constante en un valor mucho mayor que el que había antes de estos dos impulsos. La presencia de estos iones hace que la posibilidad de transmisión entre las dos neuronas que constituyen el enlace sea mucho más probable, ¡y así es como aprendemos!<sup>[2](#foot2)</sup>. La próxima vez que la neurona presináptica se active, será más probable que se active la neurona postsináptica que hayamos activado antes más veces. Esta capacidad por la cual las conexiones entre las neuronas pueden potenciarse o debilitarse se llama plasticidad sináptica, y es la base del aprendizaje en los seres vivos.  Un esquema conceptual de esto se representa en la [Figura 2](#Fig2).


![Grafo](grafo.PNG)<br/>
<a name="Fig2">**Figura 2**</a>: Esquema conceptual del modelo de aprendizaje biológico.


Aquí podemos ver distintos nodos (que en la realidad estarían formados por subredes de neuronas) representando conceptos. Durante el aprendizaje de lo que es una manzana, en este caso, se refuerzan las conexiones entre las características «redondo», «rojo» y «fruta». De esta forma el cerebro es capaz de representar un concepto abstracto simplemente usando el patrón que se forma gracias a las conexiones. Además, al estar reforzadas las conexiones, será capaz de recordar la manzana cuando vea una fruta roja, aunque no distinga bien su forma porque nos hayamos olvidado nuestras gafas en casa.

Cuando se descubrió esto y se pensó en implementarlo en ordenadores, se intentó hacer uso de este principio, aunque existe una enorme barrera que los esquemas clásicos de inteligencia artificial no pueden superar. Tal y como hemos descrito el proceso anteriormente, puede observarse que el procesado de información y la memoria son totalmente inseparables en el cerebro, ambos tienen lugar en la neurona. Así, nuestro cerebro es capaz de memorizar gracias a la plasticidad sináptica, y procesar información conectando distintas neuronas entre sí, por lo que el elemento principal es la sinapsis. Esto en un ordenador actual es imposible, ya que el procesado de información y la memoria están físicamente separados, lo que nos lleva al siguiente punto.

### Cuestión de velocidades: La arquitectura de von Neumann

Todos los ordenadores que hay actualmente en el mercado y disponibles para cualquier persona (a fecha de 2020) siguen una arquitectura computacional que se suele llamar arquitectura de von Neumann. Este esquema se representa en la [Figura 3](#Fig3).


![vNeumann](vonneumann.jpg)<br/>
<a name="Fig3">**Figura 3**</a>: Esquema de distribución de elementos según la arquitectura de von Neumann[[2]](#Ref2).


El aspecto principal de este tipo de ordenadores es que la unidad de procesamiento, la CPU, (es decir, el lugar en el que se realizan las operaciones lógicas, donde tu ordenador «piensa») está separado físicamente de la memoria, el lugar donde se almacena la información. Esto supone un grandísimo inconveniente, que en los últimos años ha empezado a preocupar a los científicos que se dedican a la computación. Tal y como están diseñados nuestros ordenadores, la CPU y la memoria tienen que estar intercambiando información **constantemente**, y ese flujo de información consume más tiempo que muchas actividades que tiene que realizar la CPU. Sería algo así como que tu profesor en un examen te mandara hacer una multiplicación, pero te ordenara entregar la respuesta en papel a un profesor en Pekín; la respuesta la podrás obtener rápido, pero pierdes muchísimo tiempo en el viaje. Este problema se llama **cuello de botella de von Neumann** (en inglés *von Neumann bottleneck*), y es otro de los motivos por los que los memristores podrían suponer una revolución a nivel computacional, ya que en principio, como veremos más adelante, no tienen este problema. Este cuello de botella supone una gran desventaja para nuestras inteligencias artificiales, ya que su velocidad se ve mermada.

### Algunas conclusiones por el momento...

De momento hemos aprendido cómo aprende nuestro cerebro, y hemos hecho frente a una de las grandes limitaciones a las que nuestros dispositivos deben hacer frente: el cuello de botella de von Neumann. Podemos empezar a ver así algunas diferencias cruciales entre ordenadores y cerebros, en concreto, la separación entre procesado de información y memoria, que zancadillea a los primeros. Pero... ¿qué hay de los memristores? Hablaremos de ellos en la siguiente parte de nuestro artículo, así podemos mantener un poco de suspense... ¡que siempre alegra la vida!, dejar reposar estas ideas, y volver con fuerza para enfrentarnos al as que guardaba la ciencia bajo la manga, para ayudar a nuestros «pobres» ordenadores en esta lucha contra sus propias limitaciones.

---

<a name="foot1">1</a>: Aquí hablamos del calcio, pero en general se dan un conjunto de corrientes iónicas que involucran otras especies químicas como el sodio o el potasio. La sinápsis es un proceso complejo, pero de hecho... ¡muy físico! El modelo de ecuaciones diferenciales que describe los procesos de disparo de un inpulso nervioso en las neuronas se conoce como Modelo de Hodgkin y Huxley, y le valió a estos dos biofísicos el Nobel en fisiología o medicina en 1963.

<a name="foot2">2</a>: «The calcium concentration in the post-synaptic neuron increases following a spiking event of the pre-synaptic neuron, then decays within a timescale of tens of milliseconds. If the post-synaptic neuron also fires within this time frame, the calcium concentration can be enhanced above a threshold that triggers synaptic potentiation. The calcium concentration, and in turn the strength of the potentiation, depends on the relative timing of the pre- and postneuron spikes and this mechanism has been argued as the possible underlying process behind the observed spike-timing-dependent plasticity and rate-dependent plasticity effects» [[3]](#Ref3). 

### Referencias
<a name="Ref1">[1]</a>: Wikimedia Commons[https://commons.wikimedia.org/wiki/File:Sinapsis.png] (visita 24/04/2020)<br/>
<a name="Ref2">[2]</a>: Wikimedia Commons[https://commons.wikimedia.org/wiki/File:Arquitecturaneumann.jpg] (visita 24/04/2020)<br/>
<a name="Ref3">[3]</a>:M.A. Zidan, J.P. Strachan, W.D. Lu, _The future of electronics based on memristive systems_, Nat Electron 1, 22–29 (2018)<br/>


