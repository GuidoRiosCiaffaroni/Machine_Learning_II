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


# 3. METODOLOGÍA Y DESARROLLO EXPERIMENTAL

## 3.1. Descripción del Dataset (Tomato PlantVillage)
El conjunto de datos utilizado proviene de una versión curada de *PlantVillage*, centrada exclusivamente en el cultivo del tomate. Este dataset comprende imágenes de alta resolución clasificadas en 10 categorías:
* **Enfermedades Fúngicas/Bacterianas:** *Early Blight, Late Blight, Septoria Leaf Spot, Leaf Mold, Bacterial Spot, Target Spot.*
* **Ataques de Plagas:** *Spider Mites (Ácaros).*
* **Infecciones Virales:** *Tomato Mosaic Virus, Tomato Yellow Leaf Curl Virus.*
* **Control:** *Healthy* (Hojas sanas).

## 3.2. Pipeline de Procesamiento de Datos

### 3.2.1. Adquisición Eficiente: Sparse Checkout de GitHub
Para optimizar el almacenamiento en el entorno de Google Colab y evitar la descarga de archivos innecesarios del repositorio, se implementó la técnica de **Sparse Checkout** de Git. Este procedimiento permite clonar únicamente la subcarpeta `/DataImg/TomatoDataset_ready`, reduciendo el tiempo de preparación del entorno de minutos a segundos.



### 3.2.2. Preprocesamiento: Resizing, Normalización y Augmentation
Para garantizar la convergencia de los modelos, se aplicaron las siguientes transformaciones:
* **Redimensionamiento (Resizing):** Ajuste de todas las imágenes a $224 \times 224$ píxeles, estándar para la arquitectura EfficientNet.
* **Normalización:** Reescalado de los valores de píxeles de $[0, 255]$ a un rango de $[0, 1]$ o $[-1, 1]$ según los requisitos del modelo base.
* **Data Augmentation:** Se aplicaron rotaciones aleatorias, zooms y volteos horizontales para aumentar la variabilidad del set de entrenamiento y prevenir el sobreajuste ante cambios de iluminación o ángulo en campo.

---

## 3.3. Configuración de Modelos y Entrenamiento

### 3.3.1. Implementación de EfficientNet End-to-End
Se utilizó **EfficientNet-B0** con pesos pre-entrenados de *ImageNet* (Transfer Learning). 
1. **Fine-tuning:** Se congelaron las primeras capas para conservar los detectores de bordes y texturas universales.
2. **Capa Superior:** Se añadió una capa de *Global Average Pooling* seguida de una capa *Dense* con activación **Softmax** para la clasificación de las 10 clases.
3. **Optimización:** Uso del optimizador **Adam** con una tasa de aprendizaje adaptativa y función de pérdida *Categorical Cross-Entropy*.

### 3.3.2. Generación de Embeddings para Modelos Híbridos
Para los modelos KNN y Random Forest, se utilizó el cuerpo de la red EfficientNet como un **extractor de características**. Al eliminar la capa de clasificación final, el modelo transforma cada imagen en un vector de características (*embedding*) de 1280 dimensiones. Estos vectores sirven como entrada (X) para los algoritmos clásicos, permitiendo comparar el poder de clasificación de una red densa frente a estructuras de árboles o vecindad.



---

## 3.4. Entorno de Desarrollo y Librerías
El desarrollo se realizó íntegramente en lenguaje **Python 3.x** utilizando las siguientes bibliotecas:
* **TensorFlow / Keras:** Para la construcción, entrenamiento y evaluación de redes neuronales profundas.
* **Scikit-Learn:** Para la implementación de KNN, Random Forest, Elastic Net y el cálculo de métricas de validación.
* **OpenCV / PIL:** Para la manipulación y lectura de imágenes.
* **Matplotlib / Seaborn:** Para la visualización de curvas de aprendizaje y matrices de confusión.


# 4. ANÁLISIS DE RESULTADOS Y COMPARATIVA

## 4.1. Métricas de Evaluación de Desempeño

### 4.1.1. Accuracy, Precision, Recall y F1-Score
Para evaluar el desempeño de los modelos, se utilizaron métricas que permiten entender el comportamiento del sistema ante clases desbalanceadas:
* **Accuracy (Exactitud):** Proporción total de predicciones correctas.
* **Precision:** Capacidad del modelo para no clasificar como positiva una muestra que es negativa (evitar falsos positivos).
* **Recall (Sensibilidad):** Crucial en fitosanidad; mide la capacidad de detectar todas las hojas enfermas (evitar falsos negativos).
* **F1-Score:** Media armónica entre Precision y Recall, proporcionando una métrica equilibrada para la salud general del modelo.



### 4.1.2. Análisis de la Matriz de Confusión
La matriz de confusión reveló que el modelo **EfficientNet** tiene una alta capacidad de discriminación. Sin embargo, se observaron confusiones leves entre *Tomato Mosaic Virus* y *Target Spot* debido a patrones de manchas similares. El modelo **KNN** mostró mayores dificultades en la clase *Late Blight*, confundiéndola con estados de degradación natural de la hoja.



---

## 4.2. Comparación de Modelos: Deep Learning vs. ML Clásico

### 4.2.1. Capacidad de Generalización
El análisis comparativo arrojó los siguientes resultados tras la validación en el conjunto de prueba (Test Set):

| Modelo | Accuracy | F1-Score (Macro) | Desempeño |
| :--- | :--- | :--- | :--- |
| **EfficientNet (End-to-End)** | **0.93** | **0.91** | Excelente: Captura patrones no lineales complejos. |
| **KNN (sobre Embeddings)** | 0.90 | 0.88 | Bueno: Muy eficaz pero sensible a la densidad de datos. |
| **Random Forest** | 0.87 | 0.84 | Aceptable: Robusto pero con menor detalle fino. |

**EfficientNet** demostró ser el modelo más robusto, manteniendo su precisión incluso ante variaciones de luz presentes en el set de prueba, mientras que los modelos basados en *embeddings* dependieron críticamente de la calidad de la extracción de características previa.

### 4.2.2. Costo Computacional y Tiempo de Inferencia
Un factor determinante para el despliegue en la Región de Los Lagos es la velocidad de respuesta en dispositivos IoT:
* **EfficientNet:** Mayor costo en entrenamiento (GPU requerida), pero inferencia optimizable mediante TFLite (~45ms).
* **KNN / RF:** Entrenamiento extremadamente rápido, pero la fase de inferencia de KNN puede ralentizarse si el set de referencia es muy extenso.
* **Elastic Net:** El más rápido (~8ms), pero con una precisión insuficiente (0.78) para aplicaciones de seguridad fitosanitaria.

---

## 4.3. Discusión de Errores y Casos Críticos
Se identificaron tres escenarios donde el sistema presenta desafíos:
1. **Oclusión Parcial:** Hojas cubiertas por otras hojas o restos de tierra disminuyen la confianza del modelo.
2. **Etapas Muy Tempranas:** Los síntomas iniciales de *Early Blight* pueden confundirse con deficiencias nutricionales (clorosis), lo que sugiere que el modelo se beneficia de la incorporación de contexto temporal.
3. **Similitud Visual Intra-clase:** Ciertas virosis presentan mosaicos foliares casi idénticos, donde solo el modelo profundo logró extraer diferencias texturales suficientes para una clasificación correcta.




# 5. PROPUESTA DE DESPLIEGUE OPERACIONAL (IoT)

## 5.1. Arquitectura del Sistema: Edge vs. Cloud
Para garantizar la operatividad del sistema en zonas rurales de la Región de Los Lagos (como el archipiélago de Chiloé), donde la conectividad a internet es intermitente, se propone una arquitectura híbrida:

* **Inferencia en el Edge (Local):** El modelo reside directamente en el dispositivo del agricultor (Smartphone o cámara IoT con Raspberry Pi). Esto permite diagnósticos instantáneos sin latencia y sin depender de señal de red.
* **Gestión en la Nube (Cloud):** Los resultados se sincronizan de manera diferida cuando el dispositivo detecta una conexión estable. La nube se utiliza para el re-entrenamiento del modelo con nuevos datos de campo y para generar mapas epidemiológicos regionales.






## 5.2. Optimización para Dispositivos Móviles (TensorFlow Lite)
Debido a que los modelos de Deep Learning como **EfficientNet** son computacionalmente costosos, se implementa una etapa de post-procesamiento tras el entrenamiento:
1.  **Cuantización:** Reducción de la precisión de los pesos del modelo de 32 bits (float32) a 8 bits (int8). Esto reduce el tamaño del archivo en un 75% sin una pérdida significativa de precisión.
2.  **Conversión a TFLite:** Transformación del modelo de Keras al formato **TensorFlow Lite**, optimizado específicamente para procesadores móviles y aceleradores de hardware (NPU/GPU móvil).
3.  **Baja Latencia:** El objetivo es lograr una inferencia en menos de **100ms**, permitiendo un escaneo fluido de las hojas mediante la cámara en tiempo real.

## 5.3. Interfaz de Usuario y Notificaciones Fitosanitarias
La interacción con el agricultor se basa en un diseño de **decisión asistida**:
* **Captura de Imagen:** Interfaz intuitiva que guía al usuario para encuadrar la hoja y asegurar una iluminación adecuada.
* **Reporte de Diagnóstico:** En pantalla se muestra el nombre de la enfermedad detectada y el **nivel de confianza** del modelo (ej. *Late Blight - 94% de probabilidad*).
* **Alertas de Acción:** Si la confianza supera un umbral crítico (ej. >85%), el sistema envía una notificación push con recomendaciones agronómicas inmediatas, como el aislamiento de la planta o el uso de tratamientos específicos autorizados por el SAG.
* **Historial Georreferenciado:** Cada captura queda registrada con coordenadas GPS para facilitar el seguimiento de la propagación de focos infecciosos en el predio.


# 6. CONCLUSIONES Y TRABAJO FUTURO

## 6.1. Síntesis de Hallazgos Técnicos
Tras el desarrollo y evaluación del proyecto, se han consolidado los siguientes hallazgos:
* **Superioridad de EfficientNet:** La arquitectura *end-to-end* demostró ser la más robusta con un **93% de precisión**, validando que el escalamiento compuesto es ideal para capturar la complejidad morfológica de las enfermedades foliares.
* **Modelos Híbridos (Embeddings):** Los modelos como **KNN (90%)** y **Random Forest (87%)** demostraron ser alternativas viables y altamente eficientes. Se concluye que el uso de *embeddings* es una estrategia poderosa cuando se requiere reducir el tiempo de entrenamiento sin sacrificar drásticamente la capacidad predictiva.
* **Lección de las Actividades Previas:** A diferencia de los problemas de *churn* (donde las redes neuronales no superaron significativamente a los modelos clásicos), en visión artificial el **Deep Learning es indispensable** debido a la naturaleza no estructurada de los píxeles.

## 6.2. Impacto Socioeconómico y Ambiental
La implementación de este sistema en la **Región de Los Lagos** trasciende lo técnico:
* **Económico:** Al reducir el margen de error en el diagnóstico, se minimizan las pérdidas productivas que actualmente alcanzan el 40%, protegiendo la rentabilidad de los agricultores locales.
* **Ambiental:** La detección temprana permite transitar de un modelo de fumigación "calendario" (preventivo a ciegas) a uno de **aplicación dirigida**, reduciendo significativamente la carga química en los suelos y acuíferos de Chiloé.
* **Sostenibilidad:** El proyecto fomenta la adopción de tecnologías de Agricultura 4.0 en comunidades rurales, cerrando la brecha digital en el sector agrícola.



## 6.3. Recomendaciones para Escalabilidad del Sistema
Para la evolución del proyecto **PlantVille**, se proponen las siguientes líneas de acción:
1.  **Transfer Learning Multicultivo:** Expandir el entrenamiento hacia la detección de enfermedades en la **papa**, dada su relevancia crítica en la zona sur de Chile, reutilizando la base de conocimientos de EfficientNet.
2.  **Fusión Sensorial:** Integrar el modelo de visión con sensores IoT de humedad y temperatura. El contexto ambiental puede actuar como un "prior" estadístico para aumentar la precisión en casos visualmente ambiguos.
3.  **Active Learning:** Implementar un mecanismo donde las imágenes con baja confianza del modelo sean etiquetadas por expertos agrónomos y reincorporadas automáticamente al set de entrenamiento, permitiendo que el sistema aprenda continuamente de casos atípicos en terreno.
4.  **Optimización para Hardware Específico:** Investigar el uso de aceleradores como *Coral Edge TPU* para llevar la inferencia a microcontroladores de consumo ultrabajo, permitiendo un monitoreo autónomo mediante drones o estaciones fijas.


# 7. REFERENCIAS BIBLIOGRÁFICAS

* **Chollet, F.** (2021). *Deep Learning with Python* (2nd ed.). Manning Publications. (Referencia para el uso de Keras y TensorFlow en los notebooks A3 y A4).
* **Guo, Y., Liu, Y., Oerlemans, A., Lao, S., Wu, S., & Lew, M. S.** (2016). Deep learning for visual understanding: A review. *Neurocomputing*, 187, 27-48.
* **Hughes, D. P., & Salathé, M.** (2015). An open access repository of images on plant health to enable the development of mobile disease diagnostics. *arXiv preprint arXiv:1511.08060*. (Referencia técnica del dataset PlantVillage utilizado en PlantVille_05).
* **Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., ... & Duchesnay, E.** (2011). Scikit-learn: Machine learning in Python. *Journal of Machine Learning Research*, 12, 2825-2830. (Referencia para las implementaciones de KNN, Random Forest y Elastic Net).
* **Tan, M., & Le, Q. V.** (2019). EfficientNet: Rethinking model scaling for convolutional neural networks. *International Conference on Machine Learning (ICML)*. (Fundamento de la arquitectura utilizada en el proyecto final).
* **Universidad de las Américas.** (2025). *Hacia una Agricultura de Precisión en Chiloé: Sistema Basado en Deep Learning e IoT*. Núcleo de Investigación en Data Science (NIDS).

---

# 8. ANEXOS

## Anexo A: Repositorios de Código y Notebooks
El desarrollo técnico de este proyecto se encuentra documentado en los siguientes archivos de Jupyter Notebook, los cuales contienen el código fuente, las celdas de entrenamiento y las visualizaciones de métricas:

1.  **Fundamentos de Redes Neuronales:**
    * `A1_006_.ipynb`: Implementación del Perceptrón simple y carga de datos.
    * `A2_008.ipynb`: Análisis de métricas de negocio (Recall vs. Precision).
    * `A3_003.ipynb`: Redes Neuronales Artificiales y validación cruzada.
    * `A4_14_D.ipynb`: Comparativa entre MLP y modelos clásicos.

2.  **Proyecto Final PlantVille:**
    * `PlantVille_05.ipynb`: Pipeline de descarga (Sparse Checkout) y preprocesamiento de imágenes.
    * `KNN_002.ipynb` / `RF_003.ipynb` / `EN_010.ipynb`: Entrenamiento de modelos basados en embeddings.
    * `Comparacion_04.ipynb`: Evaluación final y contraste de métricas entre EfficientNet, KNN y Random Forest.

## Anexo B: Glosario de Términos Técnicos
* **Backpropagation:** Algoritmo fundamental para el entrenamiento de redes neuronales que calcula el gradiente de la función de pérdida respecto a los pesos.
* **Data Augmentation:** Técnica de creación de nuevos datos sintéticos a partir de los existentes (rotaciones, espejados) para mejorar la generalización.
* **Edge Computing:** Procesamiento de datos que ocurre cerca de la fuente (el dispositivo IoT), reduciendo la necesidad de enviar datos a la nube.
* **Embedding:** Representación vectorial de baja dimensionalidad que captura las características semánticas de un dato de entrada (como una imagen).
* **F1-Score:** Métrica que combina Precision y Recall; es especialmente útil cuando las clases de enfermedades están desbalanceadas.
* **Transfer Learning:** Técnica que consiste en tomar un modelo pre-entrenado en un dataset masivo (ImageNet) y adaptarlo a una tarea específica (detección de enfermedades de plantas).