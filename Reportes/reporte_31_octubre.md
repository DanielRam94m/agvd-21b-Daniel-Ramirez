## Reporte 31 de Octubre
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
### 1. **Resumen de los temas estudiados (1 pto)**
#### &emsp; 1.1 **Algoritmos Genéticos**
Estos pertenecen a la familia de algoritmos de optimización, son eurísticos, no teniendo una garantía de que el algoritmo va a converger o a encontrar una solución logrando optimizar una función, costo u objetivo.
Pertenecen a la familia de los algoritmos evolutivos.
La manera en que estos trabajan es creando individuos modelos con valores o características ideales, entonces a cada columna se le aplica una función con lo que las columnas en conjunto darán un valor que se conoce como **valor de adaptación** o bien ***fitness value*** que puede estar cerca o lejos del valor esperado. Las columnas son elegidas aveces de una forma establecida u otras veces de una forma aleatoria en las que a cada individuo de forma aleatoria se les modifica el valor, para luego volverles a aplicar la **función de fitness** y se mide que tanto el valor de fitness o de adaptación representa una buena solución.
Estas irán conmutando en cada generación, por lo que dado la función aplicada, la generación *n* y la generación *n+1* serán distintas teniendo en sí los algoritmos genéticos **propiedades fundamentales de cambio**.
* Estos puden cambiar de una generación a otra por medio de un algoritmo de selección en la que se decide cuales variables mueren y cuales sobreviven y pasan a la siguiente generación usando el **operador de selección**.
* Por medio del **operador de crossover** dos filas interactúan entre sí, creando nuevos individuos (filas) con propiedades de sus predecesores.
* Por su parte, el **operador de mutación** lo que busca es de manera aleatoria alterar la congiguración de un individuo.

#### &emsp; 1.2 **Análisis de Asociaciones** *(Association Analysis)*
Este modelo, también conocido como análisis de afinidad *(affinity analysis)*, análisis de canasta de mercado *(market basket analysis)*, o bien, reglas de asociación *(association rules)* forman ana son parte de los **modelos de descripción**.
Estos modelos son muy útiles y pueden representar una ventaja competitiva o comercial si se encuentran fuertes relaciones entre un elemento y otro para así de manera estratégica colocarlas al alcance para insentivar a los cliente a adquirir ambos productos en conjunto o incluso ser útiles para pedicción de fraudes al estudiar qué es normal y analizar cuando algo no está teniendo un comportamiento normal. En sí la naturaleza es encontrar patrones y asociar elementos que con regularidad pasan en conjunto.
Los datasets con los que estos trabajan sulen ser **transaccionales** o **tabulares** y se les suele conocer como ***itemsets*** en los que los valores en sus columnas suelen ser binarios, son asimétricos (importa más que un item esté presente) y suelen ser simplitas aunque no necesariamente (excluyendo información como precios o cantidad de items). A cada fila en estos datasets se le llama **transacción** y al número de items activos o que participan en esa transacción se le conoce como ***action width***. Un **item** corresponde a una columna en el que sus valores suelen ser binarios y la **frecuencia de un item** está dado por el número de transacciones que lo contienen. Una vez designada una frecuencia *F* esperada, se puede decir que un item es frecuente si aparece más de *F* veces.
Los estudios de los itemsets suelen **generar reglas** como por ejemplo si *A* entonces *B*, donde *A* y *B* son conjuntos disjuntos (arroz, frijoles) --> (salsa lizano). Estas reglas son estudiadas mediante dos valores, estas serán dos propiedades de dicha regla:
* ***Support:*** Se calcula como el resultado del número total de transacciones que contienen a *A* y a *B*, entre el número total de transacciones en el itemset.
* **Confidence:** Se calcula como el resultado del número total de transacciones en que aparecen *A* y *B* entre en total de transacciones en que aparece *A*
* **Lift:** Se calcula como el resultado del número total de transacciones en que aparecen *A* y *B* entre en total de transacciones en que aparece *B*. Esta nos puede informar que los clientes que compran *B* son *x* veces mas dados a comprar *A*.

Entre las dificultedes a tratar con estos modelos es que estos tienen un espacio de trabajo grande de estudiar, siendo de *2k-1*. Sin embargo gracias al **Principio a Priori** es posible reducir la dimensionalidad del campo a estudiar, ya que si un itemset es frecuente, entonces todos sus subconjuntos también son frecuentes, por otro lado si un itemset no es frecuente, todos sus superconjuntos no serán frecuentes, por lo que podemos excluir estos superconjuntos del estudio.

Para generar reglas entonces:
1. Se aplica el Principio a Priori
2. Se encuentran todos los items frecuentes
3. Se generan reglas de asociación que satisfacen las condiciones requeridas de support y de confidence

Para el **manejo de atributos**, tenemos que los itemsets son datasets con valores binarios asimétricos (en los que solo damos valor a los items con valor 1).
* Si tenemos un dateset que queremos transformar en un itemset con valores binarios simétricos (tiene igual importancia si el valor es *True* o *False*, *1* o *0*), dicha columna se puede separar en dos, en una habrá un *1* si el item es *True* y *0* si no, mientras que en la otra habrá un *1* si el item es *False* y sero si *True*.
* De igual manera una columna categórica se puede dividir en tantas columnas como categorías distintas habían en la columna original, así en la columna item correspondiente a cada categoría habrá un *1* si la observación (ahora transacción) era de esa categóría y *0* si no.
* Para columnas con valores numéricos ya seam continuos o discretos, se establecen rangos de valores y se separan en tantas columnas como rangos distintos establecidos. Si el valor de una observación del dataset cae dentro de cierto rango, en el itemset la transacción correspondiente tendrá un valor de 1 en la columna item correspondiente.

Una vez generada las reglas, todavía es necesario filtrar aún más estas, por ejemplo en los siguientes casos:
* **Reglas generadas que no serán de uso útil** (no aportan ningún valor)
    * Por ejemplo si se compró un juguete y cierto confite, talvéz es que hay un niño presente en el momento de las compras y para el caso en particular no es un caso meta.
* **Reglas triviales** (cosas que ya son bien conocidas y no implican un descubrimiento o su implicación no es lógica)
    * Clientes que compran contratos de garantías por defecto o daño, son muy dados a comprar electrónicos (en este caso la implicación debión ser en el sentido contrario, además que no es secreto que quienes compran electrónicos busquen pagar un seguro o garantía si estos no contaran ya con una)
* **Reglas inexplicables**, estas no se pueden generalizar y podrian responder a un fenómeno dado solo en cierto periodo y bajo ciertas circuntancias.

### **2. Comentarios sobre algo aprendido (1 pto)**
Aprendí que los algoritmos genéticos suelen tener un estado meta con el que se puede comparar que tan cerca o lejos estamos de encontar nuestro fin y que nuestro modelo tenga un buen comportamiento.

Aprendí que existen los itemsets y lo que los caracteriza, anteriormente no sabía que existieran estos como tal y las utilidades que podían tener. Además aprendí que existen maneras de transformar datasets normales en itemsets mediante ciertas estrategias acorde a los tipos de vables o columnas del dataset.

### **3. Dudas sobre la materia estudiada (1 pto)**
No me quedó claro como es que exactamente funciona el operador de mutación, además tanto en los operadores de mutación como de crossover, como es que las nuevas generacions con la creación de nuevas filas a partir a tantecesores no generan una desviación de comportamiento o pérdida de información del dataset original.

### **4. Posible uso que usted le dará a esta materia como profesional (1 pto)**
En mi futuro profesional como alalista de datos, el modelo de asociación me será de gran valor para encontrar frecuencias u patrones de comportamiento que le den mayor valor valor o respaldo a las investigaciones hechas y así poder probar o explicar fenómenos y generar más valor y credibilidad a dichas investigaciones.

### **5. Mencione cualquier material que utilizó como referencia para el aprendizaje (1 pto)**
Ademas de las filminas, videos y capítulos de libros brindados en el curso por el profesor, ningún otro material fue utilizado.
