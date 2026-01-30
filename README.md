# ÍNDICE GENERAL

## 1. INTRODUCCIÓN Y JUSTIFICACIÓN
* **1.1. Contexto de la Agricultura en la Región de Los Lagos**
* **1.2. Problemática:** Impacto de las enfermedades foliares en cultivos hortícolas.
* **1.3. Objetivos del Proyecto**
    * 1.3.1. Objetivo General.
    * 1.3.2. Objetivos Específicos.
* **1.4. Alcance y Limitaciones**

---

## 2. MARCO TEÓRICO
* **2.1. Fundamentos de Machine Learning**
    * 2.1.1. Aprendizaje Supervisado y Clasificación Multiclase.
    * 2.1.2. El Perceptrón y Redes Neuronales Densas (MLP).
* **2.2. Visión por Computador y Redes Neuronales Convolucionales (CNN)**
    * 2.2.1. Arquitectura EfficientNet: Escalamiento Compuesto.
    * 2.2.2. Concepto de Embeddings y Extracción de Características.
* **2.3. Algoritmos de Machine Learning Clásico**
    * 2.3.1. K-Nearest Neighbors (KNN).
    * 2.3.2. Random Forest y Ensembles.
    * 2.3.3. Regularización con Elastic Net.

---

## 3. METODOLOGÍA Y DESARROLLO EXPERIMENTAL
* **3.1. Descripción del Dataset (Tomato PlantVillage)**
* **3.2. Pipeline de Procesamiento de Datos**
    * 3.2.1. Adquisición Eficiente: Sparse Checkout de GitHub.
    * 3.2.2. Preprocesamiento: Resizing, Normalización y Augmentation.
* **3.3. Configuración de Modelos y Entrenamiento**
    * 3.3.1. Implementación de EfficientNet End-to-End.
    * 3.3.2. Generación de Embeddings para Modelos Híbridos.
* **3.4. Entorno de Desarrollo y Librerías** (TensorFlow, Keras, Scikit-Learn).

---

## 4. ANÁLISIS DE RESULTADOS Y COMPARATIVA
* **4.1. Métricas de Evaluación de Desempeño**
    * 4.1.1. Accuracy, Precision, Recall y F1-Score.
    * 4.1.2. Análisis de la Matriz de Confusión.
* **4.2. Comparación de Modelos: Deep Learning vs. ML Clásico**
    * 4.2.1. Capacidad de Generalización.
    * 4.2.2. Costo Computacional y Tiempo de Inferencia.
* **4.3. Discusión de Errores y Casos Críticos**

---

## 5. PROPUESTA DE DESPLIEGUE OPERACIONAL (IoT)
* **5.1. Arquitectura del Sistema:** Edge vs. Cloud.
* **5.2. Optimización para Dispositivos Móviles** (TensorFlow Lite).
* **5.3. Interfaz de Usuario y Notificaciones Fitosanitarias.**

---

## 6. CONCLUSIONES Y TRABAJO FUTURO
* **6.1. Síntesis de Hallazgos Técnicos.**
* **6.2. Impacto Socioeconómico y Ambiental.**
* **6.3. Recomendaciones para Escalabilidad del Sistema.**

---

## 7. REFERENCIAS BIBLIOGRÁFICAS

## 8. ANEXOS
* **Anexo A:** Repositorios de Código y Notebooks (A1 - A4, PlantVille_05, Comparación).
* **Anexo B:** Glosario de Términos Técnicos.

# 1. INTRODUCCIÓN Y JUSTIFICACIÓN

## 1.1. Contexto de la Agricultura en la Región de Los Lagos
La Región de Los Lagos, y específicamente el archipiélago de **Chiloé**, posee una identidad agrícola marcada por la pequeña y mediana producción de hortalizas y tubérculos. Esta zona se caracteriza por un clima templado lluvioso con una humedad relativa persistentemente alta y precipitaciones frecuentes. 

Aunque estas condiciones son ideales para ciertos ciclos biológicos, también configuran un escenario crítico para la proliferación de patógenos fitosanitarios. Cultivos estratégicos para la seguridad alimentaria local, como el **tomate** y la **papa**, representan el sustento de miles de familias agricultoras que dependen de la sanidad de sus predios para mantener la viabilidad económica de sus hogares.

## 1.2. Problemática: Impacto de las enfermedades foliares en cultivos hortícolas
El principal desafío fitosanitario en la región es la detección tardía de enfermedades foliares (como el *Tizón Temprano*, *Tizón Tardío* y diversas virosis). Actualmente, el proceso de diagnóstico presenta tres deficiencias estructurales:
1. **Inspección Visual Manual:** Depende enteramente de la experiencia del agricultor, lo que suele derivar en diagnósticos erróneos o tardíos.
2. **Uso Indiscriminado de Agroquímicos:** Ante la duda, los productores aplican fungicidas de amplio espectro de forma preventiva o reactiva, aumentando los costos de producción y el impacto ambiental.
3. **Pérdidas Productivas:** Se estima que una detección tardía puede reducir el rendimiento de la cosecha hasta en un **40%**, comprometiendo la trazabilidad y la calidad del producto final.



## 1.3. Objetivos del Proyecto

### 1.3.1. Objetivo General
Desarrollar y evaluar un sistema inteligente de clasificación automática de enfermedades foliares en cultivos de tomate, integrando arquitecturas de **Deep Learning** y algoritmos de **Machine Learning clásico**, para proporcionar una herramienta de alerta temprana con alta precisión y viabilidad técnica en entornos de agricultura de precisión.

### 1.3.2. Objetivos Específicos
* **Implementar** un pipeline de procesamiento de imágenes eficiente mediante técnicas de *Sparse Checkout* y normalización de datos.
* **Entrenar y comparar** el desempeño de una red neuronal profunda (**EfficientNet**) frente a modelos basados en *embeddings* como **KNN** y **Random Forest**.
* **Analizar** las métricas de desempeño (Accuracy, F1-Score y Recall) para identificar el modelo con menor tasa de falsos negativos en la detección de patologías críticas.
* **Proponer** una arquitectura de despliegue basada en **IoT e inferencia local (Edge Computing)** para su aplicación en zonas con conectividad limitada en la Región de Los Lagos.

## 1.4. Alcance y Limitaciones
**Alcance:**
El proyecto abarca desde la adquisición de datos de la base *PlantVillage*, el preprocesamiento de imágenes RGB, el entrenamiento de múltiples modelos supervisados, hasta la comparativa técnica final. Se enfoca específicamente en 10 clases de estados de salud y enfermedades en hojas de tomate.

**Limitaciones:**
* **Condiciones Lumínicas:** Los modelos pueden presentar variaciones de precisión ante imágenes capturadas con iluminación extrema o fondos altamente ruidosos no presentes en el dataset de entrenamiento.
* **Hardware:** El despliegue operacional propuesto requiere dispositivos con capacidad de procesamiento suficiente para ejecutar modelos TFLite, lo que implica una inversión inicial en hardware IoT.
* **Variabilidad Biológica:** El sistema está entrenado para patologías específicas; nuevas cepas o enfermedades emergentes requerirían un re-entrenamiento del modelo.


# 2. MARCO TEÓRICO

## 2.1. Fundamentos de Machine Learning

### 2.1.1. Aprendizaje Supervisado y Clasificación Multiclase
El aprendizaje supervisado es una subcategoría de la Inteligencia Artificial donde el modelo aprende a partir de un conjunto de datos etiquetados. En este proyecto, se aborda un problema de **Clasificación Multiclase**, donde la variable objetivo ($y$) no es binaria, sino que comprende 10 categorías distintas (9 enfermedades específicas y un estado saludable). El modelo busca encontrar una función de mapeo $f(x)$ que minimice la discrepancia entre la etiqueta real y la predicción.

### 2.1.2. El Perceptrón y Redes Neuronales Densas (MLP)
Como se analizó en las actividades iniciales (**A1 y A2**), el Perceptrón es la unidad básica de aprendizaje. Al apilar estas unidades en múltiples capas, formamos el **Multi-Layer Perceptron (MLP)**. 
* **Backpropagation:** Algoritmo utilizado para ajustar los pesos mediante el gradiente de la función de pérdida.
* **Funciones de Activación:** Uso de **ReLU** en capas ocultas para evitar el desvanecimiento del gradiente y **Softmax** en la capa de salida para generar una distribución de probabilidad multiclase.

---

## 2.2. Visión por Computador y Redes Neuronales Convolucionales (CNN)

### 2.2.1. Arquitectura EfficientNet: Escalamiento Compuesto
A diferencia de las CNN convencionales que escalan una sola dimensión (profundidad, ancho o resolución), **EfficientNet** utiliza un método de **escalamiento compuesto**. Esto permite que el modelo sea significativamente más ligero y rápido sin sacrificar precisión, lo cual es vital para el despliegue en dispositivos de bajo consumo (IoT). En este proyecto se utiliza EfficientNet como el motor principal de clasificación *end-to-end*.

### 2.2.2. Concepto de Embeddings y Extracción de Características
Las capas profundas de una CNN actúan como extractores de características de alto nivel. Al eliminar la última capa de clasificación, podemos obtener un **Embedding**: un vector numérico que representa la "esencia visual" de la hoja. Este enfoque permite que modelos clásicos (KNN, RF) "entiendan" imágenes al procesar estos vectores en lugar de píxeles crudos.

---

## 2.3. Algoritmos de Machine Learning Clásico

### 2.3.1. K-Nearest Neighbors (KNN)
Es un algoritmo no paramétrico que clasifica una nueva muestra basándose en la etiqueta de los $k$ vecinos más cercanos en el espacio del embedding. Es altamente efectivo cuando las clases están bien separadas espacialmente, aunque su costo computacional aumenta con el tamaño del dataset.

### 2.3.2. Random Forest y Ensembles
Random Forest es un método de **Ensemble Learning** que construye múltiples árboles de decisión durante el entrenamiento. Su fuerza radica en el "Bagging" (Bootstrap Aggregating), lo que reduce el sobreajuste (overfitting) y permite evaluar la importancia de las características extraídas, ofreciendo mayor robustez frente al ruido visual.

### 2.3.3. Regularización con Elastic Net
Implementado como un modelo de referencia lineal, **Elastic Net** combina las penalizaciones $L_1$ (Lasso) y $L_2$ (Ridge). Su inclusión en este marco teórico se debe a su capacidad para manejar variables altamente correlacionadas y realizar una selección automática de características, sirviendo como una línea base de comparación para los modelos no lineales.