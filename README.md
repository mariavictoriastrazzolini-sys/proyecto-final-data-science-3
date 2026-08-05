**Clasificación de Reseñas de Películas con NLP y Redes Neuronales**

**Proyecto Final – Data Science III Autora: Maria Victoria Strazzolini**

**Descripción del proyecto**

Este proyecto desarrolla un modelo de análisis de sentimientos capaz de clasificar reseñas de películas del dataset IMDB como positivas o negativas, utilizando técnicas de Procesamiento de Lenguaje Natural (NLP) y una red neuronal implementada en TensorFlow/Keras.

El trabajo cubre el flujo completo de un proyecto de Machine Learning: desde la carga y exploración de los datos, pasando por el preprocesamiento de texto y la vectorización, hasta la construcción, entrenamiento, mejora y evaluación de dos arquitecturas de red neuronal.

**Motivación y contexto**

Las plataformas de streaming y sitios de reseñas reciben grandes volúmenes de comentarios de usuarios que resultan costosos de analizar manualmente. Un sistema automático de análisis de sentimientos permite detectar rápidamente la percepción del público sobre un contenido, aportando valor tanto a nivel comercial (priorización de contenido, marketing) como analítico (clasificación supervisada de texto no estructurado).

**Preguntas / hipótesis a resolver**

*   ¿Es posible clasificar automáticamente reseñas de películas en positivas o negativas utilizando técnicas básicas de NLP?

*   ¿La representación TF-IDF conserva suficiente información para realizar una clasificación efectiva?

*   ¿Una red neuronal densa simple puede alcanzar un desempeño adecuado en esta tarea?


**Objetivos**

*   Cargar y explorar el conjunto de datos IMDB.

*   Aplicar tareas básicas de preprocesamiento de texto.

*   Convertir las reseñas en vectores numéricos mediante TF-IDF.

*   Construir una red neuronal densa con TensorFlow/Keras.

*   Entrenar y evaluar el modelo utilizando métricas de clasificación.

*   Mejorar la arquitectura de la red para reducir el sobreajuste.


**Dataset**

Fuente: subconjunto de 10.000 reseñas del dataset IMDB.

**Variables:**

review	(object):Texto de la reseña

sentiment	(object):Sentimiento asociado (positive / negative)

**Metodología**

1. Análisis exploratorio (EDA)

*   Distribución de clases (balanceada entre positivas y negativas).

*   Análisis de longitud de reseñas, en general y por sentimiento.

*   Nubes de palabras para reseñas positivas y negativas.

2. Preprocesamiento de texto (NLP)
   
*   Conversión a minúsculas.

*   Eliminación de puntuación y caracteres especiales.

*   Eliminación de espacios extra.

*   Eliminación de stopwords (NLTK).

3. Preparación de datos
   
*   Codificación binaria de la variable objetivo (positive = 1, negative = 0).

*   División en entrenamiento (80%) y prueba (20%), estratificada por clase.

*   Vectorización de texto mediante TF-IDF (ajustado únicamente sobre el conjunto de entrenamiento para evitar data leakage).

4. Modelado (Deep Learning)
   
Modelo base: red densa con dos capas ocultas (128 y 64 neuronas, activación ReLU) y salida sigmoide.

Modelo mejorado: en línea con la consigna de profundizar la actividad de Deep Learning, se amplió la arquitectura agregando una capa adicional (256, 128 y 64 neuronas), junto con capas de Dropout y EarlyStopping para atenuar el sobreajuste observado en el modelo base.

5. Evaluación
   
*   Accuracy, Precision, Recall y F1 Score.

*   Matriz de confusión.

*   Reporte de clasificación.

*   Curva ROC y AUC.


**Resultados principales**

Accuracy	87,17%

Precision	88,04%

Recall	86,29%

F1 Score	87,16%

AUC-ROC	0,946

El modelo mejorado alcanza un desempeño equilibrado entre ambas clases. Si bien la incorporación de Dropout y EarlyStopping ayudó a controlar parte del sobreajuste, los gráficos de entrenamiento muestran que el modelo continúa ajustándose mejor a los datos de entrenamiento que a los de validación, lo que abre la puerta a futuras mejoras.

**Conclusiones y trabajo futuro**

El proyecto demuestra que es posible construir un clasificador de sentimientos efectivo combinando técnicas clásicas de NLP (TF-IDF) con una red neuronal densa. Como líneas futuras de trabajo se propone:

*   Comparar contra un modelo de Machine Learning clásico (Regresión Logística, Naive Bayes) como baseline.

*   Explorar representaciones basadas en embeddings (Word2Vec, GloVe) o arquitecturas recurrentes (LSTM/GRU).

*   Aplicar lematización u otras técnicas adicionales de preprocesamiento.

*   Realizar pruebas de inferencia sobre reseñas nuevas no vistas por el modelo.

**Tecnologías utilizadas**

*   Python

*   Pandas / NumPy

*   Matplotlib / Seaborn / WordCloud

*   NLTK

*   Scikit-learn

*   TensorFlow / Keras


**Estructura del repositorio**

├── Proyecto_Final_DSIII_Strazzolini_Maria_Victoria.ipynb   
└── README.md                                               

**Cómo ejecutar el proyecto**

Clonar el repositorio:

bash

   git clone <URL-del-repositorio>
   
Instalar las dependencias necesarias:

bash

   pip install pandas numpy matplotlib seaborn wordcloud nltk scikit-learn tensorflow
   
Abrir el notebook (.ipynb) en Jupyter Notebook, JupyterLab o Google Colab y ejecutar las celdas en orden.
