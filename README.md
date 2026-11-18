<img width="1280" height="640" alt="WhatsApp Image 2026-11-17 at 3 00 46 PM (8)" src="https://github.com/user-attachments/assets/02e7bbac-cf6f-4957-99c8-b8f4171a0f8d" />

# 🤖 Ι Proyecto Iota | Recomendación de Planes de Megaline (Machine Learning)

## 📋 Descripción
**Megaline** busca migrar a sus clientes desde planes heredados hacia sus nuevas tarifas comerciales: **Smart** y **Ultra**. Para facilitar este proceso, la compañía necesita un modelo predictivo capaz de analizar el comportamiento mensual de los usuarios y recomendar automáticamente el plan más adecuado.

En este proyecto se desarrollaron modelos de clasificación supervisada utilizando información histórica de clientes que ya utilizan los nuevos planes. El objetivo fue construir un modelo con la mayor exactitud posible para predecir qué tarifa se adapta mejor a cada usuario en función de sus patrones de consumo.

## 🎯 Objetivos
- ✅ Explorar y comprender el conjunto de datos disponible.
- ✅ Preparar los datos para el entrenamiento de algoritmos de clasificación.
- ✅ Dividir la información en conjuntos de entrenamiento, validación y prueba.
- ✅ Entrenar diferentes algoritmos de Machine Learning (Árbol de Decisión y Random Forest).
- ✅ Ajustar hiperparámetros (`n_estimators` y `max_depth`) para optimizar el rendimiento.
- ✅ Comparar el desempeño entre distintas arquitecturas y seleccionar la de mayor exactitud.
- ✅ Verificar que el modelo supere el umbral mínimo de exactitud establecido por Megaline ($\text{Accuracy} > 75\%$).
- ✅ Realizar una prueba de cordura (*sanity check*) para validar la utilidad real de los resultados.

## 🛠️ Herramientas y Habilidades Utilizadas
* **Lenguaje:** Python
* **Librerías:** Pandas, NumPy, [Scikit-Learn](https://github.com/NICOLAS-8110) y Matplotlib
* **Entorno:** [Jupyter Notebook](https://github.com/santidata7/Iota-megaline-plan-recommendation/blob/main/%CE%99_Proyecto_Iota___Recomendaci%C3%B3n_de_Planes_de_Megaline.ipynb)
* **Técnicas:** Clasificación supervisada, Optimización de hiperparámetros, Modelos ensamblados (Random Forest) y Pruebas de cordura (*Dummy Classifier*).

## 📊 Fuente de Datos
El proyecto utiliza un dataset histórico con el comportamiento mensual de los clientes de Megaline:
* **Archivo utilizado:** `users_behavior.csv`
* **Variables disponibles:**
  * `calls`: Número de llamadas realizadas.
  * `minutes`: Duración total de llamadas en minutos.
  * `messages`: Cantidad de mensajes enviados.
  * `mb_used`: Tráfico de internet utilizado en MB.
  * `is_ultra`: Variable objetivo (`1 = Ultra`, `0 = Smart`).

## ⚙️ Metodología
1. **Exploración inicial:** Revisión de la estructura, tipos de datos, valores ausentes y duplicados (confirmando alta calidad inicial).
2. **Preparación y partición:** División del dataset en conjuntos de entrenamiento, validación y prueba para evaluar adecuadamente el modelo.
3. **Optimización de hiperparámetros:** Barrido iterativo probando diferentes combinaciones de número de árboles (`n_estimators`) y profundidad máxima (`max_depth`) usando `RandomForestClassifier`.
4. **Evaluación final y prueba de cordura:** Validación del rendimiento con datos independientes y comparación contra la clase mayoritaria (~69.7%) para asegurar que el modelo aprende patrones reales.

## 💡 Principales Hallazgos y Modelos Evaluados
* **Bosque Aleatorio (*Random Forest*):** Demostró ser el algoritmo con mejor desempeño general frente a alternativas como Árboles de Decisión o Regresión Logística.
* **Optimización:** La mejor configuración encontrada en validación fue con `n_estimators = 10` y `max_depth = 10`.
* **Prueba de Cordura:** El modelo superó con claridad el límite de la clase mayoritaria, confirmando su capacidad predictiva útil para el negocio.

## 📈 Resultados Clave
| Modelo / Evaluación | Exactitud (Accuracy) |
| :--- | :--- |
| **Bosque Aleatorio** (Conjunto de Validación) | **81.49%** |
| **Bosque Aleatorio** (Conjunto de Prueba) | **81.18%** |
| **Línea Base / Clase Mayoritaria** (Prueba de Cordura) | **69.70%** |

*El resultado obtenido (**81.18%** en test) supera con holgura el umbral mínimo exigido por la compañía ($\text{Accuracy} > 75\%$).*

## 📈 Visualizaciones Desarrolladas
* Distribución y estadísticas descriptivas de las variables de consumo.
* Gráficos de evolución de exactitud según la variación de hiperparámetros en el modelo de bosque aleatorio.

## 📂 Archivos Principales
* `iota_megaline_plan_recommendation.ipynb` (o [Ι_Proyecto_Iota___Recomendación_de_Planes_de_Megaline.ipynb](https://github.com/santidata7/Iota-megaline-plan-recommendation/blob/main/%CE%99_Proyecto_Iota___Recomendaci%C3%B3n_de_Planes_de_Megaline.ipynb))
* `users_behavior.csv`

## 🏁 Conclusión
El proyecto permitió desarrollar con éxito un modelo de Machine Learning capaz de automatizar la recomendación de los nuevos planes comerciales de Megaline (*Smart* y *Ultra*) a partir del consumo mensual de los usuarios. El modelo **Random Forest** demostró un rendimiento sólido superando el **81% de exactitud**, cumpliendo holgura con los requisitos del negocio y pasando exitosamente la prueba de cordura. Estos hallazgos proporcionan a Megaline una herramienta analítica confiable para facilitar la migración de clientes y optimizar sus estrategias comerciales.
