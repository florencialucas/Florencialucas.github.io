*METODOLOGIA Y PRINCIPALES RESULTADOS*

DATASET UTILIZADO: 
https://www.kaggle.com/datasets/tajamulkhan/fraud-oracle

*METODOLOGIA*

El proyecto sigue un flujo de trabajo estructurado de ciencia de datos para desarrollar un modelo de detección de fraude en siniestros de seguros de automóviles.

1. Análisis Exploratorio de Datos (EDA)
Se realizó un análisis exploratorio para comprender la estructura del dataset y las relaciones entre variables.
Esto incluyó:
- Análisis de variables numéricas (edad del conductor, días hasta reportar el siniestro, etc.).
- Análisis de variables categóricas.
- Identificación de valores duplicados y valores cero.
- Visualización de patrones de fraude en diferentes variables

2. Ingeniería de Variables
Se aplicaron distintas técnicas para mejorar la capacidad predictiva del modelo:
- Agrupación de niveles categóricos con baja frecuencia (<100 observaciones).
- Transformación de variables categóricas a formato numérico.
- Generación de nuevas variables relevantes para la detección de fraude

 3. Preprocesamiento de Datos
Previo al entrenamiento de los modelos:
- El dataset fue dividido en conjunto de entrenamiento y prueba.
- Se aplicaron técnicas de codificación de variables categóricas.
- Se realizaron transformaciones necesarias para mejorar el desempeño de los modelos.

4. Entrenamiento de Modelos
 Se implementaron y compararon distintos algoritmos de machine learning:
- Regresión Logística (modelo base)
- Random Forest
- XGBoost
- CatBoost
Los modelos fueron evaluados utilizando métricas adecuadas para problemas de clasificación desbalanceada, priorizando:
- Recall
- F1-score
- ROC-AUC
La métrica de accuracy se consideró de forma complementaria debido al desbalance en la variable objetivo

*RESULTADOS*
| Modelo              | Accuracy  | Recall    | ROC-AUC |
| ------------------- | --------- | --------- | ------- |
| Regresión Logística | 0.739     | 0.478     | 0.685   |
| Random Forest       | 0.779     | 0.559     | 0.603   |
| XGBoost             | 0.802     | 0.605     | 0.760   |
| CatBoost            | **0.823** | **0.647** | 0.617   |

El modelo CatBoost obtuvo el mejor desempeño general, especialmente en términos de recall, métrica clave en problemas de detección de fraude ya que el objetivo principal es identificar la mayor cantidad posible de casos fraudulentos.
Luego de realizar el ajuste de hiperparámetros, el modelo optimizado de CatBoost fue seleccionado como modelo final, logrando un mejor equilibrio entre la detección de fraude y el control de falsos positivos.

*Graficos principales*

1- El modelo permite priorizar las investigaciones de fraude de forma eficiente, concentrando los recursos en los casos con mayor probabilidad de frauge. Es decir, con esta estrategia se logra detectar la mayoria de los fraudes revisando solo una fraccion del total de siniestros.
<img width="861" height="630" alt="image" src="https://github.com/user-attachments/assets/df8ab070-5a75-4f3a-a479-bfbdd7eb8f57" />

