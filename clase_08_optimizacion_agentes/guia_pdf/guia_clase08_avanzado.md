# Clase 8 — Optimización de Operaciones y Agentes de IA
## 🔴 Nivel AVANZADO

> **Para participantes con manejo de Python y nociones de ML.** Detalle técnico: modelo de consumo, optimización
> numérica de velocidad, clustering con selección de k, mantenimiento predictivo y arquitectura de un agente
> reglas+ML. Se acompaña del notebook `clase08_optimizacion_avanzado.ipynb`.
> *(Existen variantes 🟢 Novato y 🟡 Intermedio de esta misma clase.)*

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN Facultad Regional Chubut | PesquerosEnIA
**Docentes:** Damián Giacone · Ariel Giamportone
**Duración:** 2 horas · **Modalidad:** Semipresencial / Virtual

---

## Objetivos

1. Ajustar un **regresor de consumo** e interpretar su importancia de variables.
2. Formular y resolver la **optimización de velocidad** como minimización de una función de costo.
3. Aplicar **K-Means** con estandarización y elegir *k* con criterios objetivos (silhouette / codo).
4. Plantear el **mantenimiento predictivo** como clasificación o detección de anomalías.
5. Diseñar un **agente reglas + ML** con el ciclo percibir–razonar–actuar.

---

## 1. Modelo de consumo

```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_absolute_error, r2_score

feats = ["distancia_puerto_km","dias_en_mar","velocidad_media_kn","viento_medio_kn",
         "estado_mar","horas_arrastre","profundidad_pesca_m","antiguedad_motor_anos"]
Xtr,Xte,ytr,yte = train_test_split(df[feats], df["consumo_tn"], test_size=0.2, random_state=42)
rf = RandomForestRegressor(n_estimators=100, random_state=42).fit(Xtr,ytr)
print("MAE:", mean_absolute_error(yte, rf.predict(Xte)), "| R2:", r2_score(yte, rf.predict(Xte)))
```

Analizar `rf.feature_importances_` (o permutation importance) para separar factores accionables (velocidad, arrastre) de los estructurales (antigüedad del motor).

## 2. Optimización de velocidad

Costo total como función de la velocidad `v` (ley de Admiralty simplificada):

```python
import numpy as np
K, D, precio, c_hora, KMH = 0.003, 300, 850, 1400, 1.852   # k, dist(km), USD/tn, USD/h, kn→km/h
def costo(v):
    t = D/(v*KMH)                     # horas de navegación
    consumo = K * v**3 * t            # toneladas
    return consumo*precio + t*c_hora
V = np.arange(5.5, 13.5, 0.05)
v_opt = V[np.argmin([costo(v) for v in V])]
```

La función es convexa en el rango operativo: el óptimo se obtiene por barrido o con `scipy.optimize.minimize_scalar`. La **sensibilidad al precio del gasoil** desplaza `v_opt` (a mayor precio, menor velocidad óptima).

## 3. Clustering de zonas

```python
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
from sklearn.metrics import silhouette_score

Xz = StandardScaler().fit_transform(zonas[["captura_tn","consumo_tn","cpue"]])
for k in range(2,6):
    lab = KMeans(n_clusters=k, n_init=10, random_state=42).fit_predict(Xz)
    print(k, silhouette_score(Xz, lab))
```

**Estandarizar siempre** antes de K-Means (es sensible a la escala). Elegir *k* con silhouette/codo y **validar la interpretación** (alta/media/baja eficiencia) con conocimiento del dominio.

## 4. Mantenimiento predictivo

Dos encuadres según los datos disponibles:
- **Clasificación supervisada** si hay histórico etiquetado de fallas (features de telemetría → probabilidad de falla en ventana futura). Cuidar el **desbalance** (fallas raras): métricas PR-AUC, recall.
- **Detección de anomalías** si no hay etiquetas (`IsolationForest`, autoencoders): se marca lo que se aparta del comportamiento normal.
Clave: **ventana de anticipación** útil (avisar con tiempo de intervenir en puerto) y control de falsos positivos (no parar un motor sano).

## 5. Agente reglas + ML

Arquitectura **percibir → razonar → actuar** en ciclo:
- **Percibir:** ingesta de telemetría, consumo y posición por buque.
- **Razonar:** los modelos (consumo, velocidad óptima, riesgo de falla) actúan como *herramientas*; una capa de **reglas** aplica prioridades (seguridad del motor > ahorro).
- **Actuar:** emite recomendaciones (seguir / bajar velocidad / volver a puerto) y ordena la flota por prioridad.
No es un LLM conversacional: es un sistema determinista+ML, auditable, con el humano en el lazo de decisión.

---

## Desafío integrador

Entrená el regresor de consumo y reportá MAE/R² e importancias. Resolvé `v_opt` para tres escenarios de precio de gasoil y graficá la curva de costo. Agrupá las zonas con K-Means (k elegido por silhouette) y asigná prioridad. Finalmente, escribí la lógica de un agente que, dado el estado de N buques, devuelva por cada uno una acción priorizada, justificando la regla de prioridad seguridad>ahorro.

## Referencias técnicas

- scikit-learn: `RandomForestRegressor`, `KMeans`, `IsolationForest`, `silhouette_score`.
- `scipy.optimize` para la minimización del costo.
- FAO — consumo energético en la pesca; literatura de *predictive maintenance*.
- Repo del curso: https://github.com/PesquerosEnIA/curso-ia-produccion-pesquera
