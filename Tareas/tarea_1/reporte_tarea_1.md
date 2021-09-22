## Reporte Tarea 1
## CI-0163   Análisis de Grandes Volúmenes de Datos
## Daniel Ricardo Ramírez Umaña, B45675
***
### Información acerca del datasert escogido:
El dataset escogido fue "original_campus_france_rouen_2019_dataset.csv", el cuál fue extraído de la plataforma de **Kaggle** en la sección de **data cleaning datasets** y cuya dirección es https://www.kaggle.com/williamscanisius/campus-france-rouen-2019-dataset?select=original_campus_france_rouen_2019_dataset.csv.

![image01](./Images/Tarea1_imagen01.png)*Figura  1: Dataset de Admisión en el Campus France Rouen 2019*

![image02](./Images/Tarea1_imagen02.png)*Figura  2: Información general del dataset generada de la función `.info()`*

Como podemos observar en las figuras 1 y 2 el dateset consiste en 4024 observaciones (filas) y 59 columnas (variables)

### Tratamiento que requrió el data set:
Es necesario antes de trabajar con el dataset hacer unos trabajos con este primero para limpiarlo.

![image03](./Images/Tarea1_imagen03.png)*Figura  3: Ejemplo de variables con pocas o ninguna entrada con valor no vacío*

Entre los tratamientos que requirió el dataset tenemos la presencia de culumnas vacías en las que existe el nombre de la variable en el *header*, pero que sin embargo todas las entradas en esta columna se encuentran vacías. Estas variables o columnas corresponden a las de:
* Date limite de traitement
* Statut particulier bac

O bien variables con muy pocas entradas con valor y todas las demás vacías como:
* Statut particulier bourse (solo una fila con valor 'Autre bourse')
* Statut particulier autre (con 9 de 4024 entradas con valor entre 6 categorías)
* Exonération (tiene solo 5 de las 4024 entradas con valor correspondientes a una sola categoría)

![image04](./Images/Tarea1_imagen04.png)*Figura  4: Eliminación de variables que aportan muy pocos valores de entrada para generarnos valor considerable*

La decisión tomada con respecto a estas columnas fue la de eliminarlas, ya que al haber tan pocos valores esta no nos aportaría mucho valor de estudio.

### 3 Preguntas que quiero estudiar del dataset:


### Primera Fase:


### Segunda Fase:


### Referencias:

![image02](./Images/Tarea1_imagen02.png)*Figura  2: I*