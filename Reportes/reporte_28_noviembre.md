## Reporte 28 Noviembre
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
### 1. **Resumen de los temas estudiados (1 pto)**
#### &emsp; 1.1 **Series de Tiempo**
Las series de tiempo son aplicadas para aquellos datasets en los que el atributo objetivo depende del tiempo, o sea que estás observaciones fueron tomadas acorde a una serie temporal. En estos casos nos intereza la dependencia entre las variables y la serie temporal. Estos valores temporales podrían ser bien continuos o discretos.

Las series de tiempo están compuestas por una **tendencia (trend) Mt** que nos dice si esta serie tiene una característica incremental, decremental o estable (stationary). Estas además poseen uns **temporalidad (seasonality) Qt** correspondientes a las fluctuaciones de frecuencia regular que aparece en una serie. También poseen un **ruido (random noise)** la cual habla de la varianza irregular en los datos.

Una serie de tiempo se puede expresar como una combinación de sus componentes.

La **descomposición de una serie de tiempo** consiste en poder identificar sus tres elementos: la tendencia, la temporalidad y el ruido, para luego se obtenga una serie de tiempo {et} a partir de {yt} eliminando los componentes y dejando solo la estructura final de los datos, lo que además de permitirnos analizar la estructura de la serie, también nos permitirá predecir valores a futuro.

Si la serie tiene un tendencia y temporalidad no es estacionaria, sin embargo es posible convertir una serie no estacionaria en una estacional.

La **eliminación de componentes (moving average)** consiste en una técnica que sirve para identificar la tendencia en una serie a largo plazo eliminando de la serie el componente de ruido o incluso tembién el componente temporal.

Para eliminación de componentes también tenemos la **eliminación de tendencia** que puede hacerse mediante el moving average o bien mediante la técnica de diferenciación.

La **eliminación de temporalidad** es otra forma para eliminar componentes. Para este caso es necesario que la serie tenga un periodo regular. Elegir el valor del periodo o ciclo basado en el dominio de los datos. Posteriormente calcular los índices de temporada para finalmente eliminar el efecto de temporalidad dividiendo los valores originales por el valor del índice correspondiente.

Finalmente, es posible realizar **separación de componentes** usando una función multiplicativa.

Para predicción en series de tiempo, es posible utilizar modelos de predicción tales como **Exponential Smoothing**, **Auto-regressive** o bien **Machine Learning**.

#### &emsp; 1.2 **Análisis de Flujo de Datos**
La técnica del **batch processing** se usa esepecialmente para casos en los que los datos cambian constantemente y con los que es necesario tomar decisiones prontas. Se caracterizan por tener transacciones de muy alto volumen con un cambio muy rápido en el tiempo.

En cuanto al **stream processing** este requiere procesar los datos sin almacenarlos, en el que los datos deben de ser procesados en tiempo real. Para estos casos no es posible esperar a que un algoritmo de Machine Learning para poder utilizarlos en los datos. Este paradigma es útil para trabajar con datasets infinitos. Sus datos cuentan con dos aspectos, su cardinalidad y su constitución.

Para su procesamiento contamos con dos tipos de datos, estas son **bounded data** y **unbunded data**.

En **bounded data** los datos pasan por un procesamiento y poseen un problema de muestreo cuando los datos son no acotados (datos en ráfaga). Es importante destacer que no es posible almacenar todos los datos que llegan.

En **unbunded data (streaming)** los datos suelen no estar en orden con respecto de los eventos que los generaron, además el sesgo evento-tiempo es muy variable por lo que son muy difíciles de analizar en contexto. Para analizar los unbunded data podemos hacer uso de alguno de estos 4 enfoques
* **Time-agnostic** en el que el tiempo es irrelevante para el análisis, todos los elementos de streaming reflejan un elemento de filtrado y además es fácil de implementar en sistemas basados en batch mediante chunks de los streams.
* **Appoximation** que toman un dato del stream y lo convierten en algo similar que conserva ciertas similitudes y la transformación puede ser cualquiera.
* **Windowing** consiste en tomar el stream de datos cintinuos y partirlo en pedacitos que conservará ciertas carcterísticas de la temporalidad.
    * **Windowing by processing time** en el que los datos entrantes se apilan en un buffer hasta conseguir un bloque de tiempo determinado y todos los datos observados en dicho bloque se pasan a la siguiente etapa de análisis. Estos son muy fáciles de implementar, pero si los datos requieren del tiempo en que ocurrió el evento, su agrupamiento daría resultados erróneos.
    * **Windowing by event time** en el que sus bloques reflejan el tiempo del evento y no el tiempo del procesamiento. Este es el méodo más utilizado y además el tamaño de su bloque puede ser dinámico. Tiene como una desventaja que las ventanas deben vivir más tiempo respecto del tiempo de procesamiento.

### **2. Comentarios sobre algo aprendido (1 pto)**
Aprendí que en cuanto a datasets en que el tiempo juega un papelimportante para el estudio de estos, se puede trabajar con series de tiempo, además de la existencia de por sí decirlo datasets infinitos en los que constantentemente están llegando cantidades enormes de datos que deben ser estudiados a momento y que por su naturaleza no pueden ser almacenados ni tampoco esperar a aplicar y entrenar un modelo para su estudio peroque existen técnicas que podemos aplicar como por ejemplo el stream processing

### **3. Dudas sobre la materia estudiada (1 pto)**
No me queda claro como identificar bien cuando utiizar Windows by processing time y cuando Windows by event time, ambos conceptos se me hacen muy similares.

### **4. Posible uso que usted le dará a esta materia como profesional (1 pto)**
Como ingeniero de datos, es posible que en mometos tengs que tabajar con sensores que constantemente están recibiendo información, o bien con un gran volumen de tráfico de red en el que constantemete tenga que sacar información de estos para la toma de decisiones importantes que implican un gran valor. Además es frecuentes el estudio de valores con respecto al tiempo para poder reaizar predicciones o bien ajustes a algún proceso para mejorar el rendimiento de algo.

### **5. Mencione cualquier material que utilizó como referencia para el aprendizaje (1 pto)**
Ninguno además del material brindado en clases
