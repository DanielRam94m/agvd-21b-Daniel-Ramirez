## Reporte 05 se Septiembre
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
## Big Data
#### ¿Qué es?
Es una cantidad inmensa de datos almacenada, con estos datos pueden ser analizados, encontrar patrones y sacar conclusiones. Con todo esto se pueden tomar decisiones de gran valor para los interesados en estos datos
Para considerar que un conjunto de datos entra en la categoría de Big Data, podríasmos decir que estos deben coincidir con 5 características, las **5Vs**:
1. **V**olumen: Generan o tienen acceso a grandes cantidades de dates.
2. **V**elocidad: Estos datos son generados a gran velocidad.
3. **V**arabilidad: Los datos poseen variedad entre sí, y estos pueden estar organizados de forma **estructurada**, **semi estructurada** o bien **no estructurada**.
4. **V**eracidad: Estos datos cuentan con precisión y fiabilidad.
5. **V**alor: Poseen un valor especial, como por ejemplo detectar enfermedades, mejoras de tratamientos o procesos, predecir desastres o bien reducir costos.

Estos datos pueden ser almacenados y procesados al utilizar frameworks.

#### Científico vs Científico de la Computación vs Ciencia de Datos
Un científico intenta entender el comportamiento del mundo natural. Por otro lado los Científicos de la Computación prefieren crear y desarrollar herramientas. La Ciencia de Datos se encientra en un punto intermedio entre estos dos. Aquí existe un interés por descubrir aspectos del mundo y también, así como manejar y desarrollar herramientas para analizar datos.

## Almacenamiento de Datos
En muchos casos existen más datos de los que podemos procesar, es por esto que es necesario de aplicar temas de filtrado, pero esto sin perder información.

## Extracción de Información
Es necesario de saber de como aplicar buenas técnicas de limpieza de datos, esto debido a que los datos del mundo real muy frecuentemente tendrán muchas cosas producto de ruido externo. Una vez hecho esto los datos pueden ser integrados, agrupados y representados.

## Limpieza de Datos
Es importante desconfiar de los datos ya que los métodos o herramientas de recolección de estos pueden fallar, puede existir también un sesgo introducido o la fuente haberse visto vulnerabilizada.

## Modelado y Análisis
Al trabajar con volúmenos masivos de datos, es también muy probable que estos cuenten con mucho ruido, suelen ser dinámicos y muy heterogéneos, por lo que métodos de muestreo donde se trbajen con subconjuntos más pequeños de estos puede no ser lo más indicado ya que todo el ruido generado en menor escala no nos permitirá controlar los datos que en verdad nos interezan

## Interpretación
En esta etapa se busca ayudar a la toma de decisiones acertadas e informadas

## Scraping
Consiste en obtener datos de páginas web de forma automática.
En este caso, obtener datos consiste en dos etapas:
1. Spidering: Consiste en extraer los datos de la página de interés.
2. Consiste en parcearlos y estructurarlos para después poder trabajar con ellos.

## Ruido en los datos
#### Ruido por Errores
Puede darse en la recolección de datos por errores en las tomas de estos y son muy difíciles o incluso imposibles de recuperar.

#### Ruido por Artefactos
También puede darse lo que llamamos artefactos que son errores sistematizados a los cuales por medio de ciertos tratamientos podemos llegar a corregirlos o a reconstruirlos.

## Valores faltantes (Missing Values)
Existen muchos métodos para poder completar los valores perdidos, pero es necesario entender el porqué es que se perdieron o si existe alguna justificación para que estos no se encuentren en el dataset ya que si intentaramos llenarlos esto nos generaría ruido que era inecesario y que además nos podría afectar otros datos al voncularlos con valores erroneos de otra variable.
Entre los métodos para complera los valores perdidos tenemos: 
* **Impitación basado en heurística**
* **Imputación de valor promedio**
* **Imputación de valor aleatótio**
* **Imputación por vecino más cercano**
* **Imputación por interpolación**

## Detección de Outliers
Conociendo cuál es la distribución más o menos que debería tener los datos, los *outliers* son valores que se encuentran muy por fuera de rango de tal desviación estándar

## Open Refine
Open Refine es una herramienta que nos permite hacer limpieza de datos en un *dataset*, con esto podemos agrupar variables categóricas donde a razón de diferentes formas de tomar un dato, se generaron distintas categorías que debían ser una sola, como por ejemplo variaciones en si al momento de tomar cada onservación se utilizaron mayúsculas o no, si se utilizaron signos de acentuación, si se digitaron espacios de mal o se cometieron errores hortográficos. Esta misma herramienta tiene muchas otras funcionalidades que con el uso en su tiempos sería de gran utilidad ir aprendiendo.
