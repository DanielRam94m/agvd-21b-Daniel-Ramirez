
## Reporte 1
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
A continuación se listará lo aprendido de cada script de python agrupados según sección.
#### 1. Lab2_Notes.ipynb
* Al aplicar la función `head()` al dataset leído, se desplegarán las primaras observaciones de este dataset.
* Con la función `describe()` podemos obtener un sesumen de algunos datos estadísticos de variables continuas del dataset, como lo son la media, la desciación estándar, el primer, segundo (mediana) y tercer cuartil, así como del valor mínimo y máximo en dicha variable.
* Con la función `hist()` podemos graficar un histograma en relación a una variable definida en la estrctura `dataset_cargado[variable_a_graficar]`.
* Con `xlim()` y con `ylim()` podemos delimitar los límites inferiores y superiores a gragicar.
* Con la función `plot()` se puede graficar la distribución de los valores en una variable.
* Para graficar Python nos ofrece dos librerías, una de estas es **pandas** la cual ya conozco y he usado antes, y la otra es **matplotlib.pyplot**.
* Con `groupby()` podemos agrupar los valores de una variables con respecto a los distintos valores presentes en una variable categórica.
* Podemos graficar boxpllots utilizando `boxplot()`.
* Podemos también obtener más datos estadísticos como las medias (usando `mean()`), las correlaciones (usando `corr()`), las varianzas (con `var()`), en orden ascendente o descendente con respecto a una variable (con `sort_index()`) y otras más.
* Haciendo uso de **docstring** podemos mejorar la documentación de nuestro código.
* Podemos crear funciones lambda de una sola línea que a pesar de retorcar un valor, estas no nesecitan que escribamos la sección de `return`, esto se puede realizar al hacaer uso de la palabra reservada **lambda**.
#### 2. Lab3_Notes.ipynb
* Podemos crear un arreglo multidimensional que funciona de forma rápida al usar la librería de **numpy** y su función de `array()`, misma que se puede usar para un arreglo de arreglos (matriz), o bien multidimencionales.
* Con `.shape` podemos obtener las dimenciones de los arreglos.
* Con `reshape()` podemos redimencionar matrices en tal forma que siempre se mantenga el mismo valor de entradas en la matriz nueva que en la original.
* Con la función `diag()` podemos obtener los valores en la diagonal.
* Podemos pasar varios valores a una función al **vectorizar** dicha función.
* Con `.columns` podemos observar el nombre de cada columna en un daraset.
* Con la opción de `.loc['texto a buscar']` podemos encontrar el match exacto el la variable deseada en un dataset y retornar todos los valores de dicha observación.
#### 3. viz1_intro_matplotlib.ipynb
* Al usar `plt.style.use('classic')` nos aseguramos de utilizar un formato clásico a la hora de crear nuestros gráficos.
* Con `savefig('my_figure.png')` podemos crear un directorio donde se puede guardar los gráficos.
#### 4. viz2_simple_line_plots.ipynb
* En **Matplotlib** debemos primero generar los eges antes de graficar y esto se puede hacer con `fig = plt.figure()` y con  `ax = plt.axes()`.
* Con `color=` podemos cambiar el color de la línea a graficar y cambiar el estilo de línea con `linestyle=`.
#### 5. viz3_simple_scatter_plots.ipynb
* Con `cmap=` podemos especificar algún esquema de color. El esquema 'viridis' es bonito.
* Con la función `alpha=` podemos ajustar la transparencia de lo graficado.
* `colorbar()` mostrará a un lado la escala de color utilizada en la graficación.
#### 6. viz4_errorbars.ipynb
* Con `errorbar()` podemos graficar la distribución de los errores.
* Es posible hacer cuantos cambios deseemos en un gráfico con muchos distintos comandos que podemos buscar en documentaciones de las librerías utilizadas para graficar.
#### 7. viz5_density_contour_plots.ipynb
* Con `contour()` podemos ver la densidad de valores graficados, y al usar en esta la función `cmap=` podemos en escala de color mejorar la visualización de estas densidades.
* También podemos graficar densidades rellenando contornos al usar `contourf()` es buena idea de convinar con las funciones `cmap=` y `colorbar()` para hacer un gráfico más completo.
* También podríamos nuevamente ajustar la transparencia con `alpha=` y resaltar los contornos con etiquetas con `plt.clabel()`
#### 8. viz6_histograms.ipynb
* Con `histtype='stepfilled'` al combinarlo con `alpha=` para graficar distintas variables y que se puedan distinguir en casos de traslapes.
#### 9. viz7_legends.ipynb
* Es posible poner varios niveles de *labels* o etiquetas en los gráficos, esto primero graficando con el primer nivel de *labels* y una vez creado irle agregando nuevos niveles de *lebels*.
#### 10. viz8_colorbars.ipynb
* Con `imshow()` podemos personalozar algunas características de la graficación. Por ejemplo podemos agregar `cmap='gray'` para cambiarlos a un esquema de escala de grises.
* Podemos ver escalas de colores en RGB y también su versión respectiva en escala de grisis con el uso de `view_colormap()`. Algunos ejemplos de temas de colores que podemos poner dentro de esos paréntesis pueden ser *'jet'*, *'viridis'*, *'cubehelix'* o *'RdBu'*, por mencionar algunos.
* Los colores de barras que normalmente vienen en un degradado continuo también pueden ser discretizados a usar la función `plt.cm.get_cmap()`
#### 11. viz9_basemap.ipynb
* Me salen errores al intentar instalar las librerías de esta e intenté de varias formas sin cambio, por lo que esta en particular no pude realizarla
