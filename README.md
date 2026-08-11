# 🚀 Tarea 1: Spark MLlib Classification Pipeline

Este repositorio contiene la implementación de un flujo de trabajo (Pipeline) de Machine Learning utilizando **PySpark MLlib** para resolver un problema de clasificación binaria. El proyecto ilustra la importancia de la calidad de los datos y el *Feature Engineering* comparando el rendimiento de varios algoritmos predictivos.

## 📝 Descripción del Proyecto

El objetivo del proyecto es entrenar y evaluar modelos de clasificación capaces de predecir una etiqueta binaria (0 o 1) a partir de tres variables numéricas (`feature_1`, `feature_2`, `feature_3`). Este tipo de enfoque es fundamental para resolver problemas de negocio reales como:
* Detección de Fraude.
* Predicción de Fuga de Clientes (*Churn*).
* Evaluación de Riesgo de Crédito.

## ⚙️ Modelos Entrenados

Se construyeron Pipelines automatizados para los siguientes algoritmos:
1. Regresión Logística (Logistic Regression)
2. Máquina de Vectores de Soporte (Linear SVC)
3. Bosque Aleatorio (Random Forest)
4. Árbol de Decisión (Decision Tree)

## 📊 Resultados y Análisis

El experimento se dividió en dos fases para demostrar el principio *"Garbage In, Garbage Out"* (si entras ruido, sale ruido):

1. **Dataset Original:** Datos generados de forma 100% aleatoria sin correlación lógica. Los modelos apenas superaron el 70% de precisión (sesgados por la clase mayoritaria).
2. **Dataset Mejorado:** Datos generados con una regla matemática subyacente y un 10% de ruido aleatorio para simular la imprevisibilidad del mundo real. 

### Cuadro Comparativo de Rendimiento (Accuracy)

| Modelo | DS Original | DS Mejorado | Diferencia Absoluta |
| :--- | :--- | :--- | :--- |
| **Regresión Logística** | 0.7046 | 0.8894 | **+ 0.1848** |
| **SVM Lineal** | 0.7046 | 0.8967 | **+ 0.1921** |
| **Random Forest** | 0.7056 | 0.8528 | **+ 0.1472** |
| **Decision Tree** | 0.7004 | 0.8486 | **+ 0.1482** |

**Conclusión Principal:** Los algoritmos aprendieron exitosamente los patrones en el Dataset Mejorado. La Regresión Logística y el SVM Lineal lideraron la prueba al identificar perfectamente la relación lineal de las variables, alcanzando casi el límite teórico máximo (~90%) impuesto por el ruido introducido.

## 🛠️ Tecnologías Utilizadas
* **Lenguaje:** Python 3
* **Framework:** Apache Spark (PySpark MLlib)
* **Librerías Extra:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn (para evaluación visual).
* **Entorno:** Google Colab
