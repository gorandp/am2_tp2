.. Trabajo Practico 2 documentation master file, created by
   sphinx-quickstart on Fri Oct  8 21:02:57 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Trabajo Practico 2
==================

Fecha límite de entrega: 01-11-21 (23:59 h)


Alumnos
-------

- Goran Prpic. Ingeniería Electrónica.
- Pablo Usero. Ingeniería Mecánica.


Consigna
--------

Preparar un **VIDEO** en el que se muestre el proceso de modelización y
resolución, por parte de los integrantes del equipo, de **DOS PROBLEMAS**
que se modelicen con **DISTINTOS TIPOS DE ECUACIONES DIFERENCIALES
ORDINARIAS DE PRIMER ORDEN**.

En el video se debe mostrar:

#. Enunciado de la situación planteada.
#. Modelo matemático obtenido (ecuación diferencial ordinaria de primer
   orden) a partir del enunciado.
#. Resolución y obtención de la solución general.
#. Proposición de una condición inicial y obtención de la solución
   particular correspondiente.
#. Análisis las soluciones obtenidas en función del problema.
#. interpretación geométrica de las soluciones obtenidas.

.. admonition:: Forma de trabajo

   Se realiza en EQUIPO conformado por 2 o 3 estudiantes (pueden pertenecer a
   especialidades distintas)

.. attention::

   El enunciado del problema no debe presentar la ecuación diferencial que
   modeliza la situación, sino que a partir de los datos del problema se
   obtenga la modelización del este.

.. attention::

   - Se podrá buscar el problema tanto en libros de AMII como en Internet.
     Indicar fuente bibliográfica.
   - Entregar un archivo PDF en donde se incluya: nombre de los participantes
     del equipo, especialidad y link del video subido en la nube (YouTube o
     OneDrive).
   - Sólo uno de los integrantes del equipo sube la tarea.


Ejercicio 1
===========

Bronson, R. y Costa, G. (año). *Capítulo 7: Aplicaciones de las ecuaciones
diferenciales de primer orden*. **Ecuaciones Diferenciales**. Mc Graw Hill.

Enunciado
---------

Cinco ratones de una población estable de 500 son infectados intencionalmente
con una enfermedad contagiosa para probar una teoría de difusión de epidemia
que postula que la tasa de cambio en la población infectada es proporcional al
producto del número de ratones que tienen la enfermedad con el número que está
libre de ésta. Asumiendo que la teoría es correcta, ¿cuánto tiempo le tomará a
la mitad de la población adquirir la enfermedad?

Desarrollo
----------

Sea :math:`R(t)` el número de ratones infectados con la enfermedad en el tiempo
:math:`t`. Luego, se dice que en un inicio se infectan 5 ratones, por lo que se
deduce que :math:`R(0) = 5`. Por último, sea :math:`500 - R(t)` el número de
ratones libre de la enfermedad.

Se interpreta la teoría de difusión de epidemia planteada:

   La tasa de cambio en la población infectada es proporcional al producto del
   número de ratones que tienen la enfermedad con el número que está libre de
   ésta

Con el siguiente modelo matemático:

.. math::
   :label: planteo-ley

   \frac {dR}{dt} = k R (500 - R)

.. math::
   :label: var-sep

   \frac {1}{R (500 - R)} dR = k dt

Vemos que la forma tomada en :math:numref:`var-sep` es la de una ecuación
diferencial ordinaria de primer orden a variable separables.

Para resolverla, primero descomponemos en fracciones simples la fracción
del primer miembro:

.. math::

   \frac {A}{R} + \frac {B}{500 - R} &= \frac {A(500 - R) + B R}{R (500 - R)} \\
                                     &= \frac {1}{R (500 - R)}

Por lo tanto:

.. math::

   1 = A(500 - R) + B R

   R=0 => A = \frac {1}{500}

   R=500 => B = \frac {1}{500}

Finalmente:

.. math::
   :label: frac-simple

   \frac {1}{R (500 - R)} = \frac {1}{500} ( \frac {1}{R} + \frac {1}{500 - R} )

Reemplazo :math:numref:`frac-simple` en :math:numref:`var-sep`.

.. math::

   \frac {1}{500} ( \frac {1}{R} + \frac {1}{500 - R} ) dR = k dt

   ( \frac {1}{R} + \frac {1}{500 - R} ) dR = 500 k dt

Integro ambos miembros

.. math::

   \int ( \frac {1}{R} + \frac {1}{500 - R} ) dR = 500 k \int dt

.. math::

   \ln |R| - \ln |500 - R| = 500kt + C_1

.. math::

   \ln | \frac {R}{500-R} | = 500kt + C_1

.. math::

   \frac {R}{500-R} = e^{500kt + C_1}

.. math::

   \frac {R}{500-R} = e^{500kt} e^{C_1}

.. math::
   :label: ecuacion-ratones-practica

   \frac {R}{500-R} = C e^{500kt}

Reacomodando:

.. math::

   \frac {1}{\frac {500}{R} -1} = C e^{500kt}

.. math::

   \frac {500}{R} = \frac {1}{C e^{500kt}} + 1

.. math::
   :label: solucion-ratones-general

   R_{(t)} = \frac {500}{ \frac {1}{C e^{500kt}} + 1 }

La ecuación :math:numref:`solucion-ratones-general` es la solución general
a nuestro modelo matemático planteado.

Para calcular :math:`C`, traeremos nuevamente la condicion inicial dada
por el enunciado :math:`R(t=0) = 5` y la reemplazamos en
:math:numref:`ecuacion-ratones-practica` por practicidad:

.. math::

   \frac {5}{500-5} = C e^{500 k * 0}

.. math::

   \frac {5}{495} = C

.. math::

   C = \frac {1}{99}

Por lo que sustituyendo :math:`C` en :math:numref:`solucion-ratones-general`
y reacomodando nos queda:

.. math::
   :label: solucion-particular-previa-ratones

   R_{(t)} = \frac {500}{ \frac {99}{e^{500kt}} + 1 }

Para determinar el valor de :math:`k` deberíamos de tener otra condicion
inicial, por lo que propondremos lo siguiente:

.. admonition:: Condición inicial propuesta

  Se tomó la siguiente medición de las ratas infectadas: :math:`R(t=5) = 10`

Si esto lo reemplazamos en :math:numref:`ecuacion-ratones-practica`:

.. math::

   \frac {10}{500-10} = \frac {1}{99} e^{2500k}

.. math::

   \frac {99}{49} = e^{2500k}

.. math::

   \ln \frac {99}{49} = 2500k

.. math::

   k = \frac {\ln 99 - \ln 49}{2500} \approx 2.81 \times 10^{-4}

Por lo que :math:numref:`solucion-particular-previa-ratones` nos queda:

.. math::
   :label: solucion-particular-ratones

   R_{(t)} = \frac {500}{ \frac {99}{e^{0.1405 t}} + 1 }

La cual, es la solución particular al modelo matemático planteado
inicialmente.

Ahora solo nos queda averiguar la principal incógnita del problema, en la que
debemos averiguar para qué valor de :math:`t` se cumple que :math:`R(t)=250`.
Reemplazamos esto último en :math:numref:`solucion-particular-ratones`:

.. math::

   250 = \frac {500}{ \frac {99}{e^{0.1405 t}} + 1 }

.. math::

   \frac {99}{e^{0.1405 t}} + 1 = \frac {500}{250}

.. math::

   \frac {1}{99} e^{0.1405 t} = 1

.. math::

   e^{0.1405 t} = 99

   0.1405 t = \ln 99

.. math::
   :label: solucion-p1

   t = \frac {\ln 99}{0.1405} \approx 32.705

.. admonition:: Resultado final

   Por lo tanto, el tiempo que le tomará a la mitad de la población adquirir la
   enfermedad es :math:`t=32.705` unidades de tiempo.


Interpretación gráfica
----------------------

.. raw:: html
   :file: _static/graph-1.html



Ejercicio 2
===========

Dennis G. Zill y Warren S. Wright (2015). **Ecuaciones Diferenciales con
problemas con valores en la frontera.** (8va ed.). Cengage Learning.


Enunciado
---------

.. todo::

   Agregar enunciado


Desarrollo
----------

Sea :math:`A_{(t)}` la cantidad de sal, medida en kilogramos, dentro del tanque
en el tiempo :math:`t`, entonces la razón con al que :math:`A_{(t)}` cambia es
una razón neta:

.. math::
   :label: ec-dif-inicial

   \frac {dA}{dt} = R_{entra} - R_{sale}

Donde:

- :math:`R_{entra}` es la **razón de entrada** de la sal con la que entra en
  el tanque
- :math:`R_{sale}` es la **razón de salida** de la sal con la que sale del
  tanque

A su vez, :math:`R_{entra}`, que se mide en kilos por minuto, es el producto
de la concentración de la afluencia de sal y la tasa de flujo de fluido.
Ambas magnitudes, según el enunciado, valen :math:`2 \frac {kg}{litro}` y 
:math:`6 \frac {litro}{minuto}` respectivamente, entonces:

.. math::
   :label: def-r-entra

   R_{entra} = 2 \frac {kg}{litro} * 3 \frac {litro}{minuto} = 6 \frac {kg}{minuto}

Como la solución que sale del tanque tiene la misma razón con la que entra, la
cantidad de litros de salmuera en el tanque al tiempo t es una constante de
300 litros.

Sea :math:`c_{(t)}` la concentración de la sal en el tanque así como en el
flujo de salida, y queda definida de la siguiente manera:

.. math::

   c_{(t)} = \frac { A_{(t)} }{300} \frac {kg}{litro}

Recordemos que :math:`A_{(t)}`  es la **cantidad** de sal detro del tanque
en un tiempo :math:`t`.

Luego, la razón de salida :math:`R_{sale}`, muy similar a la razón de
entrada, es el producto de la concentración de sal en el tanque y el flujo
de salida de la solución. Estas magnitudes valen :math:`c_{(t)}` y
:math:`3 \frac {litro}{minuto}`, es decir:

.. math::

   R_{sale} = c_{(t)} * 3 \frac {litro}{minuto} 

Reemplazamos la definición de :math:`c_{(t)}`, simplificamos y nos queda:

.. math::
   :label: def-r-sale

   R_{sale} = \frac { A_{(t)} }{100} \frac {kg}{minuto}

Con ambas razones definidas, sustituimos :math:numref:`def-r-entra` y
:math:numref:`def-r-sale` en :math:numref:`ec-dif-inicial`:

.. math::

   \frac {dA}{dt} = \left( 6 \frac {kg}{minuto} \right) - \left( \frac
                    { A_{(t)} }{100} \frac {kg}{minuto} \right)

Reacomodando:

.. math::

   \frac {dA}{dt} + \frac { A_{(t)} }{100} \frac {kg}{minuto} = 6 \frac
   {kg}{minuto}

Vemos que todos los términos, en ambos miembros, poseen las mismas unidades
(ya que :math:`\left[ \frac {dA}{dt} \right] = \frac {kg}{minuto}` ), y por lo
tanto, para simplificar el cálculo, dejaremos de mencionarlas de ahora en
más, a no ser que sea necesario explicitarlas. Entonces:

.. math::
   :label: ec-dif-mod-mat

   \frac {dA}{dt} + \frac { A_{(t)} }{100} = 6

La ecuación :math:numref:`ec-dif-mod-mat` es la modelización matemática del
problema planteado, la cual es una ecuación diferencial ordinaria de primer
orden.

Si :math:`R_{entra}` y :math:`R_{sale}` son las razones de entrada y de salida
de las soluciones de salmuera, entonces hay tres posibilidades:

#. :math:`R_{entra} = R_{sale}`
#. :math:`R_{entra} > R_{sale}`
#. :math:`R_{entra} < R_{sale}`

En el análisis que conduce a la ecuación :math:numref:`ec-dif-mod-mat` se tomo
la relación :math:`R_{entra} = R_{sale}`.

Para encontrar la función solución :math:`A_{(t)}` se utiliza método del
factor integrante. Según :math:numref:`ec-dif-mod-mat` se definen:

.. math::

   p_{(t)} = \frac {1}{100}

.. math::

   q_{(t)} = 6

Sea :math:`u_{(t)}` el factor integrante definido como:

.. math::

   u_{(t)} = e ^ {\int p_{(t)} dt} = e ^ {\frac {1}{100} \int dt}

.. math::
   :label: factor-integrante

   u_{(t)} = e^{\frac {t}{100}}

Multiplicando ambos miembros de :math:numref:`ec-dif-mod-mat` por el factor
integrante nos queda:

.. math::

   \frac {dA}{dt} * u_{(t)} + \frac { A_{(t)} }{100} * u_{(t)} = 6 * u_{(t)}

Sustituimos con :math:numref:`factor-integrante`:

.. math::

   \frac {dA}{dt} * e^{\frac {t}{100}} + \frac { A_{(t)} }{100} *
   e^{\frac {t}{100}} = 6 * e^{\frac {t}{100}}

Notamos que el miembro izquierdo de la expresión anterior es igual a la
derivada del producto entre :math:`A_{(t)}` y :math:`e^{\frac {t}{100}}`, por
lo que se puede reescribir como:

.. math::

   \frac {d}{dt} (A_{(t)} * e^{\frac {t}{100}}) = 6 * e^{\frac {t}{100}}

Integramos ambos miembros:

.. math::

   \int \frac {d}{dt} (A_{(t)} * e^{\frac {t}{100}}) dt = \int 6 *
   e^{\frac {t}{100}} dt

.. math::

   A_{(t)} * e^{\frac {t}{100}} = 600 * e^{\frac {t}{100}} + C

Tal que :math:`C` es una constante de integración.

Por último, despejando :math:`A_{(t)}`, obtenemos la **solución general** de la
ecuación diferencial ordinaria de primer orden:

.. math::
   :label: solucion-tanque-general

   A_{(t)} = 600 + C * e^{\frac {-t}{100}}

Por la condición inicial dada en el enunciado, sabemos que :math:`A(t=0) = 50`.
Sustituimos esta condición inicial en :math:numref:`solucion-tanque-general`:

.. math::

   50 = 600 + C * e^{\frac {0}{100}}

.. math::

   -550 = C * 1 \implies C = -550

Reemplazamos en :math:numref:`solucion-tanque-general`:

.. math::
   :label: solucion-tanque-particular

   A_{(t)} = 600 - 550 * e^{\frac {-t}{100}}

Y obtenemos :math:numref:`solucion-tanque-particular` que es la **solución
particular** de nuestro modelo planteado inicialmente.

.. todo::

   Resolver incógnita a plantear en el enunciado


Interpretación gráfica
----------------------

.. todo::

   Agregar gráfica
