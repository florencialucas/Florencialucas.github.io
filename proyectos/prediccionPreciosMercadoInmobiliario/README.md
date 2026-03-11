**METODOLOOGÍA Y RESULTADOS**

**METODOLOGÍA**

*DATASET UTILIZADO*

Datos de publicaciones inmobiliarias obtenidos mediante web scraping de los portales Mercado Libre y Gallito entre 2023 y 2025, con más de 550.000 registros de propiedades en Uruguay.

El proyecto sigue un flujo de trabajo estructurado de ciencia de datos para desarrollar un modelo de predicción de precios del mercado inmobiliario.

*Análisis Exploratorio de Datos (EDA)*

Se realizó un análisis exploratorio para comprender la estructura del dataset y las relaciones entre variables. Esto incluyó:
- Análisis de la distribución de precios de las propiedades.
- Evaluación de variables estructurales del inmueble (superficie, dormitorios, baños, etc.).
- Análisis por ubicación geográfica y diferencias entre zonas.
- Identificación de duplicados provenientes de múltiples extracciones del scraping.
- Detección de valores atípicos en variables relevantes como precio y superficie.

*Ingeniería y Limpieza de Datos*

Se aplicaron distintas técnicas para mejorar la calidad del dataset y la capacidad predictiva del modelo:
- Eliminación de duplicados exactos y temporales.
- Corrección de tipos de datos.
- Tratamiento de valores faltantes.
- Filtrado de observaciones con valores inconsistentes o extremos.

*Preprocesamiento de Datos*

Previo al entrenamiento de los modelos:
- El dataset fue dividido en conjunto de entrenamiento y prueba.
- Se aplicaron transformaciones necesarias en variables categóricas.
- Se prepararon las variables para su uso en algoritmos de machine learning

*Entrenamiento de Modelos*

Se implementaron y compararon distintos algoritmos de regresión supervisada para predecir el precio de las propiedades:
- Regresión Lineal: Modelo base simple para capturar relaciones lineales entre variables.
- Random Forest: Permite capturar relaciones no lineales y reducir el riesgo de sobreajuste.
- XGBoost: Algoritmo de gradient boosting con alto desempeño en problemas tabulares.
- Modelos optimizados: Se aplicó optimización de hiperparámetros utilizando Optuna para mejorar el desempeño predictivo.

Los modelos fueron evaluados utilizando métricas de desempeño para problemas de regresión, incluyendo:
- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)
- R²

**RESULTADOS**

