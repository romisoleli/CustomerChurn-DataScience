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

# 🔍 Etapas del Proyecto (2da Pre - Entrega)
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

# 📊 4ta Preentrega – Análisis No Supervisado (Clustering)

En esta etapa, se aplicaron técnicas de aprendizaje no supervisado con el objetivo de identificar **agrupamientos naturales de clientes** basados en sus características y comportamientos. A diferencia de las etapas anteriores, en esta fase no se utiliza una variable objetivo como “Churn”, sino que se intenta descubrir patrones ocultos en los datos.

El algoritmo elegido fue **K-Means**, ya que se adapta bien a datos estructurados y escalados como los del dataset utilizado. Se tomaron decisiones informadas basadas en los métodos del Codo y Silhouette para definir el número óptimo de clusters. Además, se aplicó **PCA (Análisis de Componentes Principales)** para reducir la dimensionalidad y facilitar la visualización de los grupos formados.

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
