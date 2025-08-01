# Reconocimiento de Actividades Humanas con Redes Neuronales Profundas

Proyecto con una Red Neuronal Profunda (DNN) para clasificación utilizando el dataset "Human Activity Recognition Using Smartphones Dataset" (HAR). 
Este dataset contiene lecturas de sensores de smartphones que intentan identificar la actividad realizada por una persona (caminar, estar sentado, subiendo escaleras, etc.).
- **Maestrante:**   Ing. Ludwing Young  
- **Docente:**      M.Sc. Ing. Marcelo Invert Palma Salas  
---
## Introducción al Reconocimiento de Actividades Humanas (HAR)
El Reconocimiento de Actividades Humanas (HAR, por sus siglas en inglés) es una disciplina del aprendizaje automático orientada a identificar patrones de movimiento humano a partir de datos recolectados por sensores, como acelerómetros y giroscopios. Este tipo de análisis tiene aplicaciones en:
- Monitorización de la salud y rehabilitación.
- Dispositivos wearables y deporte.
- Sistemas inteligentes de vigilancia.
- Interacción hombre-máquina.

## Descripción del Dataset
El dataset utilizado es el "Human Activity Recognition Using Smartphones Dataset", recopilado por el grupo de investigación de la Universidad de California, Irvine (UCI). Contiene datos recolectados de 30 sujetos mientras realizaban seis actividades físicas portando un smartphone en la cintura:
- WALKING (CAMINAR)
- WALKING_UPSTAIRS (SUBIR ESCALERAS)
- WALKING_DOWNSTAIRS (BAJAR ESCALERAS)
- SITTING (SENTARSE)
- STANDING (ESTAR DE PIE)
- LAYING (ACOSTARSE)

### Características del dataset:
- Entrada (X_train, X_test): 561 características numéricas extraídas de las señales del acelerómetro y giroscopio.
- Salida (y_train, y_test): Etiquetas que representan las actividades.

## Importancia de la Normalización
La normalización de datos es una etapa crítica en el preprocesamiento cuando se trabaja con modelos de machine learning y deep learning, especialmente en problemas como el reconocimiento de actividades humanas (HAR) con redes neuronales profundas (DNN).

En el dataset HAR, los datos provienen de acelerómetros y giroscopios, cuyas mediciones pueden variar ampliamente en magnitud (por ejemplo, aceleración en metros/segundo² vs. rotación angular). Si no se normalizan, las características con valores mayores dominarán el aprendizaje.

**Evita problemas de convergencia lenta o inestable:**
- Los algoritmos de optimización como Adam o SGD funcionan mejor cuando los datos están en rangos similares. La normalización mejora la velocidad de convergencia y estabiliza el proceso de entrenamiento.

**Mejora la precisión del modelo:**
- Un modelo entrenado con datos no normalizados puede obtener una peor precisión y peor capacidad de generalización.

**Evita que los pesos aprendidos sean distorsionados:**
- Si una característica tiene un rango mucho mayor que otras, los pesos asociados a ella serán exageradamente grandes, lo que desequilibra la red.

## Red Neuronal Profunda (DNN)
Una Red Neuronal Profunda es un tipo de modelo de deep learning que consiste en múltiples capas ocultas entre la capa de entrada y la de salida. Es capaz de modelar relaciones no lineales complejas y aprender representaciones jerárquicas de los datos.

### Ventajas de usar DNN para HAR:
- Aprende automáticamente combinaciones de características relevantes.
- No requiere tanta ingeniería manual de características.
- Escalable y aplicable a otros conjuntos de datos HAR.

## Arquitectura Propuesta
La red DNN diseñada incluye:
- Capa de entrada: 561 neuronas, una por cada característica del conjunto de datos.
- Varias capas ocultas: con funciones de activación ReLU, que introducen no linealidades.
- Capa de salida: 6 neuronas con activación softmax (en caso de clasificación multiclase).
- Función de pérdida: categorical_crossentropy.
- Optimizador: Adam, que ofrece un buen equilibrio entre rendimiento y eficiencia.
- Métricas: Accuracy y F1-score, para medir la calidad del modelo.

## Evaluación del Modelo
Se utiliza un conjunto de prueba independiente (X_test, y_test) para evaluar la capacidad de generalización del modelo entrenado.

### Métricas clave:
- Accuracy: Porcentaje de predicciones correctas.
- Matriz de confusión: Visualiza errores de clasificación entre clases.
- Reporte de clasificación (Precision, Recall, F1-Score): Evalúa el desempeño por clase.

## Visualización y Análisis
Para tener una mejor comprensión del comportamiento del modelo, se incluyen gráficos de:
- Distribución de clases en los datos de entrenamiento.
- Curvas de pérdida y accuracy durante el entrenamiento.
- Matriz de confusión.
- Ejemplos de predicciones correctas e incorrectas.
---
