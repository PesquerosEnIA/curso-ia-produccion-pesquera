# Clase 10 — Cierre, Conclusiones y Hoja de Ruta
## 🔴 Nivel AVANZADO

> **Para perfiles técnicos y líderes de proyecto.** Cierre orientado a **llevar un modelo a
> producción**, sostenerlo y liderar la transformación. Asume el recorrido técnico del curso.
> *(Existen variantes 🟢 Novato y 🟡 Intermedio.)*

**Curso:** IA Aplicada a la Producción Pesquera · UTN FRCh · PesquerosEnIA
**Docentes:** Soraya Corvalán · Ariel Giamportone · **Duración:** 2 horas

---

## 1. Del notebook a producción: el 90% que falta

Un modelo que funciona en un notebook está lejos de generar valor. El trabajo real:

| Etapa | Qué implica | Riesgo si se omite |
|-------|-------------|--------------------|
| Datos | Pipeline reproducible, versionado de datos | Resultados no replicables |
| Validación | **Temporal**, no aleatoria; calibración | Métricas infladas, sorpresas en prod |
| Despliegue | API/servicio, batch vs. tiempo real | El modelo "vive" solo en la laptop |
| Monitoreo | *Data/concept drift*, alertas | Degradación silenciosa |
| Reentrenamiento | Cadencia y gatillos definidos | Modelo obsoleto (El Niño, cambios de flota) |
| Gobernanza | Dueño, documentación, trazabilidad | Nadie mantiene el sistema |

> El océano **no es estacionario**: un modelo de zonas de pesca se degrada con el tiempo.
> Sin monitoreo y reentrenamiento, todo modelo pesquero caduca.

---

## 2. MLOps mínimo viable para el sector

No hace falta una plataforma cara. Un stack sobrio y suficiente:
- **Reproducibilidad:** notebooks + entorno fijado (requirements/conda), semillas, datos versionados.
- **Validación honesta:** `TimeSeriesSplit`, curvas de calibración, *backtesting* por temporada.
- **Servicio:** un endpoint simple (FastAPI) o *batch* diario que escribe a la base de decisiones.
- **Monitoreo:** *drift* de features (distribuciones), performance sobre datos etiquetados que van llegando.
- **Gatillo de reentrenamiento:** por calendario (temporada) y por umbral (caída de métrica).

---

## 3. Integración de todo el curso en un sistema

Los bloques del curso encajan como piezas de un mismo sistema operativo de decisión:

```
Clase 4 (datos/features) → Clase 6 (predicción de zona/abundancia)
        ↘                         ↘
     Clase 9 (dashboards)   Clase 8 (optimización + agente autónomo)
        ↘                         ↘
                Clase 10: gobierno, ética y mejora continua
```

Un caso integrador realista: features ambientales (C4) → modelo de zona+abundancia (C6) →
agente que combina predicción con optimización de ruta/velocidad (C8) → tablero para gerencia
y regulador (C9), todo bajo validación temporal y monitoreo (C10).

---

## 4. Ética y sesgos, en profundidad

- **Sesgo de esfuerzo:** entrenar con partes de pesca replica el comportamiento pasado de la
  flota, no la biología. Mitigar con datos independientes (campañas INIDEP) y variables biológicas.
- **Optimización con restricciones duras:** cuotas, vedas y tallas mínimas como *constraints*
  del modelo/agente, no como sugerencias. La eficiencia opera **dentro** del marco sostenible.
- **Externalidades:** un modelo que reduce costo por marea no debe traducirse en más esfuerzo
  total; medir impacto sobre el stock, no solo sobre la rentabilidad.
- **Privacidad y datos de flota:** anonimización, uso leal, transparencia con la tripulación.
- **Explicabilidad:** para adopción y regulación, preferir modelos interpretables o añadir
  explicaciones (importancia de variables, SHAP) cuando la decisión afecta a personas/recurso.

---

## 5. Hoja de ruta para perfiles técnicos

- **Ahora:** validación temporal + calibración en tus modelos; versionar datos y código.
- **3–6 meses:** un modelo en servicio (aunque sea batch) con monitoreo de drift; ingesta real
  (Copernicus/GFW) con el patrón fuente-real→fallback (Clase 4).
- **6–12 meses:** política de decisión por costo esperado en el agente (Clase 8); *backtesting*
  por temporada; documentación y handover.
- **Continuo:** contribuir a PesquerosEnIA (issues, PRs, casos), publicar resultados reproducibles.

---

## 6. Proyecto integrador (exigencia avanzada)

Además de la consigna general, para este nivel se valora:
- Un **pipeline reproducible** (datos → features → modelo → evaluación).
- **Validación temporal** y discusión de degradación.
- Un **plan de despliegue y monitoreo** (aunque el modelo sea simple).
- El tratamiento explícito de **restricciones de sostenibilidad**.

---

## Recursos avanzados

- FAO (2024). *Digital Technologies and Innovation in Fisheries and Aquaculture*.
- Kroodsma, D. A., et al. (2018). *Science*, 359(6378), 904–908.
- Paquetes R (Dr. J. D. González): `RMBC`, `ktaucenters` (clustering robusto, CRAN).
- Buenas prácticas MLOps (referencia general adaptable al sector).
- PesquerosEnIA — github.com/PesquerosEnIA · ML_DL_FisheriesEngineers
