## Reporte sobre Multi Layer Perceptron
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
### 1. Resumen del tema tratado
Se puede ententender como **perceptrón** al modelo de una sola neurona que es parte de redes neuronales más grandes.

Las **redes neuronales** poseen un gran valor dado a su capacidad de aprender lo que representan sus datos de entrenamiento y su mejor relación con la variable de salida. Estas aprenden por medio de mapeo en las que estas por medio de sus estructuras jerárquicas o multicapa poseen la habilidad de aprender.

La **neurona** corresponde a la unidad básica de conformación de las redes neuronales. Estas unidedes computacionales reciben un peso y por medio de una **función de activación** producen un resultado (salida).

El **peso de las neuronas** poseen un **sesgo** que corresponde a una entrada que siempre vale 1.0 y que también debe ser pesado; de esta forma, si la neurona tiene una cantidad *n* de entredas, esta pesará un total de *n+1* ya que se toma en cuenta el sesgo. Además es importate mencionar que los pesos de las neuronas son iniciados con valores aleatorios pequeños que serán modificaos en cada época. Además dado que pesos grandes en las neuronas causan mayor fragilidad y complejidad es que se prefieren mantener pesos pequeños utilizando **funciones de regularización**.

Los pesos son sumados y pasados a trevés de **funciones de activación**. Esta sumará las entradas sumadas a su salida y producirá una fuerza de señal que producirá la activación o no activación de esta, esto dado un **threshold** (por ejemplo 5.0) en el que si es mayor a este la salida será 1.0 o en caso contrario será un 0.0.

Las **redes de neuronas** pueden estar conformadas por varias **capas *(layers)*** donde cada capa corresponde a una fila de neuronas.

La **topología de una neurona** corresponde a la arquitectura o patrón que conforma a esta.

En cuanto a las capas, estas se pueden clasificar en 3 tipos:
* La **capa de input o (capa visible)** corresponde a las entradas provenientes desde el dataset (aunque estas en sí no son neuronas sino entradas).
* Las **capas ocultas** corresponden a las capas de neuronas entre la capa entrada y la de salida.
* La **capa de salida** están conectadas a la última capa oculta y están encargadas de la salida de un valor o de un vector de valores que responden al problema.

Las redes neuronales necesitan de valores numéricos, así que los datos categóricos deben ser modificados a alguna especie de representación numérica. A esta acción de transformar variables categóricas a una representación numérica se le conoce como ***one hot encoding*** y se da en la fase de **preparasión de datos** previa al entrenamiento.

Finalmente y como se mencionó antes, es importante en cada época ir reajustando los valores de los pesos para que estos se acerquen lo mejor posible a producir el comportamiento esperado de la red neuronal.

### 2. Comentarios sobre algo aprendido
Este tema ya lo había estudiado por cuanta propia antes, mas no sabía que la capa de entrada también podía ser llamada como capa visible, lo cual tiene mucho sentido ya que de las capas requeridas para producir la capa de resultado es la única que antes que eso suceda en que podemos apreciar valores sin necesidad de funciones adicionales.

### 3. Dudas sobre el tema tratado
Creo que entiendo cuanto al one hot encoding el como funciona con variables categóricas de 3 o más valores, sin embargo, no estoy seguro si el one hot encoding es algo de lo que me deba encargar yo o de si es algo que ya en sí existe alguna función que realice esta tarea por mi.


