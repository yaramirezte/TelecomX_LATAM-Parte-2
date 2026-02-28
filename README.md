# 📞 Telecom X: Predicción de Churn (Parte 2)

Este proyecto tiene como objetivo analizar y predecir la **cancelación de clientes (Churn)** para una empresa de telecomunicaciones. Mediante el uso de Machine Learning, buscamos identificar a los clientes con mayor riesgo de abandonar el servicio para facilitar estrategias de retención proactivas.

## 🎯 Propósito del Análisis
El objetivo principal es construir modelos predictivos que clasifiquen si un cliente cancelará su servicio (`Evasion = 1`) o no (`Evasion = 0`). Se pone especial énfasis en el **Recall**, ya que para el negocio es fundamental detectar la mayor cantidad de cancelaciones posibles.

---

📁 **Estructura del Proyecto**

```
Telecom-X-Parte-2/
│
├── TelecomX_LATAM_parte_2.ipynb   # Cuaderno principal con el análisis y modelado.
├── data
│   ├──datos_tratados.csv          # Dataset limpio y procesado
├── README.md                      # Documentación del proyecto
│
└── visualizaciones                # Carpeta con los gráficos generados (boxplot, distribución de clases, etc.).
```

---

## 🛠️ Preparación de los Datos

El proceso de ingeniería de datos siguió estas etapas críticas:

1.  **Clasificación de Variables:**
    * **Numéricas:** Antigüedad (meses), Cargos Mensuales, Cargos Totales.
    * **Categóricas:** Tipo de contrato, método de pago, servicios contratados (Internet, Streaming, etc.).
2.  **Codificación (Encoding):** Transformación de variables categóricas mediante *One-Hot Encoding* y *Label Encoding* para su compatibilidad con los algoritmos.
3.  **Normalización/Estandarización:** Se aplicó `StandardScaler` a las variables numéricas para modelos sensibles a la escala (Regresión Logística).
   ![Comparación de Distribución Antes y Después del Escalado](visualizaciones/comparacion_escalado.png)
5.  **División de Datos:** El conjunto se dividió en **70%** entrenamiento y **30%** prueba, manteniendo la proporción original de la variable objetivo mediante estratificación (stratify=y). Esto permitió validar la capacidad de generalización de los modelos y manejar adecuadamente el desbalance de clases.

---

🤖 **Modelos Implementados**

Se desarrollaron dos modelos con enfoques distintos:

1.  **Regresión Logística:**
    * *Justificación:* Modelo basado en probabilidad. Requiere **estandarización** de datos para que las variables de mayor magnitud (como Cargos Totales) no sesguen los coeficientes.
2.  **Random Forest (Bosques Aleatorios):**
    * *Justificación:* Modelo basado en árboles de decisión. No requiere normalización, ya que es robusto a la escala de las variables y captura relaciones no lineales.
      
### Evaluación de Rendimiento
Cada modelo fue evaluado mediante:
* **Exactitud (Accuracy):** Nivel de acierto general.
* **Recall (Sensibilidad):** Capacidad de encontrar a los clientes que realmente se van.
* **F1-Score:** Balance entre precisión y recall.
* **Matriz de Confusión:** Visualización de falsos positivos y falsos negativos.

El modelo con mejor desempeño en términos de recall para la clase churn fue Random Forest ajustado, lo que lo convierte en el modelo más adecuado para detectar clientes en riesgo.

 <img src="visualizaciones/matriz_logistica.png" width="400"> <img src="visualizaciones/matriz_rf.png" width="400">
 
---

📊 **Análisis Exploratorio (EDA)**

Durante el análisis exploratorio se identificaron patrones clave:

🔎 **Tipo de Contrato vs Cancelación**

 ![Tipo de Contrato vs Cancelación](visualizaciones/Tipo_Contrato_vs_Evasión.png)

Los clientes con contrato mensual presentan mayor tasa de cancelación en comparación con contratos anuales.

**Insight:**
El nivel de compromiso contractual reduce significativamente el churn.

---

🔎 **Antigüedad del Cliente**

 ![Antigüedad del Cliente](visualizaciones/boxplot_antiguedad.png)

Clientes con menor antigüedad muestran mayor probabilidad de cancelar el servicio.

**Insight:**
El riesgo de churn es más alto en las primeras etapas del ciclo de vida del cliente.

---

🔎 **Cargos Mensuales**

![Distribución de Cargos](visualizaciones/distribucion_cargos.png)

Clientes con cargos mensuales elevados presentan mayor probabilidad de evasión.

**Insight:**
La percepción de valor y la estructura de precios influyen en la decisión de cancelación.

---

📈 **Importancia de Variables**

Según Random Forest, las variables más relevantes fueron:

- Antiguedad_Meses

- Tipo_Contrato_Two year

- Cargos_Totales

- Tipo_Contrato_One year

- Cargos_Mensuales

- Soporte_Tecnico

- Seguridad_Online

Estas variables explican gran parte del comportamiento de cancelación.

---

💡 **Principales Conclusiones**

Los principales factores que influyen en la cancelación son:

- Baja antigüedad

- Contratos mensuales

- Altos cargos mensuales

- Baja integración de servicios adicionales

El modelo desarrollado permite identificar clientes en riesgo y diseñar estrategias de retención basadas en datos.

---

🚀 **Estrategias Propuestas**

- Programas de fidelización en los primeros meses.

- Incentivos para migrar a contratos anuales.

- Planes personalizados para clientes con alto gasto.

- Promoción de servicios complementarios para aumentar integración.

---

⚙️ **Instrucciones para Ejecutar el Proyecto**
1️⃣ **Clonar el repositorio**

```
git clone https://github.com/yaramirezte/TelecomX_LATAM-Parte-2.git

```

2️⃣ **Instalar dependencias**

```
pip install pandas numpy matplotlib seaborn scikit-learn

```

3️⃣ **Ejecutar el Notebook**

Abrir:
```
TelecomX_LATAM_parte_2.ipynb
```
Asegurarse de que el archivo datos_tratados.csv esté en la misma carpeta del notebook.

---

📌 **Librerías Utilizadas**

- pandas

- numpy

- matplotlib

- seaborn

- scikit-learn



---

🏆 **Resultado Final**

Este proyecto demuestra cómo el análisis de datos y el Machine Learning pueden utilizarse para anticipar la cancelación de clientes y apoyar decisiones estratégicas en el negocio de telecomunicaciones.
