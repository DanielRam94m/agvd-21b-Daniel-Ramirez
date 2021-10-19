## Reporte 03 de Octubre
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
### 1. Resumen de los temas estudiados (1 pto)
#### &emsp;1.1 Regresión Logística y Redes Neuronales
##### &emsp;&emsp;1.1.1 Modelos Lineales
En cuanto este tipo de modelos, no es recomendable su uso para problemas de baja dimensionalidad, en especial si existen más atriburos que filas (estos funcionan mejor con problemas de alta dimensionalidad).

Estos modelos buscan buscas minimizar un error (loss) por medio de coeficiente *w* y *b*. Una de las funciones de costo más utilizadas es la del **MSE** (error cuadrático medio).

Los Modelos Lineales son sensibles a la escala de los atributos y al igual que algunos otros modelos, estos aplican **técnicas de regularización** que consiste en la penalización a la complejidad del modelo.

##### &emsp;&emsp;1.1.1 EL Perceptrón
Este contiene un umbral (threshold) θ

##### &emsp;&emsp;1.1.1 Regresión Logística
Este consite en un algiritmo de clasificación binaria. Este tiene mejor desempeño en presencia de alta dimensionalidad y para clasificar utiliza una línea en el caso de estar trazado en dos dimensiones, un plano en el caso de estar trazado en tres dimensiones y un hiperplano en el caso de cuatro dimensiones o más.

##### &emsp;&emsp;1.1.1 Redes Neuronales
Pueden considerarse como una generalización de los modelos lineales, solo que estos utilizan niveles de procesamiento para tomar decisiones (más de un perceptrón) y se caracterizan por su capacidad de parender funciones mucho más complejas que los modelos lineales.

Las Redes Neuronales funcionan con coeficientes los cuales trabajan con los valores de los nodos que fueron escogidos más los pesos en las aristas que conectan a estos nodos. En cada uno de los nodos se aplica una función no lineal.

Para estos modelos contamos con los hiperparámetros de:
* Número de capas ocultas
* Número de nodos en las capas ocultas
* La función de activación en los nodos
* Los parámetros de optimización (L1, L2, Elastic) y el learning rate
* Los pesos iniciales de la red, el mecanismo de kernel

**Importante:** Que los atributos tengan escales similares (e.g. media 0 y varianza 1)

#### &emsp;1.2 Máquinas de Soporte Vectorial (SVM)
En estos se busca trabajar con el equilibrio entre el sesgo y la varianza. En estos se busca trazar un ***threshold*** justo en el medio entre ambos cunjuntos y a la distancia más corta entre las observaciones más cercanos de ambos conjuntos y el *threshold* se le conocerá como el margen y lo que se busca es el ***maximal margin classifier*** (margen clasificador maximal) correspondiente a la mayor distancia posible entre las observaciones más cercanas de ambos conjuntos y el *threshold*. Sin embargo los *maximal margin classifiers* son muy sensibles a los outliers y para estos casos será necesario permitir clasificaciones erroneas (***misclassifications***), consistiendo esto en un ejemplo de ***bias/variance tradeoff*** (equilibrio entre el sesgo y la varianza) en uso en la SVM. A este caso de permitir clasificaciones erroneas se le conoce como ***soft margin*** y podemos saber si un *soft margin* es mejor que otro al hacer uso de ***cross validation*** para determinar cuantas clasificaciones erroneas y la calntidad de observaciones permitir dentro del *soft margin* y así obtener mejores clasificaciones.

Al usar *soft margin* para encontrar la ubicación del *theshold* entonces estaremos usando un ***soft margin classifier*** (un ***support vector classifier***) para clasificar observaciones. En estos casos, a las observaciones en los extremos y dentro del *soft margin* se les conoce como ***support vectors*** o vectores de soporte.

Entonces tenemos que los *support vector classifiers* permiten *outliers* y permitir *misclassifications* para poder a largo plazo tener mejores predicciones.

En el caso de las ***support vector machines*** la idea es:
1. Empezar con datos en una relativa baja dimensión
2. Mover los datos a una dimensión mayor
3. Encontrar el *support vector classifier* que separe a los dos grupos en mayor dimensión. Para este cambio de una dimensión a otra mayor la *SVM* usa una función de kernel para de forma sistemática encontrar *support vector classifiers* en dimensiones mayores. La función de kernel no hace en realidad un cambio de dimensión, sino que calcula la correlación entre cada una de las observaciones con todo el resto de las observaciones como si estuviesen en una dimensión mayor. A esta acción de calcular las correlaciones como si estuvieran en una dimensión mayor se le conoce como ***kernel trick*** o truco de kernel que reduce el poder computacional requerido para transformar datos de una dimensión a otra

### 2. Comentarios sobre algo aprendido (1 pto)
Tanto las Máquinas de Soporte Vectorial como las Redes Neuronales son modelos con los que he trabajado antes, o que bien es estudiado. En el caso de la Máquina de Soporte Vectorial la utilicé tanto en el corso de Inteligencia Artificial como en el de Diseño de Experimentos y para ello tuve que estudiar los conceptos relacionados a este modelo. Por otro lado, en el caso de la Red Neuronal, este modelo lo estidié de forma conceptual e hice un pequeño ejemplo que busqué por cuenta proria, sin embargo, en este caso sí aprendí más acerca de los hipermarámetros con que estos cuentan y que deben ser tomados en cuenta tanto en su uso como para entender un poco mejor su funcionamiento.

### 3. Dudas sobre la materia estudiada (1 pto)
Dado que son temas con los que ya me sentía familiarizado, en este caso no tengo ninguna duda al respecto, pero si me gustaría trabajar más con el modelo de Red Neuronal y así ir agarrando más práctica y mejores destrezas a la hora de trabajar con estos modelos.

### 4. Posible uso que usted le dará a esta materia como profesional (1 pto)
Para mi futuro profesional, el poder escoger entre un modelo y otro es de suma importancia, por ello el tener estos conocimientos brindados por estos materiales me serán de gran utilidad y medir según la naturaleza de mi problema si es mejor utilizar una red neuronal, una máquina de soporte vectorial o bien obtar por alguno de los otros modelos que conozco.

### 5. Mencione cualquier material que utilizó como referencia para el aprendizaje (1 pto)
* Berrocal Rojas, A. (2021, October 8). Redes Neuronales Análisis de grandes volúmenes de datos [Slides]. Logistic Regression y RN. https://mv1.mediacionvirtual.ucr.ac.cr/pluginfile.php/1915451/mod_resource/content/1/Logistic%20Regression%20y%20RN.pdf
* Brownlee, J. (2020a, August 15). Crash Course On Multi-Layer Perceptron Neural Networks. Machine Learning Mastery. https://machinelearningmastery.com/neural-networks-crash-course/
* Brownlee, J. (2020b, August 21). Cost-Sensitive SVM for Imbalanced Classification. Machine Learning Mastery. https://machinelearningmastery.com/cost-sensitive-svm-for-imbalanced-classification/
* Brownlee, J. (2021, January 21). How to Choose an Activation Function for Deep Learning. Machine Learning Mastery. https://machinelearningmastery.com/choose-an-activation-function-for-deep-learning/
* J. [Starmer]. (2019, September 30). Support Vector Machines Part 1 (of 3): Main Ideas!!! [Video]. YouTube. https://www.youtube.com/watch?v=efR1C6CvhmE
***