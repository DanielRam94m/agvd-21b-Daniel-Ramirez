## Reporte 19 se Septiembre
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
## Resumen de los temas estudiados (1 pto)
### 1. Transformación de Datos

##### 1.1 Generalidades de los data sets
Un **dataset** es una coleccón de objetos de datos.

**Tipos de Data sets:**
Existen distintos tipos de data sets:
**Según su forma y contenido:**
>> * **Record Data:** Los datos de registro son los más comunes en los data sets.
>> * **Graph Based Data:** ~1~Cuando existen relaciones entre los objetos ~2~Cuando los datos son grafos
>> * **Ordered Data:** Están los de tipo ~1~*temporal*, los de tipo ~2~*secuencial*, los de ~3~*serie de tiempo* y los de tipo *espacial*.

Los data sets cuentan con distintas características:
>> * **Dimensionalidad:** Que corresponde a la cantidad de columnas del dateset.
>> * **Dispersión:** (o sparcity). Corresponde a la característica de que existan valores más frecuentes que otros.
>> * **Resolución:** Se refiere a la precisión de los valores para describir cada registro.

##### 1.2 Atributos
    
El **Atributo:** corresponde a una propiedad o característica que puede cambiar

**Tipos de Atributos:**

**Categóricos o Cualitativos:**
>> **Nominal:** Valores que proveen solo la información suficiente para diferenciar unos de otros.
>> **Ordinal:** Proveen suficiente información para ordenar los valores de estos.

**Numéricos o Cuantitativos:**
>> **Intervalo:** En estos las diferencias entre los valores son significativos.
>> **Radio:** En estos, tanto las direrencias como la proporción son significativos.
    
##### 1.3 Formas de trabajar los datos
Es importante trabajar con los datos para así incrementar su utilidad o mejorar el valor de estos.

Formas que existen para trabajar con los datos:
>> * **Agragación:** Aveces es posible combinar dos o más objetos en un solo (menos es más). Esto nos da ventajas como ~1~hacer menos uso de la memoria, ~2~usar menos tiempo en procesamiento y ~3~tenemos el cambio de escala, alto nivel vs bajo nivel. Pero como desventaja tenemos ~1~la pérdida de detalles.
>> * **Muestreo:** Consiste en un subconjunto del total existente. Se busca que esta sea *representativa*.
>> Existen varios tipos de muestreo:
>> Tenemos el ~1~**muestreo aleatório sin reemplazo** en el que la probabilidad de selección cambia con el tiempo (si sale se aparta del conjunto). temos el ~2~**muestreo aleatório con reemplazo** en el que la probabilidad de selección se mantiene siendo la misma durante todo el muestreo (ya que al salir un valor, este no se aparta del conjunto o es reemplazado con uno igual a este). En el ~3~**muestreo estratíficado** dado que existen valores o poblaciones menos representadas que otras, es necesario tomar una decisión para representarlas, esta decisión puede ser seleccionar ~3.a~**igual cantidad** de representantes para cada uno, o bien seleccionar una ~3.b~**cantidad proporcionas** al tamaño de cada grupo. En el ~4~**muestreo progresivo** (o muestreo adaptativo) consiste en iniciar con una muestra pequeña que irá aumentando y que gracias a una estrategia evaluar la efectividad del tamaño.
>> * **Reducción de dimensionalidad:** Busca eliminar los elementos del data set que bien o son poco relevantes, o agregan ruido, o teiene una gran correlación o que al estar un elemento duplicado impacte en el valor de nuestro ci¿onjunto. Esto nos permite usar algoritmos que trabajen mejor con baja dimensionalidad, mejora la observación e interpretación de los conjuntos, y además consumir menos memoria y tiempo de procesamiento.
>> Para reducir dimensionalidad podemos hacer uso de la técnica de **Principal Component Analysis (PCA)** que es una técnica de álgebra lineal de gran utilidad para conjuntos de gran dimensionalidad.
>> * **Selección de Atributos:** Este consiste en eliminar atributos irrelevantes o redundantes para lo que tenemos varias técnicas:
>> En el ~1~**weighting** se les asigna un mayor peso a los atributos más importantes según valoración del dominio o de forma automática utilizando modelos como por ejemplo la *Máquina de Soporte Vectorial*. Tenemos el ~2~**embedded** en el que un algoritmo de análisis de forma automatizada decide cuales atributos conservar y cuales eliminar del conjunto. Con ~3~**filter** en el que se verifica uno por uno cuales atributos son menos relevantes. Finalmente tenemos el ~4~**wrapper** en el que de manera estocástica o heurística se busca encontrar el mejor conjunto utilizando algoritmos de análisis como caja negra.
>> * **Creación de Atributos:** Con esta técnica, se crean nuevos atributos basados en atributos ya existentes.
>> Tenemos también por un lado la **binarización de atributos** en el que valores ya sean continuos o discretos son transformados en valores binarios y tenemos la **discretización de atributos** en donde valores continuos se transforman en valores categóricos de igual tamaño e igual frecuencia. Ambos muy útiles de usar con algoritmos clasificadores.
>> * **Transformaciones:** Cuando aplicar a todos los valores cierta operación nos agrega valor o es necesario para obtener un valor. Esto nos permite por ejemplo *normalizar los datos*, o bien para *estanderizar los datos*.

### 2. Conceptos Sobre Modelado
En *Machine Learning* temenos los conceptos de Algoritmo de ML y de Modelo de ML. Por un lado el **Algoritmo de ML** consiste en un procedimiento que reconoce patrones, aprende o se ajusta a un conjunto de datos para obtener un modelo de ML. Por otro lado un **Modelo de ML** consiste en un conjunto de reglas, números y estructuras generadas por un algoritmo de ML para hacer predicciones y que puede ser guardado y utilizado en el futuro. 
Entre los tipos de aprendizaje podemos encontrar la **clasificación** en la que se predice una clase binaria o multiclase. Y bien tenemos también **regresión** en el que se busca predecir un valor numérico.

### 3. Construyendo Modelos
Un **modelo** resume resume información de una herramienta que representa de forma más simple el mundo real y que permite hacer predicciones y pronósticos.
Para construir un modelo es conveniente empezar simple y aumentar complejidad 
Es necesario **ajustar** o hacer **fitting** en nuestros modelos con respecto a los datos de entrenamiento. Para esto es necesario estimar los parámetros que nos genere mejores resultados al momento de testeo (más importante que los resultados al momento de entrenamiento) y para esto existen algunos métodos disponibles para aplicar.
Es necesario tener cuidado con los ajustes de parámetros. Por un lado un entrenamiento muy ajustado al conjunto de entrenamiento a pesar de dar resultados de clasificación perfectos o muy cercanos al 100% de predicción puede no ser una buena noticia si esto se debe a un **sobreajuste** o **overfitting** que al ser aplicado al conjunto de prueba o incluso al mundo real, sea muy malo prediciendo, o que bien por otro lado haya un **infraajunte** o **underfitting** en el que no haya suficiente conocimiento para poder realizar clasificaciones.

**Diferentes Tipos de Modelos:**
>> * **Modelos Lineales:** calculan sumas ponderadas de variables en el que cada variable característica se multiplica por un coeficiente. Estos modelos son fácilmente comprensibles, generalmente defendibles y fáciles de construir.
>> * **Modelos No Lineales:** estos pueden ofrecer un ajuste mucho mayor, pero a la vez es más difíciles de encontrar los coeficientes adecuados (el mundo usualmente no es lineal)
>> * **Modelo de Caja Negra:** pueden llegar a ser estremadamente efectivos, puede llegar a realizar tareas que antes no eran posibles, pero no nos comunica el por qué. 
>> * **Modelo Descrptivo:** Estos se basan en teorías bien desarrolladas y nos muestran como es el proceso de decisión.
>> * **Modelo de Primer Principio:** Se basa en el principio de como funciona algo (como por ejemplo algún área matemática) o basado en la heurística.
>> * **Modelo Basado en Datos:** Este se basa en correlaciones que se lograron observar entre los parámetros de entrada y las variables de resultado y que se puede realizar sin entender el dominio.
>> * **Combinación de Modelo de Primer Principio y Modelos Basado en Datos:** Hace uso del conocimiento del dominio para afinar el modelo y también usa los datos para mejorar el ajuste y la evaluación.
>> * **Modelo Estocástico:**  es un modelo aleatoriamente determinado agregando un valor probabilístico al modelo lo que proporciona un acercamiento al comportamiento del mundo real. 
>> * **Modelo Determinista:** estos son fáciles de implementar y de debuguear. Se basan en leyes o comportamientos conocidos.
>> * **Modelo Plano:**
>> * **Modelo Jerárquico:** estos dividen modelos en submodelos en una forma más clara. Para estos se necesitan datos apropiados para cada submodelo, además de ser más complejos de construir. Un modelo que no usa una estructura de este forma se considera **Modelo Plano**.
>> Los modelos clasificadores generan una **matriz de confusión** cuyos campos de definen como **verdaderos positivos (TP)** que consisten en valores que originalmente son positivos y en efecto fueron clasificados como positivos, en **verdaderos negativos (TN)** en los que valores negativos fueron en efecto clasificados como negativos, en **falsos positivos (FP)** cuando objetos que originalmente eran negativos pero fueron clasificados como positivos y **falsos negativos (FN)** para los casos en que el objeto fue clasificado como negativo cuando originalmente este esta positivo.
>> Esta matriz de confusión nos permite obtener valores para evaluar los modelos como lo son la **exactitud** (o accuracy) que se calcula con (TP+TN)/(TP+TN+FN+FP), la **precisión** que se calcula como (TP)/(TP+FP), el **retirada** (o recall) que se calcula con el (TP)/(TP+FN) y el **F-score** que es muy utilizado al usar los cuatro valores de la matriz de confusión y que se calcula como 2*(precision*recall)/(precision+recall).

## Comentarios sobre algo aprendido (1 pto)
* Aprendí de la existencia de distintos tipos de datasets y de formas de trabajarlos.
* Aprendí de la existencia de varios tipos de categorías de modelos o de clasificaciones de estos que no conocía, de sus aplicaciones, sus beneficios y sus desventajas de aplicación.

## Dudas sobre la materia estudiada (1 pto)
* No estoy del todo seguro si entendí en qué consisten los *modelos determinísticos* y su diferencia con los *modelos estocásticos*
* Me gustaría entender mejor en forma práctica como aplicar un modelo de *regresión* a un caso de conjunto de datos real.
* Me gustaría poner en práctica una *reducción de dimensionalidad* con distintas de las técnicas para poder tener un mejor acercamiento y comprensión del tema.

## Posible uso que usted le dará a esta materia como profesional (1 pto)
En mi futuro laboral quiero trabajar en áreas relacionadas a la Ciencia de Datos y poder trabajar con conjuntos de datos y editarlos para agregarles valor y con base a estos y a los objetivos poder escoger los modelos más apropiados me serán de gran utilidad. Con esta materia me gustaría poder tomar decisiones de valor para obtener predicciones y generar los productos más útiles para su uso.

## Mencione cualquier material que utilizó como referencia para el aprendizaje (1 pto)
Referencias
* Shin, T. (2020, October 17). All Machine Learning Models Explained in 6 Minutes - Towards Data Science. Medium. https://towardsdatascience.com/all-machine-learning-models-explained-in-6-minutes-9fe30ff6776a
* Shung, K. P. (2020, April 10). Accuracy, Precision, Recall or F1? - Towards Data Science. Medium. https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9

