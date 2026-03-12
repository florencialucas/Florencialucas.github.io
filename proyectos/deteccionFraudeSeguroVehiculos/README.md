**METODOLOGÍA Y PRINCIPALES RESULTADOS**

**METODOLOGÍA**

*Dataset utilizado*

https://www.kaggle.com/datasets/tajamulkhan/fraud-oracle


*1. Análisis Exploratorio de Datos (EDA)*

Se realizó un análisis exploratorio para comprender la estructura del dataset y las relaciones entre variables.
Esto incluyó:
- Análisis de variables numéricas (edad del conductor, días hasta reportar el siniestro, etc.).
- Análisis de variables categóricas.
- Identificación de valores duplicados y valores cero.
- Visualización de patrones de fraude en diferentes variables

*2. Ingeniería de Variables*

Se aplicaron distintas técnicas para mejorar la capacidad predictiva del modelo:
- Agrupación de niveles categóricos con baja frecuencia (<100 observaciones).
- Transformación de variables categóricas a formato numérico.
- Generación de nuevas variables relevantes para la detección de fraude

*3. Preprocesamiento de Datos*

Previo al entrenamiento de los modelos:
- El dataset fue dividido en conjunto de entrenamiento y prueba (80/20)
- Se aplicaron técnicas de one-hot-encoding de variables categóricas.
- Se realizaron transformaciones necesarias para mejorar el desempeño de los modelos.

*4. Entrenamiento de Modelos*

 Se implementaron y compararon distintos algoritmos de machine learning:
- Regresión Logística (modelo base): Simple pero limitada. No logra capturar patrones de fraude complejos y no lineales.
- Random Forest: Mejora en la capacidad de modelar relaciones complejas, aunque existen algoritmos más eficientes.
- XGBoost: Potente método de boosting, pero menos eficiente para manejar variables categóricas con alta cardinalidad.
- CatBoost: Mejor manejo de variables categóricas y mayor estabilidad en la clasificación del riesgo de fraude.
- CatBoost (ajustado): A pesar de aplicar una optimización rigurosa en dos fases, las métricas se mantuvieron estables.
  
Los modelos fueron evaluados utilizando métricas adecuadas para problemas de clasificación desbalanceada, priorizando:
- Recall
- F1-score
- ROC-AUC
- Gini
  
La métrica de accuracy se consideró de forma complementaria debido al desbalance en la variable objetivo


**RESULTADOS**

<img width="536" height="181" alt="image" src="https://github.com/user-attachments/assets/81e082cd-df5d-4701-a5f3-a9628ac5bc2d" />

El modelo CatBoost obtuvo el mejor desempeño general, especialmente en términos de recall, métrica clave en problemas de detección de fraude ya que el objetivo principal es identificar la mayor cantidad posible de casos fraudulentos.

*Graficos principales*

1- El modelo permite priorizar las investigaciones de fraude de forma eficiente, concentrando los recursos en los casos con mayor probabilidad de frauge. Es decir, con esta estrategia se logra detectar la mayoria de los fraudes revisando solo una fraccion del total de siniestros.
<img width="861" height="630" alt="image" src="https://github.com/user-attachments/assets/df8ab070-5a75-4f3a-a479-bfbdd7eb8f57" />

2- Las variables Fault y BasePolicy son los principales impulsores de la predicción de fraude, seguidas por factores relacionados con el comportamiento del reporte del siniestro. El resto de las variables presentan un impacto menor en el modelo. 

<img width="790" height="563" alt="image" src="https://github.com/user-attachments/assets/ee7d6c41-46e8-44aa-ae8e-c3a71c4c922c" />







