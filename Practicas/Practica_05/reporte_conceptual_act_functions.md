## Reporte sobre Cómo Escoger una Función de Activación para Deep Learning
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
### 1. Resumen del tema tratado
La **función de activación** corresponde a la suma ponderada de los pesos en la entrada de una neurona que se transformarán en la salida de uno o varios nodos en la capa de la red. Es por esto de la importancia de cual función de activación es utilizada ya que tiene un impacto directo en el rendimiento y la capacidad de la red neuronal. Es también importante decir que en distintas partes del modelo se puede utilizar distintas funciones de activación, pero típicamente todas las capas ocultas de una red suelen usar la misma función de activación y la capa de salida típicamente usará una función de activación distinta a la de las capas internas en la que dicha función de activación dependerá del tipo de predicción requerido por el modelo.

#### **Activación para Capas Ocultas** 
Normalmente en las capas ocultas se suelen utilizar funciones de activación no lineales, esto con el fin de aprender funciones más complejas que si se usaran funciones lineales.

Tres funciones de activación que pueden ser consideradas de usar con capas ocultas son: 
* Rectified Linear Activation (ReLU)
* Logistic (Sigmoid)
* Hyperbolic Tangent (Tanh)

NOTA: Estas no es toda la lista de funciones de activación disponibles, pero son las más usadas.

**ReLU Hidden Layer Activation Function** es la función de activación más utilizada para capas ocultas. Esta es sencilla de implementar y eficaz para superar las limitaciones de otras funciones de activación como las de Sihmoid y Tahn, esto porque es menos suceptible a los gradientes de fuga que impiden el entrenamiento de modelos profundos. Sin embargo este puede sufrir otros problemas como por ejemplo las unidades saturadas o muertas.

**Sigmoid Hidden Layer Activation Function**, también llamada la función logística es la misma función utilizada en el algoritmo de clasificación de regresión logística. Toma valores entre 0 y 1, entre más cerca se encuentre de 1.0 su salida será 1.0 y entre más cerca esté es 0.0 su salida será 0.0. Su señal de activación se llama por medio de la función `1.0 / (1.0 + e^-x)`.

**Tanh Hidden Layer Activation Function** también llamada como la función tangencial, toma valores entre -1 y 1 donde entre más positivo es el número, la salida será 1.0 y entre más negativo la salida será 0.0. Su señal de activación es `(e^x – e^-x) / (e^x + e^-x)`.

#### **Activación para Capas De Salida** 
Entre la lista de funciones de activación que pueden ser utilizadas por las capas de salidas, 3 opcines interesantes y las más usadas son:
* Linear
* Logistic (Sigmoid)
* Softmax

**Linear Output Activation Function**, llamada también la función identidad (entity) o de no activación (no activation). Esta no altera la suma de los pesos que recibe y en su lugar lo retorna directamente.

**Sigmoid Output Activation Function** corresponde a la misma recomendada en las capas ocultas y descrita anteriormente.

**Softmax Output Activation Function**, este puede interpretarse como probabilidades de pertenencia a una clase. Esta función se calcula mediante `e^x / sum(e^x)`.

#### Escoger la función de activación para la capa de salida:
Si su problema es un problema de regresión, debe utilizar una función de activación lineal:
* Regression: One node, linear activation.

Si su problema es un problema de clasificación, existen 3 posibilidades:
* Binary Classification: One node, sigmoid activation.
* Multiclass Classification: One node per class, softmax activation.
* Multilabel Classification: One node per class, sigmoid activation.

### 2. Comentarios sobre algo aprendido
Nunca había considerado de que las funciones de activación fueran distintas y que estas dependieran de la naturaleza del modelo, tampoco que estas fueran distintas entre las capas ocultas y las de salida. Además me parece súper necesario el conocimiento de las consideraciones para seleccionar la función de activación adecuada.

### 3. Dudas sobre el tema tratado
En cuanto a las funciones de activación para las capas internas me surgió una duda con respecto a lo que es una Red Neuronal Recurrente que es para las que se recomiendan las funciones de activación de Sigmoid Activation y Tahn Activation. Esta sería mi única duda, lo demás me pareció muy claro.

