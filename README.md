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