.. Trabajo Practico 2 documentation master file, created by
   sphinx-quickstart on Fri Oct  8 21:02:57 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Trabajo Practico 2
==================

.. important:: Fecha límite de entrega: 01-11-21 (23:59 h)

Alumnos
-------

- Goran Prpic. Ingeniería Electrónica.
- Pablo Usero. Ingeniería

.. todo::

   Completar la ingeniería de Pablo

Indicaciones
------------

Forma de trabajo
~~~~~~~~~~~~~~~~

Se realiza en EQUIPO conformado por 2 o 3 estudiantes (pueden pertenecer a
especialidades distintas)

Consigna
~~~~~~~~

Preparar un **VIDEO** en el que se muestre el proceso de modelización y
resolución, por parte de los integrantes del equipo, de **DOS PROBLEMAS**
que se modelicen con **DISTINTOS TIPOS DE ECUACIONES DIFERENCIALES
ORDINARIAS DE PRIMER ORDEN**.

.. attention::

   El enunciado del problema no debe presentar la ecuación diferencial que
   modeliza la situación, sino que a partir de los datos del problema se
   obtenga la modelización del este.

En el video se debe mostrar:

#. Enunciado de la situación planteada.
#. Modelo matemático obtenido (ecuación diferencial ordinaria de primer
   orden) a partir del enunciado.
#. Resolución y obtención de la solución general.
#. Proposición de una condición inicial y obtención de la solución
   particular correspondiente.
#. Análisis las soluciones obtenidas en función del problema.
#. interpretación geométrica de las soluciones obtenidas.

.. attention::

   - Se podrá buscar el problema tanto en libros de AMII como en Internet.
     Indicar fuente bibliográfica.
   - Entregar un archivo PDF en donde se incluya: nombre de los participantes
     del equipo, especialidad y link del video subido en la nube (YouTube o
     OneDrive).
   - Sólo uno de los integrantes del equipo sube la tarea.


Ejercicio 1
===========

Por Goran Prpic.

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

Sea :math:`N(t)` el número de ratones infectados con la enfermedad en el tiempo
:math:`t`. Luego, se dice que en un inicio se infectan 5 ratones, por lo que se
deduce que :math:`N(0) = 5`. Por último, sea :math:`500 - N(t)` el número de
ratones libre de la enfermedad.

Se interpreta la teoría de difusión de epidemia planteada:

   La tasa de cambio en la población infectada es proporcional al producto del
   número de ratones que tienen la enfermedad con el número que está libre de
   ésta

Con la siguiente ley:

.. math::

   \frac {dN}{dt} = k N (500 - N)


   ejercicio_1

\begin{equation}
R_{k+1} = \frac{f^{(k+1)}(\xi)}{(k+1)!}\Delta x^{k+1}, \quad\quad x\leq \xi \leq x+\Delta x.
\end{equation}

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
