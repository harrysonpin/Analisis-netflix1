Este proyecto utiliza una base de datos obtenida de Kaggle: Netflix Data Cleaning, Analysis, and Visualization.

El objetivo principal es verificar el estado de los datos, realizar la limpieza necesaria y analizar el contenido de la plataforma de Netflix entre 2016 y 2021.

1. Limpieza de datos
Estado inicial:
Los datos no contenían valores nulos ni duplicados, por lo que no fue necesario realizar procesos de eliminación.

Ajustes realizados:

Se detectó que los identificadores (show_id) incluían una letra "s", lo cual se corrigió.
La columna de duración (duration) contenía textos como "min" y "Season", lo que podría interferir en el análisis.
Se generaron dos nuevas columnas para análisis temporal:
year_added: Año en que se añadió el contenido.
month_added: Mes en que se añadió el contenido.
2. Análisis
El análisis se centra en el crecimiento del contenido en Netflix entre 2016 y 2021.

2.1. Crecimiento de contenido por tipo
Durante este periodo, el lanzamiento de películas fue mayor que el de series de televisión.
Hacia el final del periodo estudiado, las series mostraron un ligero incremento, aunque las películas continuaron representando más del 50% del contenido subido.
2.2. Distribución geográfica
La mayoría del contenido se produjo en Estados Unidos e India.
2.3. Categorías principales
Las categorías más frecuentes fueron:
Películas internacionales (International Movies).
Comedias (Comedies).
Acción y aventura (Action & Adventure).
3. Dificultades encontradas
Análisis de los géneros (listed_in):

Los géneros estaban agrupados en una sola columna. Se intentó dividirla en tres columnas, pero esto dificultó el análisis.
Finalmente, se utilizó Python para descomponer la columna y analizar las categorías:
python
Copiar código
category_counts_recent = recent_years['listed_in'].str.split(', ').explode().value_counts()
Integración con geoplot:

Se presentaron dificultades para generar un mapa de calor.
4. Otros intentos
Google Sheets:

Se intentó replicar el análisis en Google Sheets, pero la cantidad de datos dificultó la creación de gráficas.
Además, solo se pudo analizar el primer género de cada película o serie debido a las limitaciones en la estructura de los datos.
Hoja utilizada: Google Sheets.
Uso de nuevas herramientas:

Fue la primera experiencia trabajando con bibliotecas como geoplot y plotly, lo que generó varios errores durante la implementación.
5. Conclusión
Este proyecto permitió analizar el crecimiento y la distribución del contenido en Netflix, destacando las tendencias de las películas y series en diferentes géneros y regiones.
A pesar de las dificultades técnicas, el uso de Python facilitó el procesamiento y la visualización de los datos.
