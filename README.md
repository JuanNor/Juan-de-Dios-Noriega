MODELO LSTM APLICADO A LA PREDICCIÓN DE LA LATIDUD DE SISMOS EN MÉXICO

En este proyecto se utilizaron las bases aprendidas en el curso de redes neuronales, tomando como base de datos los sismos ocurridos en el país (México) desde el inicio del año 2020 hasta el final del año 2024, esto con la finalidad de predecir y comparar los resultados con los datos oficiales del año 2024. El archivo de los sismos (csv) fue obtenido de la página del Servicio Sismológico Nacional (https://www.ssn.unam.mx/sismicidad/ultimos/).

El dataset original contiene 10 columnas: Fecha, Hora, Magnitud, Latitud, Longitud, Profundidad, Referencia de localización, Fecha UTC, Hora UTC, Estatus. Aunque para los fines prácticos de este proyecto solo se tomó en cuenta las columnas: Fecha, Magnitud, Latitud, Longitud y Profundidad.

Para la elaboración del modelo se prosiguió con lo visto en clase:

Cargar librerías y base de datos
Limpieza de dataset
Escalado de datos
Modelo LSTM, para ello se utilizó un dropout del 20% de las neuronas para evitar el sobreajuste, además de que se planteó el modelo con 30 épocas. Para el modelo la variable a predecir fue la latitud, utilizando como variable predictora la magnitud de los sismos ocurridos en el periodo 2020-204
Generar un nuevo dataset con únicamente los valores del año 2024
Generar predicciones y reescalado
Gráfica de comparación
R-squared

Observación: como se puede observar, el código no presenta errores al momento de la ejecución, sin embargo, la predicción no es del todo acertada respecto a los datos originales, después de investigar acerca del por qué se puede dar esta situación existen 2 principales candidatos: problema en el escalado y/o reescalado de datos, porque el patrón de las gráficas (picos, bajadas, etc) es igual en ambas, solo que en los datos predichos parecen estar en una escala distinta, después de intentar corregir este error (variando el número de épocas, dropout, de capas, etc), este fue el mejor resultado obtenido.
