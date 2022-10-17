# Grupo 4: Seoul Bike Dataset

## Integrantes:

>> * Fernando Nachbauer
>> * Hernán Almonacid
>> * Ignacio Fuentes
>> * Kevin Gallardo
>> * Patricio Ramírez


## Descripción del Proyecto: 

>> ### Incidencia de las condiciones climáticas en el arrendamiento de bicicletas en Seúl, Corea del Sur.

### Problema planteado:

>> La movilidad de las personas a través de medios de transporte ecológicos es cada vez más demandada, lo que ha impactado fuertemente en la utilización de bicicletas en las grandes ciudades. La congestión vehicular y los tiempos de desplazamiento han ido en aumento en el últimpo tiempo, obligando a la búsqueda de alternativas más eficientes. Dado este contexto, es de interés para un equipo de inversión determinar, a través de análisis de regresiones, qué tanto influyen las condiciones climáticas en el uso de bicicletas como medio de transporte y por ende su arrendamiento. Es importante determinar si existen estacionalidades y períodos de alta demanda específicamente en la ciudad de Seúl, Corea del Sur. 

>> Para responder a la interrogante del grupo de inversión utilizaremos una muestra del año 2017 que contiene variables climáticas observadas a cada hora del día y cuántas bicicletas fueron arrendadas bajo esas condiciones. El dataset fue obtenido desde Public Bikes y su nombre es SeoulBikeData.csv.

>> Esperamos que exista correlación positiva entre la temperatura (°C) y la cantidad de bicicletas arrendadas, por ende una mayor afluencia en la utilización del servicio en verano. Bajo el supuesto que la jornada laboral en Seúl es similar a la de Santiago, se espera que exista mayor cantidad de arrendamientos entre las 8:00 y 9:00 hrs. (hora de entrada) y entre las 18:00 y 19:00 hrs. (hora de salida).


## Estructura de archivos y carpetas:

### Carpeta data:

>> #### Carpeta raw: 

>>>> Contiene dataset SeoulBikeData.csv sin ningún tipo de transformación.

>> #### Carpeta processed: 

>>>> Contiene dataset transformado y adecuado para obtener el mejor desempeño en nuestro análisis.
 
### Carpeta notebooks:

>> #### Archivo limpieza.ipynb: 

>>>> Notebook donde detallamos todo el proceso de exploración y transformación que se llevó a cabo para conseguir el dataset ubicado en la carpeta "processed". Dentro de los cambios realizados podemos destacar:

>>>>>> * Revisión de valores nulos, únicos, duplicados y el tipo de datos con los que contamos.
>>>>>> * Eliminación de variables irrelevantes para nuestro análisis como: "Functioning Day" y "Dew point temperature(°C)".
>>>>>> * Modificación de formato en la variable "Date" y descomposición.
>>>>>> * Box plot utilizando variables categóricas ("Seasons" y "Holiday") vs nuestra variable dependiente ("Rented Bike Count"). 
>>>>>> * Visualización de la distribución de los datos utilizando QQ plot.
>>>>>> * Normalización de variables "Rented Bike Count" y "Wind speed (m/s)" mediante la utilización de de función cuadrática (sqrt).
>>>>>> * Conversión de variables categóricas a valores numéricos utilizando técnica de "Dummyficación".

>> #### Archivo analisis.ipynb:
 
>>>> Notebook donde exploramos, analizamos y visualizamos los datos procesados. Podemos encontrar los siguientes análisis:

>>>>>> * Chequeo de correlación existente entre nuestra variable objetivo "Rented Bike Count" y las demás incluídas a través de una matriz.
>>>>>> * Análisis de distribución de las variables numéricas.
>>>>>> * Agrupar por variables categóricas ("Seasons","Holiday") y observar la frecuencia de nuestra variable objetivo.
>>>>>> * Ejecución de modelos de:

>>>>>>>>    * Regresión Lineal: Modelo para analizar y predecir comportamientos entre una variable dependiente e independiente.
>>>>>>>>    * Lasso: Modelo de regresión que contrae ciertos parámetros a 0, selecciona variables que optimicen el resultado imponiendo penalización sobre coeficientes del modelo.
>>>>>>>>    * Random Forest: Modelo de regresión y clasificación basado en árboles de decisión.
>>>>>>>>    * XGBoost: Modelo optimizado de regresión y clasificación basado en técnica "Gradient Boosting", potenciador de resultados Random Forest.

>>>>>> * Comparación de resultados obtenidos por cada uno de los modelos aplicados.

>> #### Archivo reporte.ipynb: 

>>>> Notebook que reúne los principales insights de cada uno de los pasos recorridos a lo largo del proyecto.

>>>>>> * Descripción del dataset utilizado y contextualización.
>>>>>> * Descripción detallada del proceso de transformación y limpieza de datos para alcanzar el archivo resultante ubicado en la carpeta "data/processed".
>>>>>> * Descripción y justificación de los modelos probados, basado en el contexto y la naturaleza del problema.
>>>>>> * Selección del modelo con mejor rendimiento y precisión.
>>>>>> * Supuestos que nos permitirán poner a prueba el modelo elegido y la interpretación de los resultados obtenidos.
>>>>>> * Conclusiones.

### Carpeta output:

>> #### Archivo reporte.html: 

>>>> Resultado obtenido en el archivo reporte.ipynb.


## Guía de ejecución de los archivos.ipynb y librerías utilizadas:

>> Todos los notebooks.ipynb vienen con el kernel reiniciado, por lo que, para obtener el output de cada línea de código solo basta correr el kernel.

>> Además, hemos utilizado ciertas librerías y paquetes que podrían no estar instaladas por defecto en la interfaz que se utilice para ejecutar nuestros notebooks. Revisa el detalle a continuación.

>> ### Detalle de librerías utilizadas.

>>>> * Pandas: Manipulación y Transformación de datos.
>>>> * Numpy: Cálculos numéricos, computación científica y análisis de datos.
>>>> * Matplotlib: Creación de gráficos.
>>>> * Seaborn: Creación de gráficos.
>>>> * Warnings: Control de advertencias, en este caso utiizada para omitir alertas no fatales para el código programado.
>>>> * Missingno: Visualización de datos faltantes o nulos de manera práctica a través de una matriz. 







