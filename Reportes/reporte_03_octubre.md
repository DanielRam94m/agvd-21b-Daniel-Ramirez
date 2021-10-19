## Reporte 03 de Octubre
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
### 1. Resumen de los temas estudiados (1 pto)
#### &emsp;1.1 Construyendo Modelos
En cuanto al **Análisis Exploratorio de Datos** (*EDA* por sus siglas en inglés) consiste en analizar e investigar los conjuntos de datos con que se van a trabajar y de esta manera tener una mejor noción de como manipular los datos de la mejor manera posible.

Los **modelos** buscan por medio de una herramienta representar al mundo real de la mejor manera posible buscando que este sea lo suficientemente bueno para pronosticar y hacer predicciones que permitan tomar decisiones o sacar conclusiones.

Algunas veces ciertos comportamientos de distribución nos ayudan a tener imformación importante de los datos ya que existen ciertas distribuciones son un patrón muy común en la naturaleza como por ejemplo la *distribución normal*.
![image01](./Images/Reporte03_imagen01.png)*Figura 1: Algunas distribuciones comunes en la naturaleza*

Una vez ya se ha decidido el modelo, es necesario ajustar los parámetro para el modelo, lo que suele utilizar métodos optimizadores y algoritmos y para esto existen muchos métodos ya diseñados que puedo utilizar. En estos casos suele ser mejor modelos simples y con menor cantidad de parámetros que modelos complejos y con gran variedad de parámetros, aumentando la posibilidad de variables que generen ruido y además haciendo los modelos mucho más pasados de entrenar, reduciendo así eficiencia y eficacia. Eso sí, sin caer en hacer modelo muy simple al punto en que más bien se reduzca su rendimiento.

Por un lado en los modelos tenemos el **sesgo** (o ***bias*** en inglés) que se introduce al tomar supuestos incorrectos e incorporarlos al modelo. **Errores de sesgo** harán que mis modelos están infraajustados.

Por otro lado tenemos la **varianza** que es la sensibilidad de los modelos a los cambios o fluctuaciones. **Errores de varianza** generará modelos sobreajustados.

Existen distinas formas de clasificar los modelos. Estas formas de clasificarlos pueden ser:
* Lineales vs No Lineales
* Caja Negra (Blackbox) vs Descriptivos
* Primer Principio (First Principle) vs Basados en los Datos (Data Driven)
* Estocásticos vs Deterministas
* Planos (Flat) vs Jerárquicos

Para evaluar los modelos es recomendable:
* Contruir un ambiente razonable para evaluación del modelo.
* De ser posible automatizar la evaluación del modelo.
* Generar reportes (para esto puedo hacer uso de gráficos y resúmenes. estadísticos).
* Separar e identificar los datasets de **entrenamiento**, de **validación** y de **prueba**.
* Tener cuidado a la hora del muestreo de los datasets.
* Si el dataset es algo pequeño, una opción para poder compenzar es usar la **validación cruza (cross-validation)**.

Para medir qué tan bien se comportan nuestros modelos podemos usar distintas técnicas. Por ejemplo si nuestros modelos son clasificadores binarios o clasificadores multiclase, podemos usar la matriz de **confusión (confusion matrix)** en la que podemos usar funciones como ***accurracy***, ***precision***, ***recall*** o ***F-score***. Por otro lado para los predictores de valores numéricos podemos ver qué tan precisa fue la predicción utilizando funciones para el calculo ya sea del **error absoluto**, el **error relativo** o el **error cuadrado (squared error)**. O bien se puede hacer uso de los ***baseline models*** que son modelos ya existentes y que se conoce de su desempeño y comparar nuestro modelo y verificar si lo mejora o no. 

#### &emsp;1.2 Árboles de Decisión
Los árboles de decisión funcionan de forma jerárquica, donde en cada nodo se toma una decisión de qué ruta tomar de acuerdo a una condición. Las hojas de estos modelos corresponderán a la clasificación que la instancia recibirá acorde al algoritmo del árbol de decisión.

Los árboles de decisión cuentan con ciertas ventajas y desventajas.

|Ventajas|Desventajas|
|---|---|
| 1. Son simples de interpretar | 1. Es sensible a los pequeños cambios en el dataset |
| 2. No son sensibles a los datos faltantes | 2. Cuando los árboles son muy grandes, estos se vuelven difíciles de interpretar |
| 3. No es sensible a la no normalización ni estandarización de los datos | 3. Por la naturaleza de estos, los árboles más profundos son los más efectivos |
| 4. Puede trabajar con valores tanto categóricos como numéricos| 4. En la práctica tienden a hacer overfitting pese a las estrategias |
| 5. Los algoritmos de entrenamiento son eficientes||
| 6. Con el uso de parámetros es posible prevenir el overfitting||

##### &emsp;1.2.1 RandomForest
Los **RandomForest** corresponden a un conjunto de árboles ligeramente distintos y si bien individualmente puede que estos generen overfitting, estos deben tener una buena predicción y con estos se saca un promedio de las predicciones del **bosque**.

Para generar los árboles para un RandomForest existen dos estrategias:
* Selección de observaciones
* Selección de atributos para cada **split**

También se puede seguir algunos pasos y aplizar ciertas estrategias para cada paso:
1. Elegir una cantidad de árboles para el bosque: para esto se puede usar `n_estimators`
2. Extraer muestras aleatórias del dataset para construir cada árbol: se puede usar `n_samples`
3. En cada nodo evaluar cierta catidad de fetures para el split: se puede usar `max_features`
4. Para casos de clasificación utilizar ***soft-voting***, cada árbol predice una probabilidad para cada clase. Para estos caso usar `max_features = sqrt(n_features)`
5. Para los casos de regresión, se promedian las predicciones de todos los árboles. Para estos casos utilizar `max_features = log2(n_features)`

Entre sus ventanas y desventajas tenemos:
|Ventajas |Desventas|
|---|---|
| 1. Suelen tener mejores resultados |1. No son fáciles de interpretar como lo es un solo árbol |
| 2. El bosque suele tener menos overfit que cualquier árbol individual | 2. cambio de random_state puede producir modelos muy distintos (entre más árboles más robusto respecto de random_state) |
|3. No necesita de mucho reafinamiento de parámetros para su correcto funcionamiento | 3. En grandes conjuntos de datos el procesamiento es lento y consume mucha memoria |
| 4. No requiere de cambio de escala de los datos | 4. No funcionan bien en datos dispersos (sparse) de alta dimensionalidad como texto|
| 5. Se puede paralelizar en procesadores multi-core ||

##### &emsp;1.2.2 GradientBoosting
En estos los árboles trabajan de forma secuencial (uno tras otro), esto para que cada árbol intente de corregir el error del árbol anterior y en estos no hay aleatoriedad de su construcción y su algoritmo suele ser *greedy*.

Para estos se suele pretender que sus áboles sean pequeños (4 - 8  niveles). Suelen ser más sensibles a los parámetros que los random forest

|Ventajas|Desventajas|
|---|---|
| 1. Suelen ser más rápidos que los random forest (depende del caso pueden tener mejores resultados) | 1. requieren de un apropiado **tuning** de parámetros|
| 2. Son robustos a escala de los datos y atributos | 2. Suelen tardar más tiempo en entrenarse |
|| 3. No tienen buen rendimiento frente a datos dispersos y de alta dimensionalidad (ej. Texto) |

#### &emsp;1.3 Estategias de Entrenamiento
* Train_test_splits: Estos son muy sensibles dado que un simple split puede significar el clasificar mal una instancia, además de no haber garantía de la representatividad de cada conjunto.
* Cross-validation: Este consiste en particionar un datasets en n subsets, estos disjuntos entre sí, y son respecto a estos, se entrenan n modelos tomando n-1 subconjuntos para entrenar cada modelo y dejando 1 subset aparte para la validación de cada modelo. Para estos debe de esperarse o buscarse que cada clase a clasificar esté bien representada. 

### 2. Comentarios sobre algo aprendido (1 pto)
Aprendí del funcionamiento de los random forest lo que me parece ser un modelo interesante para empezar a experimentar con él.
Aprendí que siempre es necesario realizar estudios no solo sobre mis datos, sino también sobre los modelos procurando usar las herramientas más adecuadas para esto según las características de todo lo que involucra la creación de mis modelos ya que muchas veces no solo se trata de que mi modelo funcione, sino también poder justificar el comportamiento y las decisiones tomadas (esto también con el tiempo a ser cada vez mejor seleccionando mis modelos).

### 3. Dudas sobre la materia estudiada (1 pto)
No recuerdo bien del concepto de greedy, por lo que lo relacionado con esto me generó algo de dudas, por lo que buscaré información al respecto.

### 4. Posible uso que usted le dará a esta materia como profesional (1 pto)
Quiero mejorar cada vez más en mi conocimiento y destreza en temas relacionados con Big Data y Machine Learning para así en mi futuro profesional poder tomar las mejores decisiones para poder sacar los mejores resultados generando modelos de gran valor para uso en distintas áreas.

### 5. Mencione cualquier material que utilizó como referencia para el aprendizaje (1 pto)
Para esta sección además de las clases, el libro y presentaciones del profesor, hice uso de un par de sitios web para alcarar u obtener un poco más de información respecto a un par de conceptos. Adjunto las siguientes referencias:
* Education, I. C. (2021, July 6). Exploratory Data Analysis. IBM Cloud Learn Hub. https://www.ibm.com/cloud/learn/exploratory-data-analysis 
* Mannor, S., Meir, R., & Zhang, T. (2003). Greedy Algorithms for Classification – Consistency, Convergence Rates, and Adaptivity. Journal of Machine Learning Research 4, 718–730. https://www.jmlr.org/papers/volume4/mannor03a/mannor03a.pdf





