# Argentina en la historia: análisis de partidos de selecciones

Análisis de datos en Python sobre más de 49.900 partidos internacionales de selecciones masculinas de fútbol (1872–2026), con foco en la selección argentina. Trabajo del **Data Challenge** de la materia Introducción a Análisis de Datos (TUP, UTN Haedo).

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/JanezSersen07/analisis-seleccion-argentina/blob/main/analisis-argentina.ipynb)

## Preguntas

1. ¿Cómo le fue a Argentina a lo largo de la historia (victorias, empates y derrotas por década)?
2. ¿Quiénes son los máximos goleadores de Argentina según los datos registrados?
3. ¿Qué lugar ocupa Argentina entre las selecciones del mundo según su porcentaje de victorias?
4. ¿Cómo le fue en los Mundiales y contra sus rivales históricos?

## Hallazgos

- Argentina jugó **1.079 partidos** (1902–2026): ganó el **55,8%**, empató el 23,7% y perdió el 20,5%.
- La mejor década fue la de **1940** (72,9% de victorias) y la peor la de **1980** (37,1%). Desde los 90 las victorias suben y se mantienen por encima del 50%.
- El máximo goleador registrado es **Lionel Messi (71)**, seguido por Gabriel Batistuta (37), Hernán Crespo (26), Lautaro Martínez (25) y Gonzalo Higuaín (23).
- Los goles se reparten de forma bastante pareja entre los tramos de minutos, así que no se puede sacar una conclusión firme.

### Argentina frente a otras selecciones

- Entre las 83 selecciones con 500 partidos o más, Argentina es la **sexta** por porcentaje de victorias (55,8%). Lideran Brasil (63,4%), España, Alemania, Inglaterra e Irán.
- Convierte menos goles por partido que Brasil, Alemania o Inglaterra (1,91 contra 2,2 aproximadamente), pero recibe pocos: 1,00 por partido.
- Por década, los 80 fueron su peor momento frente a las otras potencias (37,1%), y desde los 2000 se mantiene cerca del 59%. Los 2020 llegan a 78,2%, aunque esa década está incompleta.
- En **Mundiales** es tercera de 17 selecciones con 40 partidos o más (56,2%), detrás de Brasil (66,4%) y Alemania (60,3%).
- Entre sus rivales de Sudamérica, le va mejor contra Chile (65,9% de victorias). Contra Uruguay ganó 85 de 183 partidos y contra Brasil el historial está casi parejo (41 ganados y 43 perdidos).

## Proceso

1. **Exploración:** estructura, tipos de datos y estadísticas descriptivas.
2. **Limpieza:** conversión de fechas, revisión de filas repetidas (resultaron ser goles reales, no duplicados) y tratamiento de valores faltantes.
3. **Transformación:** columnas nuevas (año, década, resultado de Argentina), tramos de minutos y tablas con `pd.crosstab`.
4. **Visualización:** barras apiladas por década, ranking de goleadores y goles por tramo de minutos.
5. **Comparación con otras selecciones:** un formato con una fila por equipo y partido (`pd.concat`), ranking por porcentaje de victorias, evolución por década, Mundiales y cara a cara con los rivales (`groupby` y `pd.crosstab`).

## Limitaciones

- Las primeras décadas tienen pocos partidos (la de 1900, solo 12), así que sus porcentajes son poco confiables.
- El archivo de goleadores registra **984 de los 2.058 goles** de Argentina (~48%), por lo que el ranking es un piso y no el total real.
- La década de 2020 está incompleta.
- El porcentaje de victorias no mide qué tan fuertes eran los rivales: por ejemplo, Irán y Corea del Sur figuran arriba porque juegan muchos partidos contra selecciones de su región.
- Se mezclan amistosos y torneos oficiales, y partidos de épocas muy distintas.
- Los partidos definidos por penales figuran como empates, aunque haya habido un ganador.
- Contra varias selecciones europeas hay pocos partidos (entre 10 y 23), así que esos porcentajes se mueven mucho con un solo resultado.

## Próximos pasos

Comparar el rendimiento teniendo en cuenta la fuerza de los rivales y separar partidos amistosos de torneos oficiales.

## Tecnologías

Python, pandas, NumPy, matplotlib, Google Colab

## Fuente de los datos

[International football results from 1872 to 2026](https://github.com/martj42/international_results), un repositorio público de GitHub. El notebook carga los datos directamente desde esa fuente.

