<img width="1280" height="640" alt="WhatsApp Image 2026-11-17 at 3 00 46 PM (8)" src="https://github.com/user-attachments/assets/02e7bbac-cf6f-4957-99c8-b8f4171a0f8d" />

# 🤖 Ι Proyecto Iota | Recomendación de Planes de Megaline (Machine Learning)

## 📋 Descripción
**Megaline** busca migrar a sus clientes desde planes heredados hacia sus nuevas tarifas comerciales: **Smart** y **Ultra**. Para facilitar este proceso, la compañía necesita un modelo predictivo capaz de analizar el comportamiento mensual de los usuarios y recomendar automáticamente el plan más adecuado.

En este proyecto se desarrollaron modelos de clasificación supervisada utilizando información histórica de clientes que ya utilizan los nuevos planes. El objetivo fue construir un modelo con la mayor exactitud posible para predecir qué tarifa se adapta mejor a cada usuario en función de sus patrones de consumo.

## 🎯 Objetivos
- ✅ Explorar y comprender el conjunto de datos disponible.
- ✅ Preparar los datos para el entrenamiento de algoritmos de clasificación.
- ✅ Dividir la información en conjuntos de entrenamiento, validación y prueba (estratificación).
- ✅ Entrenar diferentes algoritmos de Machine Learning (Árbol de Decisión y Random Forest).
- ✅ Ajustar hiperparámetros para optimizar el rendimiento de los modelos.
- ✅ Comparar el desempeño entre distintas arquitecturas y seleccionar la de mayor exactitud.
- ✅ Verificar que el modelo seleccionado supere el umbral mínimo de exactitud establecido por Megaline ($\text{Accuracy} > 75\%$).
- ✅ Realizar una prueba de cordura (*sanity check*) para validar la utilidad real de los resultados.

## 🛠️ Herramientas y Habilidades Utilizadas
* **Lenguaje:** Python
* **Librerías:** Pandas, NumPy, Scikit-Learn y Matplotlib
* **Entorno:** Jupyter Notebook
* **Técnicas:** Clasificación supervisada, Ajuste de hiperparámetros, Validación cruzada/estratificada, Modelos ensamblados (Random Forest) y Pruebas de cordura (*Dummy Classifier*).

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
1. **Exploración inicial:** Revisión de la estructura, tipos de datos, valores ausentes y duplicados (confirmando alta calidad inicial sin requerir limpieza compleja).
2. **Preparación del problema:** Creación de la variable categórica `Name_plan` para representar las clases (*Smart* y *Ultra*) y definición de características (*features*) y objetivo (*target*).
3. **División estratificada:** Partición de los datos conservando la proporción original de clases: **60% Entrenamiento, 20% Validación y 20% Prueba**.
4. **Entrenamiento y optimización:**
   * **Árbol de decisión:** Evaluación de hiperparámetros (`max_depth = 8`, logrando `79.63%` de exactitud).
   * **Bosque aleatorio (Random Forest):** Evaluación de combinaciones de árboles y profundidad (`n_estimators = 76`, `max_depth = 12`, alcanzando `81.34%`).
5. **Evaluación final:** Prueba del modelo óptimo sobre el conjunto de prueba independiente y ejecución de prueba de cordura mediante un `DummyClassifier`.

## 💡 Principales Hallazgos y Modelos Evaluados
* **Árbol de Decisión:** Destacó por su fácil interpretación y rápido entrenamiento, alcanzando un desempeño sólido pero con menor capacidad de generalización.
* **Bosque Aleatorio (*Random Forest*):** Obtuvo el mejor rendimiento global, ofreciendo mayor estabilidad, robustez frente a variaciones y una exactitud superior.
* **Prueba de Cordura:** El modelo seleccionado superó ampliamente al clasificador base por frecuencia (`69.36%`), confirmando que aprendió patrones reales del comportamiento del usuario en lugar de aprovechar sesgos de distribución.

## 📈 Resultados Clave
| Modelo / Evaluación | Exactitud (Accuracy) |
| :--- | :--- |
| **Árbol de Decisión** (Optimizado) | 79.63% |
| **Bosque Aleatorio** (Validación) | 81.34% |
| **Bosque Aleatorio** (Conjunto de Prueba) | **81.80%** |
| **Clasificador Ficticio** (Prueba de Cordura) | 69.36% |

*El resultado final en prueba (**81.80%**) supera con holgura el umbral mínimo exigido por la compañía ($\text{Accuracy} > 75\%$).*

## 📈 Visualizaciones Desarrolladas
* Distribución de clases en el dataset original y en los subconjuntos de entrenamiento, validación y prueba.
* Evolución de la exactitud del árbol de decisión según los distintos niveles de profundidad.
* Gráficos comparativos de rendimiento entre los algoritmos evaluados.

## 📂 Archivos Principales
* `iota_megaline_plan_recommendation.ipynb` (o `Ι_Proyecto_Iota___Recomendación_de_Planes_de_Megaline.ipynb`)
* `users_behavior.csv`

## 🏁 Conclusión
El proyecto permitió desarrollar con éxito un modelo de Machine Learning capaz de automatizar la recomendación de los nuevos planes comerciales de Megaline (*Smart* y *Ultra*) a partir del consumo mensual de los usuarios. El modelo **Random Forest** demostró un rendimiento sobresaliente cercano al **82% de exactitud**, superando ampliamente las expectativas de negocio y la prueba de cordura. Estos hallazgos proporcionan a Megaline una herramienta analítica sólida para impulsar su estrategia comercial, facilitar la migración de clientes y optimizar la personalización de sus ofertas.
