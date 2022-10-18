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
>>>>>> * Chequeo de correlación entre nuestra variable objetivo "Rented Bike Count" y las demás variables numéricas a través de una matriz.
>>>>>> * Eliminación de variables irrelevantes para nuestro análisis como: "Functioning Day" = No y "Dew point temperature(°C)". 
>>>>>> * Descomposición de la variable "Date" en día y mes para luego ser eliminada.
>>>>>> * Box plot utilizando variables categóricas ("Seasons" y "Holiday") vs nuestra variable dependiente ("Rented Bike Count"). 
>>>>>> * Visualización de la distribución de variables continuas.

>> #### Archivo analisis.ipynb:
 
>>>> Notebook donde analizamos y aplicamos ciertos modelos de machine learning a los datos procesados. Podemos encontrar los siguientes pasos:

>>>>>> * Conversión de variables categóricas a valores numéricos utilizando técnica de "Dummyficación".
>>>>>> * Split de dataset en subsets de entrenamiento y testeo.
>>>>>> * Aplicación de escalamiento estándar a variables numéricas.
>>>>>> * Ejecución de modelos de:

>>>>>>>>    * Regresión Lineal: Modelo para analizar y predecir comportamientos entre una variable dependiente e independiente.
>>>>>>>>    * Lasso: Modelo de regresión que contrae ciertos parámetros a 0, selecciona variables que optimicen el resultado imponiendo penalización sobre coeficientes del modelo.
>>>>>>>>    * RandomForest: Modelo de regresión y clasificación basado en árboles de decisión.
>>>>>>>>    * XGBoost: Modelo optimizado de regresión y clasificación basado en técnica "Gradient Boosting", potenciador de resultados Random Forest.

>>>>>> * Observación de indicadores r cuadrado y errores cuadrados para los modelos de Regresión Lineal, Lasso y RandomForest.
>>>>>> * Exploración y visualización de coeficientes de regresión Lasso.
>>>>>> * Utilización de cross-validation y obtención de mejores parámetros para el modelo Lasso.
>>>>>> * Aplicación de GridSearchCV a modelo de RandomForest.
>>>>>> * Análisis de factores y características que afectan en mayor medida al modelo RandomForest y graficamos las importancias en base a la media y la desviación.
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

>>>> * Pandas: Análisis y Transformación de datos.
>>>> * Numpy: Cálculos numéricos, computación científica y análisis de datos.
>>>> * Matplotlib: Creación de gráficos estáticos, animados e interactivos.
>>>> * Seaborn: Librería de alto nivel para creación de gráficos estadísticos.
>>>> * Warnings: Control de advertencias, en este caso utiizada para omitir alertas no fatales para el código programado.
>>>> * Missingno: Visualización de datos faltantes o nulos de manera práctica a través de una matriz. 
>>>> * multiprocessing: Paquete optimizador que permite aprovechar multinúcleos CPU, evitando cuellos de botella computacionales.

>>>> * xgboost:

>>>>>> * xgb: Modelo optimizado de regresión y clasificación basado en técnica "Gradient Boosting", potenciador de resultados Random Forest.
>>>>>> * plot_importance: Nos permite graficar la importancia de los predictores y visualizar cuáles afectan en mayor medida al modelo.

>>>> * Scikit learn: Una de las librerías más importantes dentro de Machine Learning que nos permite implementar algoritmos de aprendizaje supervisado, no supervisado, validación cruzada, entre otras funcionalidades. Dentro de nuestro proceso de análisis utilizamos los siguientes paquetes:

>>>>>> * Model_selection:

>>>>>>>> * train_test_split: Divide arreglos o matrices en subsets aleatorios destinados al entrenamiento y testeo de modelos implementados. 
>>>>>>>> * GridSearchCV: A través de la técnica de "Cross Validation", este método nos entrega los mejores hiperparámetros que podemos utilizar en un algoritmo de ML.
>>>>>>>> * RepeatedKFold: Repetición de K-Fold n veces con diferente aleatoriedad en cada repetición.

>>>>>> * preprocessing:

>>>>>>>> * StandardScaler: Estandarización de datos elimnando la media y escalando la varianza a 1. Requisito para el correcto desempeño de algunos modelos implementados en este proyecto.

>>>>>> * linear_model:

>>>>>>>> * Lasso: Modelo de regresión que contrae ciertos parámetros a 0, selecciona variables que optimicen el resultado imponiendo penalización sobre coeficientes del modelo.
>>>>>>>> * LinearRegression: Modelo para analizar y predecir comportamientos entre una variable dependiente e independiente.
>>>>>>>> * LassoCV: Modelo Lasso con ajuste iterativo a lo largo del proceso de regularización de variables.

>>>>>> * metrics:

>>>>>>>> * r2_score: Función de puntuación de regresión, medido en una escala esperada entre 1 y 0, siendo 1 la mejor puntuación posible.
>>>>>>>> * mean_squared_error: Definido como valor medio de los cuadrados de la diferencia entre predicción y valor observado. Esta función nos permitirá entender cómo se desempeña nuestro modelo de predicción.

>>>>>> * ensemble:

>>>>>>>> * RandomForestRegressor: Metaestimador que nos permite ajustar un número de árboles de decisión en varias submuestras utilizando el promedio para mejorar precisión y controlar overfiting.

>>>>>> * inspection: 

>>>>>>>> * permutation_importance: Técnica de inspección de modelos que nos permite cuantificar la dependencia de una caracterísctica para dicho modelo. Es posible calcularlo n veces con distintas características. 

























