# Argentina en la historia: análisis de partidos de selecciones

Análisis de datos en Python sobre más de 49.900 partidos internacionales de selecciones masculinas de fútbol (1872–2026), con foco en la selección argentina. Trabajo del **Data Challenge** de la materia Introducción a Análisis de Datos (TUP, UTN Haedo).

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/JanezSersen07/analisis-seleccion-argentina/blob/main/analisis-argentina.ipynb)

## Preguntas

1. ¿Cómo le fue a Argentina a lo largo de la historia (victorias, empates y derrotas por década)?
2. ¿Quiénes son los máximos goleadores de Argentina según los datos registrados?

## Hallazgos

- Argentina jugó **1.079 partidos** (1902–2026): ganó el **55,8%**, empató el 23,7% y perdió el 20,5%.
- La mejor década fue la de **1940** (72,9% de victorias) y la peor la de **1980** (37,1%). Desde los 90 las victorias suben y se mantienen por encima del 50%.
- El máximo goleador registrado es **Lionel Messi (71)**, seguido por Gabriel Batistuta (37), Hernán Crespo (26), Lautaro Martínez (25) y Gonzalo Higuaín (23).
- Los goles se reparten de forma bastante pareja entre los tramos de minutos, así que no se puede sacar una conclusión firme.

## Proceso

1. **Exploración:** estructura, tipos de datos y estadísticas descriptivas.
2. **Limpieza:** conversión de fechas, revisión de filas repetidas (resultaron ser goles reales, no duplicados) y tratamiento de valores faltantes.
3. **Transformación:** columnas nuevas (año, década, resultado de Argentina), tramos de minutos y tablas con `pd.crosstab`.
4. **Visualización:** barras apiladas por década, ranking de goleadores y goles por tramo de minutos.

## Limitaciones

- Las primeras décadas tienen pocos partidos (la de 1900, solo 12), así que sus porcentajes son poco confiables.
- El archivo de goleadores registra **984 de los 2.058 goles** de Argentina (~48%), por lo que el ranking es un piso y no el total real.
- La década de 2020 está incompleta.
- El análisis solo mira a Argentina, sin compararla con otras selecciones.

## Próximos pasos

Comparar a Argentina con otras selecciones (por ejemplo Brasil y Alemania) por década.

## Tecnologías

Python, pandas, NumPy, matplotlib, Google Colab

## Fuente de los datos

[International football results from 1872 to 2026](https://github.com/martj42/international_results), un repositorio público de GitHub. El notebook carga los datos directamente desde esa fuente.
