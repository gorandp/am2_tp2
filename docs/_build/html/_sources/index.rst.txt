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


Gráficas
--------

.. raw:: html
   :file: _static/graph-1.html


Ejercicio 2
===========

Enunciado
---------

Test

Desarrollo
----------

Test

Gráficas
--------

Test
