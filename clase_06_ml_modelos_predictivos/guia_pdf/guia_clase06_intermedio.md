# Clase 6 — Machine Learning y Modelos Predictivos en Pesca
## 🟡 Nivel INTERMEDIO

> **Para participantes con base básica de Python** que leen y modifican código. Esta guía desarrolla
> el marco conceptual completo del aprendizaje automático supervisado aplicado a la predicción de zonas
> de pesca, y se acompaña del notebook `clase06_ml_intermedio.ipynb` con ejercicios prácticos.
> *(Existen variantes 🟢 Novato y 🔴 Avanzado de esta misma clase.)*

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN Facultad Regional Chubut | PesquerosEnIA
**Docentes:** Damián Giacone · Ariel Giamportone
**Duración:** 2 horas
**Modalidad:** Semipresencial / Virtual

---

## Objetivos de la clase

1. Comprender qué es el Machine Learning supervisado y en qué se diferencia de la programación clásica.
2. Plantear un problema real del sector como una tarea de **clasificación** (¿conviene ir a esta zona?) y de **regresión** (¿cuántos kg esperar?).
3. Entrenar y **comparar** modelos (Regresión Logística, Random Forest, Gradient Boosting) con validación cruzada.
4. Evaluar con honestidad: matriz de confusión, curva ROC y AUC; entender el **sobreajuste**.
5. Interpretar los errores en términos económicos y elegir el **umbral de decisión**.
6. Leer la **importancia de las variables** y usarla como conocimiento del recurso.
7. Reconocer las limitaciones y el **uso ético** del modelo.

---

## 1. Del dato a la predicción: el ML supervisado

En la Clase 4 vimos de dónde salen los datos. Ahora los ponemos a trabajar. El **aprendizaje supervisado** parte de ejemplos históricos donde conocemos tanto las **variables de entrada** (predictores) como el **resultado** (la variable objetivo). El algoritmo ajusta un modelo que aprende la relación entre unos y otro, para luego **predecir el resultado en casos nuevos**.

- **Programación clásica:** persona → escribe reglas → la máquina las aplica.
- **Machine Learning:** persona → aporta ejemplos (datos + resultado) → la máquina **infiere las reglas**.

El corazón del ML es **generalizar**, no memorizar: que funcione con datos que el modelo nunca vio.

---

## 2. El problema: predecir zonas de pesca exitosas

Un capitán de arrastrero debe decidir a qué zona dirigirse. Tiene pronósticos de variables oceanográficas, historial de capturas y su experiencia. **¿Puede un modelo ayudarlo?**

- **Variable objetivo** `captura_exitosa`: `1` si la marea supera un umbral de captura definido por la empresa, `0` si no.
- **Predictores (features):** temperatura superficial (SST), clorofila-a, profundidad media, salinidad, velocidad de corriente, mes, latitud y longitud.

Con ~1.000 mareas históricas construimos el dataset. La relación no es trivial: la captura es mayor cuando la SST ronda los 8–12 °C, la clorofila es alta y la profundidad es intermedia (~140 m) — el hábitat de la merluza.

---

## 3. Preparar los datos

Antes de entrenar:

1. **Separar** predictores (`X`) de la variable objetivo (`y`).
2. **Dividir** en entrenamiento y prueba (`train_test_split`, típicamente 80/20), con `stratify=y` para conservar la proporción de clases.
3. **Escalar** las features (`StandardScaler`) — importante para modelos lineales como la Regresión Logística; los árboles no lo necesitan, pero no molesta.

> **Regla de oro:** el conjunto de prueba **no se toca** durante el entrenamiento. Es la única forma honesta de estimar cómo se comportará el modelo con mareas futuras.

---

## 4. Entrenar y comparar modelos

No hay un modelo "mejor" universal: se prueban varios y se comparan. En esta clase usamos tres, de complejidad creciente:

| Modelo | Idea | Fuerte en |
|--------|------|-----------|
| **Regresión Logística** | Frontera lineal | Interpretabilidad, baseline |
| **Random Forest** | Ensamble de árboles | Robustez, importancia de variables |
| **Gradient Boosting** | Árboles secuenciales | Suele dar la mayor precisión |

Para compararlos con justicia usamos **validación cruzada (5-fold)**: se parte el entrenamiento en 5, se entrena con 4 y se evalúa con 1, rotando. La métrica es el **AUC-ROC** (ver §6). Así obtenemos un promedio ± desvío, más confiable que una sola partición.

---

## 5. El enemigo: el sobreajuste (overfitting)

Un modelo **sobreajustado** memoriza el ruido del entrenamiento en lugar de aprender el patrón: rinde perfecto con los datos que ya vio y **falla con datos nuevos**. Señales:

- Error de entrenamiento muy bajo y error de prueba mucho más alto.
- Modelos demasiado complejos para la cantidad de datos disponibles.

Se combate con: más datos, modelos más simples, regularización y —sobre todo— **evaluar siempre en test y con validación cruzada**. En el aula hay un **simulador de sobreajuste** donde se ve subir el error de test mientras el de entrenamiento sigue bajando.

---

## 6. Evaluar bien: matriz de confusión y curva ROC

La **exactitud** (aciertos totales) engaña cuando las clases están desbalanceadas. Herramientas mejores:

- **Matriz de confusión:** cruza lo predicho con lo real. Sus cuatro celdas son verdaderos positivos, verdaderos negativos, **falsos positivos** y **falsos negativos**.
- **Curva ROC y AUC:** la ROC muestra el compromiso entre detectar bien las mareas buenas (sensibilidad) y no dar falsas alarmas. El **AUC** resume la curva en un número: 1,0 es perfecto; 0,5 es tirar la moneda. Es la métrica que usamos para comparar modelos.

---

## 7. Los dos errores, traducidos a plata — y el umbral

El modelo devuelve una **probabilidad**; el **umbral** decide desde qué probabilidad se actúa. Mover el umbral cambia el balance de errores:

- **Falso positivo:** predijo "exitosa", se fue y no lo era → **gasoil y tiempo perdidos**.
- **Falso negativo:** predijo "no exitosa", no se fue y sí lo era → **oportunidad perdida**.

Bajar el umbral reduce falsos negativos pero aumenta falsos positivos, y viceversa. **No hay un umbral óptimo universal:** depende del costo relativo de cada error para *esa* empresa. Elegir el umbral es, por lo tanto, **una decisión de negocio**, no puramente técnica.

---

## 8. Importancia de variables: qué manda

El Random Forest puede medir cuánto aportó cada variable a clasificar bien. Esto no solo mejora el modelo: es **conocimiento del recurso**. En nuestro caso, la **SST** y la **clorofila-a** suelen dominar, seguidas de la **profundidad** — coherente con la ecología de la merluza. Si una variable clave está fuera de rango, ninguna zona es buena.

---

## 9. De clasificación a regresión: ¿cuántos kg?

La clasificación responde *¿conviene ir?* (sí/no). Pero el programa también pide **estimar la abundancia**: *¿cuántos kg esperar?* Esa es una tarea de **regresión**.

Reutilizamos las mismas features y entrenamos un **Random Forest Regressor** sobre una variable continua `captura_kg`. Se evalúa con métricas de regresión:

- **MAE** (error absoluto medio): en kg, fácil de interpretar.
- **RMSE** (error cuadrático medio): penaliza más los errores grandes.
- **R²**: proporción de la varianza explicada (1,0 = perfecto).

Combinando ambos modelos, al capitán le damos dos números por zona: **probabilidad de éxito** *y* **kilos estimados**.

---

## 10. Límites y uso ético

- **El modelo aprende del pasado.** Ante cambios oceanográficos (El Niño, cambio climático) puede desactualizarse. Requiere **reentrenamiento** y monitoreo.
- **Variables ausentes:** estado del arte de la flota, datos biológicos del INIDEP, precios, cuotas — el modelo no las ve.
- **Validación temporal:** entrenar con el pasado y evaluar con el futuro; no mezclar temporalmente.
- **Sostenibilidad:** si el modelo hace más eficiente cada viaje, **no debe usarse para aumentar el número de viajes más allá de las cuotas**. El objetivo es optimizar el esfuerzo permitido, no evadir la gestión del recurso.
- **El modelo complementa al capitán, no lo reemplaza:** aporta lo que un humano no puede procesar; el juicio final combina ambos.

---

## Actividad práctica: Notebook `clase06_ml_intermedio.ipynb`

En Google Colab, recorré el flujo completo: EDA, comparación de los tres modelos con validación cruzada, evaluación (ROC y matriz de confusión), importancia de variables, recomendación de zona y estimación de kg.

**Ejercicios 🟡 incluidos en el notebook:**
1. Cambiá `n_estimators` del Random Forest de 100 a 300. ¿Mejora el AUC en test? ¿Justifica el costo?
2. En la recomendación de zonas, subí la clorofila de la Zona B y volvé a correr. ¿Cambia la zona recomendada? ¿Por qué?

---

## Referencias

- FAO — El Estado Mundial de la Pesca y la Acuicultura (SOFIA) 2024.
- scikit-learn — documentación de `RandomForestClassifier`, `roc_auc_score`, `cross_val_score`.
- Kroodsma et al. (2018), *Tracking the global footprint of fisheries*, Science.
- Materiales de la Clase 4 (variables ambientales) y marco de sostenibilidad del INIDEP.

## Ejercicios (nivel intermedio)

1. Reemplazá el Gradient Boosting por un modelo distinto (por ej. `KNeighborsClassifier`) y compará el AUC.
2. Calculá el costo total de una campaña con dos umbrales distintos, asignando un valor en $ al falso positivo y al falso negativo. ¿Cuál conviene según tu costo de gasoil?
3. Analizá cómo cambia la importancia de variables si quitás la clorofila del conjunto de features.

## Para explorar más

- Simuladores del aula: **umbral de decisión**, **¿a qué zona voy?** y **sobreajuste**.
- Repo del curso: https://github.com/PesquerosEnIA/curso-ia-produccion-pesquera
- Próxima clase (8): Optimización de flota y agentes de IA.
