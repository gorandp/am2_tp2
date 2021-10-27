.. Trabajo Practico 2 documentation master file, created by
   sphinx-quickstart on Fri Oct  8 21:02:57 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Trabajo Práctico 2
==================

**Universidad Tecnológica Nacional - Facultad Regional San Nicolás**

**Materia**: Análisis Matemático 2

**Fecha**: 25-10-2021


Alumnos
-------

- Goran Prpic. Ingeniería Electrónica.
- Pablo Usero. Ingeniería Mecánica.
- Santiago Asenjo. Ingeniería Electrónica.


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

   Fecha límite de entrega: 01-11-21 (23:59 h)

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

.. figure:: _static/lab_rats.webp
   :alt: Ratones

   Imagen ilustrativa. `Criver <https://www.criver.com/eureka/the-early-
   history-of-the-lab-rat>`_


Desarrollo
----------

Sea :math:`R(t)` el número de ratones infectados con la enfermedad en el tiempo
:math:`t`. Luego, se dice que en un inicio se infectan 5 ratones, por lo que se
deduce que :math:`R(0) = 5`. Por último, sea :math:`500 - R(t)` el número de
ratones libre de la enfermedad.

La teoría de difusión de epidemia plantea lo siguiente:

   La tasa de cambio en la población infectada es proporcional al producto del
   número de ratones que tienen la enfermedad con el número que está libre de
   ésta

.. admonition:: Modelo matemático

   Lo cual se modeliza con el siguiente modelo matemático:

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


.. admonition:: Solución general

   Despejando :math:`R(t)` nos queda la solución general
   a nuestro modelo matemático planteado:

   .. math::
      :label: solucion-ratones-general

      R_{(t)} = \frac {500}{ \frac {1}{C e^{500kt}} + 1 }


Para calcular :math:`C`, traeremos nuevamente la condicion inicial dada
por el enunciado :math:`R(t=0) = 5` y la reemplazamos en
:math:numref:`ecuacion-ratones-practica` por practicidad:

.. math::

   \frac {5}{500-5} = C e^{500 k · 0}

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

Si esto lo reemplazamos en :math:numref:`ecuacion-ratones-practica`
(reemplazando previamente el valor de :math:`C`):

.. math::

   \frac {10}{500-10} = \frac {1}{99} e^{2500k}

.. math::

   \frac {99}{49} = e^{2500k}

.. math::

   \ln \frac {99}{49} = 2500k

.. math::

   k = \frac {\ln 99 - \ln 49}{2500} \approx 2.81 \times 10^{-4}

.. admonition:: Solución particular

   Reemplazando :math:`k` en :math:numref:`solucion-particular-previa-ratones`
   nos queda la solución particular al modelo matemático planteado inicialmente:

   .. math::
      :label: solucion-particular-ratones

      R_{(t)} = \frac {500}{ \frac {99}{e^{0.1405 t}} + 1 }

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

Vemos que la primer condicion inicial (CI)(en el gráfico se representa con un
punto llamado :math:`A(0, a_y)`) hace variar el valor de :math:`C`. También,
vemos que si mantenemos fijo el valor de la segunda CI (representada con un
punto llamado :math:`B(5 , b_y)`), variando :math:`a_y` se modifica también
el valor de :math:`k`. Al variar :math:`b_y` se consigue cambiar el valor de
:math:`k`.

.. raw:: html
   :file: _static/graph-1.html

Vemos que el valor de :math:`t` en :math:`R(t)=250` es ligeramente distinto al
calculado en el desarrollo, esto se debe a que hubo un error de redondeo cuando
se calculó :math:`k` en el desarrollo, si se hubieran mantenido las expresiones
sin calcular y se resolvía utilizando la mayor cantidad de decimales posible,
el resultado sería identico al mostrado en la gráfica.

En el siguiente gráfico, no mantendremos fijo la posición de :math:`B`.
Modificaremos el valor de :math:`k` con un deslizador. Esto los haremos para
mostrar cómo al variar :math:`a_y` la curva solución se desplaza y "sigue"
las trazas dada por los vectores del campo descripto por la solución general.

.. raw:: html
   :file: _static/graph-1b.html


Ejercicio 2
===========

Dennis G. Zill y Warren S. Wright (2015). **Ecuaciones Diferenciales con
problemas con valores en la frontera.** (8va ed.). Cengage Learning.


Enunciado
---------

Se posee un tanque con 300 litros de salmuera y 50 kg de sal disuelta en un
inicio. Al mismo se le quiere variar la concentración de sal mediante el
ingreso de salmuera de una concentración distinta y la expulsión del líquido
del tanque al mismo ritmo del que entra.

Con esto se quiere demostrar que la tasa de variación instantánea de la
cantidad de sal en el tanque responde directamente a la diferencia de la razón
de entrada de sal con la de salida.

En este caso, la salmuera ingresante tiene una concentración de 2kg/litro de
sal. El ritmo con que ingresa es de 3 litros/minuto.

Además de demostrar lo mencionado previamente, se quiere averiguar si hay una
tendencia en la cantidad de sal dentro del tanque en un período largo de
tiempo, y si la hay, saber su valor.

Por ultimo, ¿Cuánta sal se depositará en en el tanque si el flujo de entrada
de la salmuera fuera mayor que el flujo de salida de la mezcla?


.. figure:: _static/tanque.png
   :width: 250
   :alt: tanque

   Imagen ilustrativa. `Zill y Wright. Ecuaciones Diferenciales con
   problemas con valores en la frontera` (valores editados).


Desarrollo
----------

Desarrollo (Parte A)
~~~~~~~~~~~~~~~~~~~~

Sea :math:`A(t)` la cantidad de sal, medida en kilogramos, dentro del tanque
en el tiempo :math:`t`. Además, el enunciado nos dice que :math:`A(t=0) = 50`.
También sabemos que :math:`[A(t)] = kg`.

Luego, el enunciado nos dice lo siguiente:

  se quiere demostrar que la **tasa de variación** instantánea de la **cantidad
  de sal en el tanque** responde **directamente** a la **diferencia** de la
  **razón de entrada de sal con la de salida**

Lo cual, se puede modelizar matemáticamente con la siguiente ecuación
diferencial:

.. math::
   :label: ec-dif-inicial

   \frac {dA}{dt} = R_{entra} - R_{sale}

Donde:

- :math:`R_{entra}` es la **razón de entrada** de la sal con la que entra en
  el tanque
- :math:`R_{sale}` es la **razón de salida** de la sal con la que sale del
  tanque

A su vez, :math:`R_{entra}`, que se mide en :math:`\frac {kg}{minuto}`, es el
producto de la concentración de la afluencia de sal y la tasa de flujo de
fluido. Ambas magnitudes, según el enunciado, valen :math:`2 \frac {kg}{litro}`
y :math:`6 \frac {litro}{minuto}` respectivamente, entonces:

.. math::
   :label: def-r-entra

   R_{entra} = 2 \frac {kg}{litro} · 3 \frac {litro}{minuto} = 6 \frac {kg}{minuto}

Como la solución que sale del tanque lo hace con la misma intensidad que con
la que entra, la cantidad de litros de salmuera en el tanque al tiempo
:math:`t` es una constante de 300 litros.

Sea :math:`c_{(t)}` la concentración de la sal en el tanque así como en la
mezcla de salida, y queda definida de la siguiente manera:

.. math::
   :label: def-concentracion-tanque

   c_{(t)} = \frac { A_{(t)} }{300} \frac {kg}{litro}

Recordemos que :math:`A(t)`  es la **cantidad** de sal dentro del tanque
en un tiempo :math:`t`.

Luego, la razón de salida de sal :math:`R_{sale}`, muy similar a la razón de
entrada, es el producto de la concentración de sal en el tanque y el flujo
de salida de la solución. Estas magnitudes valen :math:`c_{(t)}` y
:math:`3 \frac {litro}{minuto}`, es decir:

.. math::

   R_{sale} = c_{(t)} · 3 \frac {litro}{minuto} 

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

.. admonition:: Modelo matemático

   La siguiente ecuación es la **modelización matemática** del
   problema planteado, la cual es una **ecuación diferencial lineal de primer
   orden**.

   .. math::
      :label: ec-dif-mod-mat

      \frac {dA}{dt} + \frac { A_{(t)} }{100} = 6

Para encontrar la función solución :math:`A(t)` se utiliza método del
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

   \frac {dA}{dt} · u_{(t)} + \frac { A_{(t)} }{100} · u_{(t)} = 6 · u_{(t)}

Sustituimos con :math:numref:`factor-integrante`:

.. math::

   \frac {dA}{dt} · e^{\frac {t}{100}} + \frac { A_{(t)} }{100} ·
   e^{\frac {t}{100}} = 6 · e^{\frac {t}{100}}

Notamos que el miembro izquierdo de la expresión anterior es igual a la
derivada del producto entre :math:`A(t)` y :math:`e^{\frac {t}{100}}`, por
lo que la expresión anterior se puede reescribir como:

.. math::

   \frac {d}{dt} (A_{(t)} · e^{\frac {t}{100}}) = 6 · e^{\frac {t}{100}}

Integramos ambos miembros:

.. math::

   \int \frac {d}{dt} (A_{(t)} · e^{\frac {t}{100}}) dt = \int 6 ·
   e^{\frac {t}{100}} dt

.. math::

   A_{(t)} · e^{\frac {t}{100}} = 600 · e^{\frac {t}{100}} + C

Tal que :math:`C` es una constante de integración.

.. admonition:: Solución general

   Por último, despejando :math:`A(t)`, obtenemos la **solución general** de la
   ecuación diferencial lineal de primer orden:

   .. math::
      :label: solucion-tanque-general

      A_{(t)} = 600 + C · e^{\frac {-t}{100}}

Por la condición inicial dada en el enunciado, sabemos que :math:`A(t=0) = 50`.
Sustituimos esta condición inicial en :math:numref:`solucion-tanque-general`:

.. math::

   50 = 600 + C · e^{\frac {0}{100}}

.. math::

   -550 = C · 1 \implies C = -550


.. admonition:: Solución particular

   Reemplazamos :math:`C`  en :math:numref:`solucion-tanque-general` y
   obtenemos la **solución particular** de nuestro modelo planteado
   inicialmente:

   .. math::
      :label: solucion-tanque-particular

      A_{(t)} = 600 - 550 · e^{\frac {-t}{100}}


Ahora, resolveremos la primer incógnita de nuestro problema, y es, si hay o no
una tendencia en la cantidad de sal depositada pasado un período largo de
tiempo. Para esto observamos la cantidad de sal depositada en el tanque para
distintos valores temporales.

.. list-table::
    :widths: 10 10 5 10 10
    :header-rows: 1

    * - :math:`t` [minutos]
      - :math:`A(t)` [kg]
      - 
      - :math:`t` [minutos]
      - :math:`A(t)` [kg]
    * - 0
      - 50
      - 
      - 200
      - 525.56
    * - 50
      - 266.4
      - 
      - 300
      - 572.61
    * - 100
      - 397.66
      - 
      - 400
      - 589.92
    * - 150
      - 477.27
      - 
      - 500
      - 596.29

Se puede observar que conforme t aumenta la cantidad de sal depositada
alcanza un límite de :math:`A=600kg`, por lo tanto, calculamos el límite
de :math:`A(t)` para cuando :math:`t \implies \infty`:

.. math::

   lim_{t \to \infty} A_{(t)} = lim_{t \to \infty} \left( 600 - 550 ·
   e^{\frac {-t}{100}} \right) = 600 - \frac {500}{\infty} = 600


.. admonition:: Respuesta final

   La cantidad de sal en un período largo de tiempo tiende a 600kg


Vemos que el gráfico de :math:`A(t)` nos muestra la misma tendencia:

.. raw:: html
   :file: _static/graph-2.html


Desarrollo (Parte B)
~~~~~~~~~~~~~~~~~~~~

Por último, se pide lo siguiente:

  ¿Cuánta sal se depositará en en el tanque si el flujo de entrada
  de la salmuera fuera mayor que el flujo de salida de la mezcla?

En el análisis que conduce a la ecuación :math:numref:`ec-dif-mod-mat` se tomo
que :math:`r_{entra} = r_{sale}` (es decir, que la tasa de entrada y salida de
líquido era la misma), pero esta relación puede ser de 3 formas:

#. :math:`r_{entra} = r_{sale}`
#. :math:`r_{entra} > r_{sale}`
#. :math:`r_{entra} < r_{sale}`

Para este caso, la forma a tomar es de :math:`r_{entra} > r_{sale}`.

Entonces supongamos que la solución mezclada se bombea hacia afuera con una
tasa de flujo de mezcla más lenta de :math:`2 litro/minuto`, por lo que se
acumulará en el tanque con la razón
:math:`r_{entra} - r_{sale} = (3-2) litro/minuto = 1 litro/minuto`.

Si evaluamos el líquido dentro del tanque después de :math:`t` minutos será:
:math:`1 \frac {litro}{minuto} · t · minuto = t · litro`

Vemos que la cantidad de fluido incrementa con el tiempo, por lo que
modificará :math:numref:`def-concentracion-tanque` y se vuelve a definir
:math:`c_{(t)}` como:

.. math::
   :label: def-concentracion-tanque-nueva

   c_{(t)} = \frac { A_{(t)} }{300 + t} \frac {kg}{litro}

Esto también obliga a reescribir :math:numref:`def-r-sale`:

.. math::

   R_{sale} = c_{(t)} · r_{sale} = c_{(t)} · 2 \frac {litro}{minuto}

Reemplazamos la definición de :math:`c_{(t)}`:

.. math::
   :label: def-r-sale-nueva

   R_{sale} = \frac { 2 A_{(t)} }{300 + t} \frac {kg}{minuto}

.. admonition:: Modelo matemático (nuevo)

   La ecuación diferencial :math:numref:`ec-dif-mod-mat` ahora es

   .. math::
      :label: ec-dif-mod-mat-nueva

      \frac {dA}{dt} + \frac { 2 A_{(t)} }{300 + t} = 6

Aplicando el mismo método de resolución, vemos que su factor integrante es:

.. math::

   u_{(t)} = e ^ {\int \frac {2}{300 + t} dt}

.. math::
   :label: factor-integrante-nuevo

   u_{(t)} = (300 + t)^2

Luego multiplicamos ambos miembros de :eq:`ec-dif-mod-mat-nueva` por el
factor integrante:

.. math::

   \frac {dA}{dt} · u_{(t)} + \frac { 2 A_{(t)} }{300 + t} u_{(t)} = 6 u_{(t)}

.. math::

   \frac {dA}{dt} · (300 + t)^2 + \frac { 2 A_{(t)} }{300 + t} (300 + t)^2 = 6 (300 + t)^2

.. math::

   \frac {dA}{dt} · (300 + t)^2 + 2 A_{(t)} · (300 + t) = 6 (300 + t)^2

Vemos que el primer miembro se puede reescribir de la siguiente manera:

.. math::

   \frac {d}{dt} (A_{(t)} · (300 + t)^2) = 6 (300 + t)^2

Integramos ambos miembros:

.. math::

   A_{(t)} · (300 + t)^2 = 6 \int (300 + t)^2 dt

   A_{(t)} · (300 + t)^2 = 2 (300 + t)^3 + C


.. admonition:: Solución general (nueva)

   Despejando :math:`A(t)`, obtenemos la **solución general**

   .. math::
      :label: solucion-tanque-general-nueva

      A_{(t)} = 600 + 2t + C · (300 + t)^{-2}

Resolviendo para :math:`A(t=0) = 50`:

.. math::

   50 = 600 + 0 + C · (300 + 0)^{-2}

.. math::

   -550 · 300^2 = C

.. math::

   C = - 4.95 · 10^7


.. admonition:: Solución particular (nueva)

   Reemplazamos :math:`C`  en :math:numref:`solucion-tanque-general-nueva` y
   obtenemos la **solución particular**

   .. math::
      :label: solucion-tanque-particular-nueva

      A_{(t)} = 600 + 2t - 4.95 · 10^7 · (300 + t)^{-2}

Graficamos esta solución particular y su correspondiente campo vectorial
de la solución general.

.. raw:: html
   :file: _static/graph-2b.html

Como era de esperar, se muestra que con el tiempo se acumula la sal en el
tanque. Si calculamos su límite:

.. math::

   lim_{t \to \infty} A_{(t)} = lim_{t \to \infty} \left( 600 + 2t - 4.95 ·
   10^7 · (300 + t)^{-2} \right) = 600 + \infty + 0 = \infty


.. admonition:: Respuesta final

   La cantidad de sal en un período prolongado de tiempo tiende a infinito
   cuando el flujo de entrada de la salmuera es mayor que el flujo de salida
   de la mezcla.

|
|
|
