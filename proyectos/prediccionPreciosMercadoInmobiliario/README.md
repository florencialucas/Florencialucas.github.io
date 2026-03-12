**METODOLOOGÍA Y RESULTADOS**

**METODOLOGÍA**

*Dataset utilizado*

Datos de publicaciones inmobiliarias obtenidos mediante web scraping de los portales Mercado Libre y Gallito entre 2023 y 2025, con más de 550.000 registros de propiedades en Uruguay.

*1. Análisis Exploratorio de Datos (EDA)*

Se realizó un análisis exploratorio para comprender la estructura del dataset y las relaciones entre variables. Esto incluyó:
- Análisis de la distribución de precios de las propiedades.
- Evaluación de variables estructurales del inmueble (superficie, dormitorios, baños, etc.).
- Análisis por ubicación geográfica y diferencias entre zonas.
- Identificación de duplicados provenientes de múltiples extracciones del scraping.
- Detección de valores atípicos en variables relevantes como precio y superficie.

*2. Ingeniería y Limpieza de Datos*

Se aplicaron distintas técnicas para mejorar la calidad del dataset y la capacidad predictiva del modelo:
- Eliminación de duplicados exactos y temporales.
- Corrección de tipos de datos.
- Tratamiento de valores faltantes.
- Filtrado de observaciones con valores inconsistentes o extremos.

*3. Preprocesamiento de Datos*

Previo al entrenamiento de los modelos:
- El dataset fue dividido en conjunto de entrenamiento y prueba.
- Se aplicaron transformaciones necesarias en variables categóricas.
- Se prepararon las variables para su uso en algoritmos de machine learning

*4. Entrenamiento de Modelos*

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

1. Random Forest fue el modelo con mejor desempeño, alcanzando el menor error (RMSE = 43,194) y el mayor poder explicativo (R² = 0.79) entre los modelos evaluados


<img width="813" height="300" alt="image" src="https://github.com/user-attachments/assets/cc32e56a-4878-4581-9aee-f64921d682ae" />





2. Principales Variables Explicativas:

El Feature Importance del modelo valida que los atributos que mayor peso tienen en la determinación del precio son consistentes con el conocimiento del mercado:

- COVERED_AREA: La variable más relevante, reflejando el valor intrínseco de la propiedad.
- BATHROOMS: Un indicador clave de la funcionalidad y el confort de la unidad.
- BEDROOMS: Un factor fundamental en la segmentación del mercado y el tamaño del hogar.


<img width="995" height="855" alt="image" src="https://github.com/user-attachments/assets/308fdb9b-616f-4bb2-b2a9-819a0aba6040" />












