**METODOLOGÍA Y PRINCIPALES RESULTADOS**

**METODOLOGÍA**

*Dataset utilizado*:

“SMS Spam Collection Dataset” de Kaggle (https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset)

*1. Análisis Exploratorio de Datos (EDA)*

Se realizó un análisis exploratorio para comprender la estructura del dataset y las características de los mensajes. Esto incluyó:
- Identificación de las clases Ham (mensajes legítimos) y Spam (mensajes fraudulentos).
- Análisis del desbalance entre mensajes legítimos y fraudulentos.
- Revisión de ejemplos de mensajes para identificar patrones comunes de fraude.

*2. Preparación y Limpieza de Datos*

Para preparar el dataset para el entrenamiento del modelo se realizaron las siguientes tareas:
- Eliminación de mensajes duplicados.
- Renombrado de columnas para mayor claridad.
- División del dataset en conjunto de entrenamiento (80%) y prueba (20%) utilizando muestreo estratificado.
- Conversión del dataset al formato Hugging Face Datasets para su uso en modelos de deep learning.

*3. Preprocesamiento de Texto*

Se utilizó el enfoque de tokenización automática de Transformers, permitiendo que el modelo capture el contexto completo del lenguaje.

El proceso incluyó:
- Tokenización de los mensajes utilizando DistilBERT tokenizer.
- Conversión del texto en tokens e identificadores numéricos.
- Aplicación de padding y truncation para estandarizar la longitud de las secuencias.

Se implementó un modelo de Deep Learning basado en Transformers, específicamente:

- DistilBERT (versión optimizada y más ligera de BERT).
- Uso de Transfer Learning, aprovechando un modelo preentrenado en grandes corpus de texto.
- Aplicación de Fine-Tuning para adaptar el modelo al dominio de mensajes SMS bancarios.

 El entrenamiento se realizó utilizando la librería Hugging Face Transformers, con los siguientes parámetros principales:

- Learning rate: 2e-5
- Batch size: 16
- Número de épocas: 3
- Regularización: Weight decay para prevenir overfitting


*4. Métricas de Evaluación*

Debido al desbalance del dataset, el accuracy por sí solo no es suficiente, por lo que se evaluó el modelo utilizando:
- Accuracy
- F1-score (métrica principal para balancear precisión y recall)

**RESULTADOS**

El modelo basado en DistilBERT logró un desempeño muy alto en la clasificación de mensajes fraudulentos.

- Accuracy: 99.13%
- F1-score: 0.9653


*Principales gráficos*

La matriz de confusión muestra una capacidad de detección casi perfecta:
Solo 3 falsos positivos (mensajes legítimos clasificados como fraude).
6 falsos negativos (mensajes fraudulentos no detectados).

Al observar la Curva de Pérdida (Loss), notamos lo siguiente:

- Convergencia Rápida: La pérdida cae drásticamente de la época 1 a la 2, indicando que DistilBERT adapta su conocimiento previo al dominio bancario de forma eficiente.
- Optimización de Épocas: Mantener el entrenamiento en 3 épocas evita el overfitting, permitiendo que el modelo generalice ante nuevos tipos de fraude sin memorizar el dataset de entrenamiento.



<img width="1459" height="590" alt="image" src="https://github.com/user-attachments/assets/e6a3e478-3b2d-4d69-91d6-2154df96488c" />






