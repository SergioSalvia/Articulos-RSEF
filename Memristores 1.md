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

Desde 2008 cientos de científicos trabajan para entender mejor lo que se conoce como **memristores**: dispositivos nanoelectrónicos que intentan imitar el funcionamiento de las
neuronas, planteándose como una gran oportunidad de cara al diseño de nuevas estructuras computacionales, y como propulsores de una revolución en el campo de la inteligencia 
artificial. Son muchas las preguntas que quedan por responder en torno a este tema así que en este artículo, para no extendernos demasiado, vamos a intentar responder las más 
básicas: ¿cómo? y ¿por qué?.

### ¿Cómo aprende tu cerebro?
En primer lugar ¿por qué nuestros ordenadores no son androides (o algo parecido)?. Al fin y al cabo «inteligencia artificial» ya es algo que suena bastante bien, y contiene la
palabra «inteligencia»... ¿es todo una mentira?, ¿¡por qué se empeñan en engañarnos!? Que no cunda el pánico, veamos qué es lo que hace especial a la inteligencia biológica.

La forma que tiene el cerebro de almacenar información y, en consecuencia, aprender, es haciendo uso de las neuronas, más concretamente las conexiones que se establecen entre
ellas: las sinápsis. En la Figura 1 se muestra un esquema de su funcionamiento.

![Sinapsis](Sinapsis.png)
**Figura 1**: Esquema de una sinapsis entre dos neuronas

En este esquema podemos distinguir dos partes principales: el **axón terminal** y el **botón dendrítico**. Para no entrar mucho en la parte bioquímica, basta con pensar que el axón terminal es el cable final de una neurona, llamada **neurona presináptica** o emisora, mientras que el botón dendrítico es el cable inicial de la siguiente neurona, llamada **neurona postsináptica** o receptora. Cuando un impulso nervioso llega a la neurona presináptica, provoca que esta libere en el espacio sináptico una serie de neurotransmisores, que alcanzan la neurona postsináptica, pudiendo dar lugar a que el impulso continúe. Esta es la forma que tienen las neuronas de comunicarse entre ellas.

Pero, ¿qué tiene que ver esto con aprender? Cuando dos neuronas se conectan a través de una sinapsis, la concentración de iones de calcio en la neurona postsináptica aumenta muchísimo[^1], para luego caer rápidamente, en un tiempo del orden de los milisegundos. Sin embargo, si se da otra sinápsis antes de que la concentración haya disminuido demasiado, puede superarse un umbral y que la cantidad de iones se mantenga constante en un valor mucho mayor que el que había antes de estos dos impulsos. La presencia de estos iones hace que la posibilidad de transmisión entre las dos neuronas que constituyen el enlace sea mucho más probable, ¡y así es como aprendemos!«The calcium concentration in the post-synaptic neuron increases following a spiking event of the pre-synaptic neuron, then decays within a timescale of tens of milliseconds. If the post-synaptic neuron also fires within this time frame, the calcium concentration can be enhanced above a threshold that triggers synaptic potentiation. The calcium concentration, and in turn the strength of the potentiation, depends on the relative timing of the pre- and postneuron spikes and this mechanism has been argued as the possible underlying process behind the observed spike-timing-dependent plasticity and rate-dependent plasticity effects»[3] La próxima vez que la neurona presináptica se active, será más probable que se active la neurona postsináptica que hayamos activado antes más veces. Esta capacidad por la cual las conexiones entre las neuronas pueden potenciarse o debilitarse se llama plasticidad sináptica, y es la base del aprendizaje en los seres vivos. 

[^1]: Aquí hablamos del calcio, pero en general se dan un conjunto de corrientes iónicas que involucran otras especies químicas como el sodio o el potasio. La sinápsis es un proceso complejo, pero de hecho... ¡muy físico! El modelo de ecuaciones diferenciales que describe los procesos de disparo de un inpulso nervioso en las neuronas se conoce como Modelo de Hodgkin y Huxley, y le valió a estos dos biofísicos el Nobel en fisiología o medicina en 1963.

