# 🧾 Introducción
En las empresas de las telecomunicaciones, retener clientes es tan importante como adquirir nuevos. El abandono de clientes (churn) representa una pérdida significativa de ingresos para las empresas del sector. Comprender los factores que influyen en la decisión de un cliente de cancelar un servicio se vuelve clave para anticipar comportamientos futuros y tomar acciones preventivas.

Gracias al crecimiento del análisis de datos y la inteligencia artificial, hoy es posible aplicar modelos de machine learning que permiten detectar patrones de comportamiento y predecir qué clientes tienen mayor riesgo de abandonar el servicio. Esta capacidad predictiva no solo optimiza campañas de fidelización, sino que también mejora la experiencia general del cliente y la eficiencia operativa de la empresa.

# 🎯 Objetivo del Proyecto
Este proyecto tiene como objetivo predecir si un cliente abandonará el servicio basándose en su comportamiento y características contractuales, utilizando técnicas de ciencia de datos y aprendizaje automático.

Para ello, se empleará el dataset público [Telco Customer Churn de Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn), que incluye información detallada sobre miles de clientes de una empresa de telecomunicaciones, como:
Género
Tiempo como cliente
Servicios contratados (internet, teléfono, seguridad, etc.)
Tipo de contrato y forma de pago
Cargos mensuales y totales
Y si el cliente ha abandonado o no la empresa (variable objetivo: Churn)
Entre otros...

# 🔍 2da Preentrega - Análisis y Exploración
## Exploración y Transformación
* Mostrar primeros 5 registros
* Mostrar últimos 5 registros
* Mostrar tipos de datos por columna
* Mostrar Cantidad de datos no nulos
* Mostrar Dimensiones del dataSet
* Transformación de columna TotalCharges en númerica
* Mostrar resumen estadistico de las columnas
* Sumar cantidad de nulos por columna
## Análisis
* Cálculo del promedio de meses de permanencia
* Cálculo del porcentaje de abandono general
* Cálculo del estimado que gasto el cliente durante su tiempo de permanencia.
* Realizamos detección de outliers
* Cálculo de porcentaje de permanencia en relación con el Método de Pago
* Cálculo de porcentaje de permanencia en relación con el Tipo de Contrato
* Cálculo de porcentaje de permanencia en relación con el Tipo de Servicio de Internet
## Gráficos
* Gasto mensual que poseen los clientes
* Antiguedad de clientes
* Relación entre tipo de contrato y abandono
* Relación entre género y abandono
* Relación entre gasto mensual y abandono
* Relación entre los tipos de servicios contratados y el abandono.

  # 🧠 3ra Preentrega – Clasificación Supervisada

En esta etapa se desarrollaron modelos de **aprendizaje supervisado** con el objetivo de predecir si un cliente abandonará el servicio (variable objetivo: `Churn`). Para ello, se probaron distintos algoritmos de clasificación, se aplicaron técnicas de balanceo de clases y se evaluaron los modelos con diferentes métricas.

El modelo que obtuvo mejores resultados fue **Random Forest**, optimizado con **GridSearchCV**, mostrando un buen desempeño general y equilibrio entre precisión y recall. Para mejorar la representación de las clases, se aplicó la técnica de sobremuestreo **SMOTE**, ya que el dataset original estaba desbalanceado.

## Pasos realizados
* Preprocesamiento completo del dataset
  * Conversión de `TotalCharges` a numérico y manejo de valores nulos
  * Codificación de variables categóricas
  * Escalado de los datos
* Separación en variables predictoras (`X`) y objetivo (`y`)
* Balanceo de clases con **SMOTE**
* División de datos en entrenamiento y testeo
* Entrenamiento y evaluación de múltiples modelos de clasificación:
  * Regresión Logística
  * Árbol de Decisión
  * Random Forest (con hiperparámetros ajustados por GridSearch)
  * K-Nearest Neighbors
* Evaluación con métricas como:
  * Accuracy
  * Precision
  * Recall
  * F1-score
  * Curva ROC y AUC
* Visualización de la importancia de variables con Random Forest
* Comparación de resultados entre modelos

## Conclusiones
El modelo final logró una **buena capacidad para detectar clientes en riesgo de abandonar** el servicio. La combinación de Random Forest + GridSearch + SMOTE permitió mejorar notablemente los resultados. Además, se concluyó que variables como el tipo de contrato, el gasto mensual y la antigüedad del cliente fueron claves para determinar el churn.

Este modelo puede ser utilizado por la empresa para anticiparse a la baja de clientes y aplicar estrategias de retención personalizadas.


# 📊 4ta Preentrega – Análisis No Supervisado (Clustering)

En esta etapa se aplicaron técnicas de aprendizaje no supervisado con el objetivo de identificar agrupamientos naturales de clientes basados en sus características y comportamientos. A diferencia de las etapas anteriores, en esta fase no se utilizó una variable objetivo como “Churn”, sino que se buscó descubrir patrones ocultos en los datos. Se consideró inicialmente la posibilidad de aplicar DBSCAN, ya que puede detectar grupos de diferentes formas y tamaños sin necesidad de predefinir el número de clusters, pero sus resultados no fueron satisfactorios debido a la sensibilidad a los parámetros y a que el dataset estaba muy estructurado. Por eso se optó por el algoritmo **K-Means**, que se adapta mejor a datos numéricos, escalados y con distribución uniforme, como los del dataset trabajado. Para determinar la cantidad óptima de clusters se utilizaron los métodos del Codo (Elbow) y el Score de Silhouette, y para facilitar la visualización de los grupos formados se aplicó **PCA** (Análisis de Componentes Principales), reduciendo la dimensionalidad a dos componentes principales.

## Pasos realizados
* Preprocesamiento del dataset (eliminación de columnas irrelevantes, codificación de variables categóricas, escalado)
* Eliminación de la variable `Churn` para respetar la lógica de análisis no supervisado
* Reducción de dimensionalidad con **PCA**
* Determinación del número óptimo de clusters con:
  * Método del Codo (Elbow Method)
  * Score de Silhouette
* Aplicación de **K-Means** con el valor óptimo de k
* Visualización final de los clusters en un gráfico 2D
* Conteo y análisis básico de la distribución de clientes por cluster

## ¿Para qué sirve este análisis?
Este tipo de segmentación permite a las empresas:
* Identificar perfiles de clientes con comportamientos similares
* Detectar grupos con mayor riesgo potencial de abandono (en futuras fases podrían cruzarse los clusters con la variable `Churn`)
* Diseñar estrategias específicas de fidelización para cada segmento

El análisis no supervisado complementa la predicción de abandono al aportar una mirada más estratégica sobre el conjunto total de clientes, incluso sin saber si se irán o no.

  
# 🛠️ Herramientas Utilizadas
* Python 🐍
* Pandas 📚
* NumPy 🔢
* Matplotlib & Seaborn 📊
* Scikit-learn 🤖
* Google Colab ☁️
