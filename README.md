# Challange.X2
# Predicción de Cancelación de Clientes 

##  Descripción del proyecto

Este proyecto tiene como objetivo **predecir la cancelación de clientes (churn)** utilizando distintos modelos de *Machine Learning*, así como **identificar los factores más influyentes** que explican el abandono de clientes.

El análisis combina modelos **interpretables** y **modelos más robustos**, permitiendo no solo obtener buenas predicciones, sino también generar **insights accionables** para la toma de decisiones de negocio.


##  Objetivos

- Predecir si un cliente cancelará el servicio.
- Comparar modelos con y sin normalización.
- Evaluar el rendimiento usando métricas adecuadas.
- Identificar las variables más relevantes en la cancelación.
- Proponer estrategias de retención basadas en los resultados.

## Modelos utilizados

###  Regresión Logística
- Modelo lineal e interpretable.
- Requiere **normalización** de las variables.
- Permite analizar coeficientes para entender el impacto de cada variable.

###  K-Nearest Neighbors (KNN)
- Modelo basado en **distancia entre observaciones**.
- Sensible a la escala de los datos → se utilizó normalización.
- La importancia de variables se analizó mediante *Permutation Importance*.

###  Random Forest
- Modelo no lineal basado en árboles de decisión.
- **No requiere normalización**.
- Proporciona importancia de variables basada en la reducción de impureza.
- Fue el modelo con **mejor desempeño global**.

##  Preprocesamiento de datos

- Limpieza de datos y selección de variables relevantes.
- Normalización de variables numéricas para modelos sensibles a la escala.
- Separación del dataset en conjuntos de entrenamiento y prueba.

##  Evaluación de los modelos

Los modelos fueron evaluados utilizando las siguientes métricas:

- **Exactitud (Accuracy)**
- **Precisión (Precision)**
- **Recall (Sensibilidad)**
- **F1-score**
- **Matriz de confusión**

 En el contexto de churn, se priorizó el **Recall y el F1-score**, ya que es más costoso no detectar a un cliente que realmente va a cancelar.



##  Resultados principales

- **Random Forest** obtuvo el mejor desempeño general, con mayor F1-score y mejor capacidad para detectar clientes que cancelan.
- **Regresión Logística** mostró resultados estables y fue clave para la interpretación de variables.
- **KNN** permitió identificar patrones de similitud entre clientes, aunque fue más sensible a la elección de parámetros.



##  Análisis de variables relevantes

### Regresión Logística
- Variables con coeficientes positivos aumentan la probabilidad de cancelación.
- Variables con coeficientes negativos actúan como factores de retención.

### KNN
- Las variables más influyentes son aquellas que más afectan la proximidad entre clientes.
- Se utilizó *Permutation Importance* para medir su impacto.

### Random Forest
- Identificó como variables clave:
  - Antigüedad del cliente
  - Nivel de uso del servicio
  - Cantidad de reclamos
  - Tipo de contrato o plan
  - Costos asociados


##  Factores clave que influyen en la cancelación

A partir del análisis conjunto, los principales factores de churn fueron:

- Bajo uso o engagement con el servicio.
- Experiencias negativas (reclamos, incidencias).
- Baja antigüedad del cliente.
- Percepción de alto costo o bajo valor.
- Planes poco flexibles o no adecuados al perfil del cliente.


##  Estrategias de retención propuestas

- **Detección temprana** de clientes con riesgo de churn.
- Acciones proactivas en clientes nuevos.
- Mejora del soporte y reducción de reclamos.
- Planes y precios personalizados.
- Programas de fidelización basados en el uso del servicio.


##  Estructura del proyecto

```text
churn-prediction/
│
├── data/
│   └── dataset.csv
├── notebooks/
│   └── churn_model.ipynb
├── results/
│   ├── metricas_modelos.csv
│   ├── importancia_variables_rf.csv
│   └── coeficientes_regresion_logistica.csv
├── README.md
└── requirements.txt
