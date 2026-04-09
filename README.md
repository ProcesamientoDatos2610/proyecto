# Proyecto Big Data — Educación y conectividad en Colombia

Este proyecto busca entender algo muy real: **por qué tener internet no siempre significa mejores resultados académicos.**

A partir de datos del ICFES, conectividad y condiciones socioeconómicas, se analiza cómo diferentes factores influyen en el desempeño de estudiantes en las pruebas Saber 11, especialmente en municipios con mayor vulnerabilidad.

---

## ¿Qué problema estamos abordando?

En Colombia hay una brecha clara entre estudiantes urbanos y rurales. Aunque se ha invertido en conectividad, los resultados académicos no siempre mejoran como se esperaría.

La pregunta central es: *¿realmente el acceso a internet está ayudando a mejorar la educación?*

O hay algo más detrás (spoiler: sí hay).

---

## Enfoque del proyecto

Se trabaja bajo la metodología **CRISP-DM**, con una lógica clara:

1. Entender el problema (contexto real del país)
2. Entender los datos
3. Explorar, limpiar y transformar
4. Plantear preguntas de negocio
5. (Siguiente fase) modelar y generar soluciones

---

## Datos utilizados

Se integraron varias fuentes para tener una visión completa:

- Resultados Saber 11 (ICFES)
- Acceso a internet por municipio (MinTIC)
- Datos socioeconómicos (Sisbén / pobreza)
- Información educativa (MEN)

La idea fue no ver el problema solo desde lo académico, sino desde todo el contexto.

---

## Tecnologías

- Python
- PySpark (procesamiento distribuido)
- Apache Spark
- Jupyter Notebook

*(Varios notebooks fueron desarrollados o probados en entornos tipo Databricks; puedes adaptar rutas y credenciales si ejecutas en local.)*

---

## Notebooks (análisis de datos)

Los notebooks viven en la carpeta [`notebooks/`](notebooks/). Resumen de qué hace cada uno:

| Notebook | Qué hace |
|----------|----------|
| [`icfes.ipynb`](notebooks/icfes.ipynb) | Análisis exploratorio del dataset de Saber 11: estructura, variables relevantes y relaciones preliminares entre desempeño y factores socioeconómicos. *(El dataset era grande; en el trabajo original se partió en dos para cumplir límites de plataforma.)* |
| [`estadisticas-municipio-eda-notebook.ipynb`](notebooks/estadisticas-municipio-eda-notebook.ipynb) | EDA de estadísticas de educación preescolar, básica y media por municipio (MEN, datos.gov.co): cobertura temporal 2011–2023, indicadores como cobertura, deserción y aprobación, con conversiones a porcentaje y visualizaciones. |
| [`bono_scraper_saber11.ipynb`](notebooks/bono_scraper_saber11.ipynb) | Bono: consumo de la **SODA API** de Socrata sobre *Resultados únicos Saber 11* en datos.gov.co, con PySpark y visualizaciones (alternativa más estable que parsear HTML). |
| [`scraper_clima_colombia.ipynb`](notebooks/scraper_clima_colombia.ipynb) | Bono: pronóstico climático 5 días vía **OpenWeatherMap API** para ciudades de Colombia, procesado con PySpark y `requests`. Requiere API key propia. |

---

## ¿Qué se hizo en esta primera entrega?

- Se integraron múltiples datasets en Spark
- Se exploraron los datos (estadísticas, gráficos, relaciones)
- Se revisó calidad de datos (nulos, inconsistencias, outliers)
- Se hicieron transformaciones básicas para analizarlos mejor
- Se identificaron primeras relaciones entre variables

**Hallazgos iniciales:**

- Sí hay relación entre internet y desempeño
- Pero la pobreza pesa mucho más de lo que parece
- La conectividad sola **no explica todo**

---

## Preguntas de negocio

Preguntas que guían el proyecto (la siguiente fase las responde con más rigor):

1. ¿Qué tanto influye tener internet en casa en los resultados de Saber 11?
2. ¿Cómo cambia el rendimiento entre zonas rurales y urbanas según la conectividad?
3. ¿La pobreza afecta más que el acceso a internet?
4. ¿Qué diferencia hay entre municipios con alta vs baja conectividad?
5. ¿Qué variables explican mejor el desempeño: lo económico o lo digital?
6. ¿Cómo se relaciona la cobertura educativa con la conectividad?
7. ¿Tener computador en casa realmente hace diferencia?
8. ¿Existen municipios con buen internet pero malos resultados? ¿qué está pasando ahí?

---

## Extras (bonos)

- Consumo de API / datos abiertos (Saber 11 vía Socrata) y clima (OpenWeatherMap)
- Visualizaciones con matplotlib
- Uso de Zotero para referencias

---

## Contexto académico

Proyecto del curso **Procesamiento de Datos a Gran Escala**, 
Grupo REST pAPIs
- Juan Pablo Cañón
- Juan Camilo Carvajal
- Juan David Rincón
- Tatiana Vivas
Pontificia Universidad Javeriana.
