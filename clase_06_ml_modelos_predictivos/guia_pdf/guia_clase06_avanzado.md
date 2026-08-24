# Clase 6 — Machine Learning y Modelos Predictivos en Pesca
## 🔴 Nivel AVANZADO

> **Para participantes con manejo de Python y nociones de estadística/ML.** Esta guía va al detalle
> técnico: pipeline reproducible, comparación rigurosa de modelos, elección de umbral por costo,
> regresión de abundancia y control de sobreajuste/deriva. Se acompaña del notebook
> `clase06_ml_avanzado.ipynb`.
> *(Existen variantes 🟢 Novato y 🟡 Intermedio de esta misma clase.)*

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN Facultad Regional Chubut | PesquerosEnIA
**Docentes:** Damián Giacone · Ariel Giamportone
**Duración:** 2 horas · **Modalidad:** Semipresencial / Virtual

---

## Objetivos

1. Construir un **pipeline** reproducible de clasificación (preprocesamiento + modelo) con `scikit-learn`.
2. Comparar modelos con **validación cruzada estratificada** y métricas robustas (AUC-ROC, PR-AUC).
3. Elegir el **umbral de decisión** minimizando una función de costo del negocio.
4. Ajustar un **regresor** de abundancia y evaluar con MAE/RMSE/R².
5. Diagnosticar y mitigar **sobreajuste** y **data/label leakage**; anticipar **drift** temporal.

---

## 1. Pipeline reproducible

Encapsular preprocesamiento y modelo evita fugas de información y facilita la validación cruzada:

```python
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.model_selection import train_test_split, StratifiedKFold, cross_val_score

X_tr, X_te, y_tr, y_te = train_test_split(X, y, test_size=0.2,
                                          random_state=42, stratify=y)

pipe = Pipeline([
    ("scaler", StandardScaler()),                 # inocuo para árboles, necesario para modelos lineales
    ("clf", GradientBoostingClassifier(random_state=42)),
])
```

> El escalado va **dentro** del pipeline para que se ajuste solo con el fold de entrenamiento en cada iteración de CV (sin leakage).

## 2. Comparación rigurosa de modelos

```python
cv = StratifiedKFold(n_splits=5, shuffle=True, random_state=42)
for nombre, modelo in modelos.items():
    auc = cross_val_score(modelo, X_tr, y_tr, cv=cv, scoring="roc_auc")
    print(f"{nombre:20s} AUC = {auc.mean():.3f} ± {auc.std():.3f}")
```

- Usar **`StratifiedKFold`** con datos desbalanceados.
- Reportar **media ± desvío**; un modelo con AUC ligeramente menor pero más estable puede ser preferible.
- Complementar AUC-ROC con **PR-AUC** (precision-recall) cuando la clase positiva es rara.

## 3. Elección del umbral por costo

El umbral por defecto (0,5) rara vez es óptimo. Se elige barriendo umbrales y minimizando el costo esperado, con los costos reales de cada error:

```python
import numpy as np
proba = pipe.fit(X_tr, y_tr).predict_proba(X_te)[:, 1]
C_FP, C_FN = 350_000, 500_000            # $ por falso positivo / falso negativo
umbrales = np.linspace(0.05, 0.95, 181)
def costo(t):
    pred = (proba >= t).astype(int)
    fp = ((pred == 1) & (y_te == 0)).sum()
    fn = ((pred == 0) & (y_te == 1)).sum()
    return fp * C_FP + fn * C_FN
t_opt = umbrales[np.argmin([costo(t) for t in umbrales])]
```

El **umbral óptimo es una función del negocio** (costo de gasoil vs. oportunidad), no un hiperparámetro del modelo. El simulador de umbral del aula ilustra esta curva de costo.

## 4. Regresión de abundancia

```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

reg = RandomForestRegressor(n_estimators=200, random_state=42).fit(Xr_tr, yr_tr)
pred = reg.predict(Xr_te)
mae  = mean_absolute_error(yr_te, pred)
rmse = mean_squared_error(yr_te, pred, squared=False)
r2   = r2_score(yr_te, pred)
```

Interpretar el MAE en unidades del negocio (kg) y relativizarlo a la captura media. Cuidado con la **heterocedasticidad**: el error suele crecer con la abundancia.

## 5. Sobreajuste, leakage y drift

- **Sobreajuste:** curvas de validación (train vs. CV) al variar complejidad; `learning_curve` para ver si más datos ayudarían.
- **Leakage:** ninguna transformación ajustada con el conjunto completo; nada derivado del futuro (p. ej. capturas posteriores).
- **Validación temporal:** para series de mareas, usar **splits temporales** (`TimeSeriesSplit`), no aleatorios — el pasado predice el futuro, no al revés.
- **Drift:** monitorear en producción la distribución de features y el desempeño; reentrenar ante cambios oceanográficos.
- **Interpretabilidad:** `feature_importances_`, permutation importance y, si se justifica, **SHAP** para explicar predicciones individuales.

---

## Desafío integrador

Entrená y calibrá un clasificador con `StratifiedKFold`, elegí el umbral que minimiza tu función de costo, y reportá: AUC-ROC, PR-AUC, matriz de confusión al umbral óptimo y las 3 variables más importantes. Luego sumá el regresor de abundancia y entregá, para tres zonas candidatas, la tupla **(probabilidad, kg estimados, decisión al umbral)**. Documentá una estrategia de **validación temporal** y de **monitoreo de drift** para llevarlo a producción.

## Referencias técnicas

- scikit-learn: `Pipeline`, `StratifiedKFold`, `cross_val_score`, `RandomForestRegressor`, `permutation_importance`.
- Lundberg & Lee (2017), *A Unified Approach to Interpreting Model Predictions* (SHAP).
- FAO SOFIA 2024; Kroodsma et al. (2018), Science.
- Repo del curso: https://github.com/PesquerosEnIA/curso-ia-produccion-pesquera
