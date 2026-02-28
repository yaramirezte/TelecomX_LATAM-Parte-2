📊 Telecom X – Parte 2

Predicción de Cancelación de Clientes (Churn)
---

🎯 **Propósito del Proyecto**

El objetivo principal de este análisis es **predecir la cancelación (churn) de clientes** en Telecom X utilizando técnicas de Machine Learning.

A través del análisis exploratorio de datos (EDA) y la implementación de modelos de clasificación, se busca:

- Identificar los factores que más influyen en la cancelación.

- Construir modelos predictivos capaces de anticipar clientes en riesgo.

- Proponer estrategias de retención basadas en evidencia analítica.

Este proyecto permite transformar datos históricos en una herramienta estratégica para la toma de decisiones empresariales.

---

📁 **Estructura del Proyecto**

```
Telecom-X-Parte-2/
│
├── TelecomX_LATAM_parte_2.ipynb   # Notebook principal
├── data
│   ├──datos_tratados.csv          # Dataset limpio y procesado
├── README.md                      # Documentación del proyecto
│
└── visualizaciones                # Carpeta con gráficos exportados
```

---

🧹 **Preparación de los Datos**
1️⃣ Clasificación de Variables

Las variables fueron clasificadas en:

**Variables categóricas:**

- Tipo_Contrato

- Tipo_Internet

- Factura_Digital

- Soporte_Tecnico

- Seguridad_Online

- Genero

- Tiene_Pareja

- Tiene_Dependientes

- etc.

**Variables numéricas:**

- Antiguedad_Meses

- Cargos_Mensuales

- Cargos_Totales

- Cargos_Diarios

- Cantidad_Servicios

---

2️⃣ **Codificación y Normalización**

Se aplicó **One-Hot Encoding** a las variables categóricas.

- Se utilizó escalado (StandardScaler) para modelos sensibles a la escala como:
  ![Comparación de Distribución Antes y Después del Escalado](visualizaciones/comparacion_escalado.png)

  Regresión Logística

- Random Forest no requirió escalado.

---

3️⃣ **División de Datos**

El dataset fue dividido en:

- Conjunto de entrenamiento

- Conjunto de prueba

Esto permitió evaluar la capacidad de generalización de los modelos y evitar sobreajuste.

Además, se aplicaron técnicas de balanceo en el conjunto de entrenamiento para manejar el desbalance de clases.

---

🤖 **Modelos Implementados**

Se entrenaron los siguientes modelos:

- Regresión Logística

- Random Forest

El modelo con mejor desempeño en términos de recall para la clase churn fue Random Forest ajustado, lo que lo convierte en el modelo más adecuado para detectar clientes en riesgo.

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
