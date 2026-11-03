# 🚆 DATA DETECTIVE · Caso 01: transporte ferroviario en España

*¿Cómo ha evolucionado el número de viajeros ferroviarios en España entre 2016 y 2025?*

Análisis exploratorio de datos públicos de la CNMC con Python y pandas. Forma parte de *Data Detective*, una serie de proyectos en los que parto de una noticia para hacerme una pregunta y responderla con datos.

---

## Contexto

Una noticia sobre un accidente ferroviario despertó mi interés por conocer mejor el transporte en tren en España. A partir de esa curiosidad, el proyecto se centra en una pregunta que se puede abordar con datos públicos: cómo ha evolucionado el número de viajeros por tipo de servicio.

*Objetivo:* observar tendencias, comparar tipos de servicio y detectar cambios a lo largo del tiempo.
*Fuera de alcance:* las causas de accidentes concretos y la evaluación de la seguridad ferroviaria.

## Datos

- *Fuente:* estadísticas trimestrales de transporte ferroviario de la Comisión Nacional de los Mercados y la Competencia (CNMC).
- *Archivo:* transporte-ferroviario.csv
- *Variable principal:* número de viajeros, por trimestre y tipo de producto.

| Producto | Descripción |
|---|---|
| Cercanías | Cercanías |
| LD AV | Larga distancia de alta velocidad |
| LD Convencional | Larga distancia convencional |
| MD AV | Media distancia de alta velocidad |
| MD Convencional | Media distancia convencional |

## Metodología

1. Lectura del CSV
2. Revisión de tipos de datos y valores ausentes
3. Agrupación trimestral
4. Construcción de fechas
5. Agregación anual
6. Cálculo de variaciones interanuales e índice con base 2016 = 100

> ⚠️ *Precaución metodológica.* El fichero contiene filas por empresa y filas identificadas como “Total”. Hay que comprobar que la agregación no sume a la vez totales y desgloses, porque duplicaría viajeros. Los resultados deben considerarse *exploratorios* hasta completar esa validación.

## Resultados principales

*Comparación 2019 vs 2025*

| Producto | Viajeros 2019 | Viajeros 2025 | Cambio |
|---|---:|---:|---:|
| Cercanías | 443.178.453 | 446.348.801 | +0,7 % |
| LD AV | 22.372.822 | 44.499.598 | +98,9 % |
| LD Convencional | 12.145.913 | 8.701.707 | −28,4 % |
| MD AV | 8.877.431 | 13.189.297 | +48,6 % |
| MD Convencional | 24.256.908 | 34.616.678 | +42,7 % |

- En *2020* se observa una caída pronunciada en todos los productos. Coincide con la pandemia de COVID-19, pero este análisis descriptivo no demuestra por sí mismo qué factores causaron los cambios.
- Las evoluciones son distintas según el producto: algunos superan el nivel de 2019 y otros no.

## ¿Y la seguridad?

El número de viajeros no indica si viajar en tren es más o menos seguro. Para estudiarlo harían falta indicadores específicos: accidentes por año, personas fallecidas y heridas, accidentes por trenes-kilómetro recorridos y sucesos por tipo de servicio. Las fuentes adecuadas serían la Agencia Estatal de Seguridad Ferroviaria (AESF) y la Agencia Ferroviaria de la Unión Europea (ERA).

## Próximos pasos

- Validar la agregación de totales y desgloses por empresa.
- Abrir una segunda línea de trabajo sobre seguridad ferroviaria con estadísticas oficiales de accidentes, víctimas y exposición al tráfico.

## Cómo ejecutarlo

bash
pip install pandas matplotlib jupyter
jupyter notebook DATA_DETECTIVE_01_transporte_ferroviario.ipynb


## Herramientas

Python · pandas · matplotlib · Jupyter

---

> «Los datos nos muestran patrones. Nuestra responsabilidad es interpretarlos con rigor y sin olvidar lo que representan».

Este proyecto no es una evaluación técnica de la seguridad ferroviaria ni una investigación de accidentes.
