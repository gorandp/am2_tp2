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
- Pablo Usero. Ingeniería

.. todo::

   Completar la ingeniería de Pablo


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

Con la siguiente ley:

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
   :label: ley-ratones-general

   \frac {R}{500-R} = C e^{500kt}

La ecuación :math:numref:`ley-ratones-general` la dejaremos como está, ya que
nos es de utilidad en la forma actual.

Trayendo nuevamente los datos del enunciado (condiciones iniciales) sabemos
que :math:`R(t=0) = 5`, por lo que lo reemplazamos en :math:numref:`ley-ratones-general`:

.. math::

   \frac {5}{500-5} = C e^{500 k * 0}

.. math::

   \frac {5}{495} = C

.. math::

   C = \frac {1}{99}

Por lo que sustituyendo :math:`C` en :math:numref:`ley-ratones-general` nos
queda:

.. math::
   :label: ley-ratones

   \frac {R}{500-R} = \frac {1}{99} e^{500kt}

Ahora solo nos queda averiguar la principal incógnita del problema, en la que
debemos averiguar para qué valor de :math:`t` se cumple que :math:`R(t)=250`.
Reemplazamos esto en :math:numref:`ley-ratones`:

.. math::

   \frac {250}{500-250} = \frac {1}{99} e^{500kt}

.. math::

   1 = \frac {1}{99} e^{500kt}

.. math::

   99 = e^{500kt}

   \ln 99 = 500kt

.. math::
   :label: solucion-p1

   t = \frac {\ln 99}{500k}



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
