## Reporte 31 de Octubre
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
### 1. **Resumen de los temas estudiados (1 pto)**
#### &emsp; 1.1 **Segmentación (Clustering)**
Esta consiste en una técnica de aprendizaje no supervisado utilizado para dividir un conjunto de datos en grupos, esto dado las características que estos compartan. Cada segmento repesenta una abstracción de los elementos individuales.

Entre los usos posibles que podría tener esta técnica son el obtener resúmenes, compresión y la búsqueda de vecinos cercanos de las observaciones.

Estos algoritmos requeren:
* De una métrica de similitud, una vez dada esta métrica
* Que sus atributos categóricos sean codificados
* La transformación de datos numéricos
* La cantidad de clusters que se buscan
* Si un objeto se parece a otro, su valor de similitud será 1 o de lo contrario 0

Exister varios métodos de clustering:
* **Métodos de Partición:** 
    * Encuentra clusters mutualmente exclusivos de forma esférica
    * Se basan en la distancia
    * Pueden utilizar varias funcines para calcular el centro del cluster
    * Son efectivos en conjuntos de datos de tamaño pequeño a medio
* **Métodos Jerárquicos:** 
    * La segmentación es una descomposición gerárquica
    * No puede corregir divisiones o uniones erróneas
    * Podría incorporar técnicas como microsegmentación o considerar enlaces de objetos
* **Métodos Basados en Densidad:** 
    * Pueden encontrar formas de clusters arbitrarias
    * Los clusters son áreas densas de un objeto en un espacio que está separado por regiones de baja densidad
    * En cuanto a la densidad del cluster, cada punto debe tener como mínimo un número establecido de puntos dentro de su vecindario
* **Métodos Basados en la Red:** 
    * Usa una estructura de datos de red de alta resolución
    * Tiene un tiempo de prosesamiento rápido

Tipos de algorítmos de clustering:
* **K-means y K-modes:** Estos se basan en centroides, se basan en prototipos y crean particionamientos de un solo nivel. Define un prototipo como un centroide y se suele usar en objetos con valores continuos en espacios n-dimensionales
    * Se asemeja a la clasificación en el hecho de que guarda una etiqueta
    * El número k es arbitrario y solo toma significado luego de que este es aplicado
    * La única interpretación es que los elementos de un grupo son similares
    * Hay mucha aleatoridad en la definición inicial de los k clusters
    * No hay garantía de encontrar el número correcto de clusters
    * Este supone que los clusters poseen el mismo tamaño o diámetro
    * El límite entre clusters está justamente en la mitad de la distancia entre ambos clusters
    * Suponen que cualquier dirección es igualmente importante
    * Los clunters tienen forma convexa definidas por su centroide
* **K-medoids:** Define el prototipo como el punto más representativo entre todo el grupo, este es por definición un punto en los datos y no el centro, además requiere que se le asigne una medida de similitud o cercanía
* **Clustering Aglomerativo:** 
    * En estos cada punto inicia como un cluster. Luego en cada iteración se mezclan los dos más cercanos, este se detiene al alcanzar un criterio
* **Clustering Jerarquico y Dendogramas:** 
    * Es un clustering aglomerativo en sus iteraciones
* **DBSCAN (método de densidad):** 
    * No requiere que se indiquen los k clusters a priori
    * Puede encontrar clusters de forma compleja
    * Puede encontrar puntos que no pertenecen a ningún cluster
    * Es más lento que el algoritmo k-means, pero trabaja bien con conjuntos de datos jigantes

### **2. Comentarios sobre algo aprendido (1 pto)**
Aprendí que existen varios algoritmos de segmentación con distintas características con respecto a los pasos e hiperparámetros para generar los clusters, así como sus ventajas y desventajas.

### **3. Dudas sobre la materia estudiada (1 pto)**
En cuanto a lo teórico no me quedó ninguna duda ya que los contenidos estaban muy bien detallados, mas me gustaría poder tener alguna noción más en lo práctico de como decidir cuando usar k-means, k-medoids, custering aglomerativo, clustering jerarquico o bien DBSCAN

### **4. Posible uso que usted le dará a esta materia como profesional (1 pto)**
Los algoritmos de clustering pueden llegar a ser muy útiles para estudiar o encontrar patrones en los conjuntos de datos, por lo que en casos de estudios poblacionales podría ser de utilidad como por ejemplo decidir características de los públicos meta.

### **5. Mencione cualquier material que utilizó como referencia para el aprendizaje (1 pto)**
Ningún otro material además de las presentaciones y los capítulos de los libros fueron utilizados