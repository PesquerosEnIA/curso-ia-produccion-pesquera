# Clase 6 — ML y Modelos Predictivos en Pesca

**Responsables:** Damian (principal) + Ariel Giamportone
**Duración:** 2 horas
**Rol de Ariel:** Co-responsable (aporte de casos de dominio y notebooks)

---

## Objetivo

Que los participantes comprendan cómo aplicar modelos de machine learning para predecir zonas de pesca y estimar abundancia de especies usando variables ambientales.

> **Nota de coordinación:** Damian cubre los fundamentos de ML (Clase 5). La contribución de Ariel se centra en los casos de uso aplicados al dominio pesquero y los notebooks prácticos.

---

## Contenido previsto (contribución Ariel)

- Ejemplos de modelos de predicción de zonas de pesca usando SST, clorofila y profundidad
- Análisis de patrones de captura: series temporales y estacionalidad
- Conexión con los datos trabajados en Clase 4
- Evaluación de modelos en contexto pesquero (métricas relevantes para el sector)

---

## Estructura de carpetas

```
clase_06_ml_modelos_predictivos/
├── slides/      → (coordinar con Damian)
├── guia_pdf/    → Guía de casos de uso (aporte Ariel)
├── notebooks/   → clase_06_prediccion_captura_variables_ambientales.ipynb
└── recursos/    → Datasets, papers de referencia
```

---

## Notebook principal

**`clase_06_prediccion_captura_variables_ambientales.ipynb`**
- Carga del dataset preparado en Clase 4
- Modelo de regresión/clasificación para predicción de zona óptima de pesca
- Validación y visualización de resultados en mapa
- Discusión de limitaciones y aplicaciones reales

---

## Recursos a reutilizar

- [`Hydrodinamic_model_Aquaculture_nets`](https://github.com/arielgiamportone/Hydrodinamic_model_Aquaculture_nets) — código base de modelos predictivos
- [`Machine_Learning_for_Sales_and_operations_Planning`](https://github.com/arielgiamportone/Machine_Learning_for_Sales_and_operations_Planning) — patrones ML para planificación operativa
- [`ML_DL_FisheriesEngineers`](https://github.com/PesquerosEnIA/ML_DL_FisheriesEngineers) — notebooks de ML para pesquerías

---

## Estado

- [ ] Coordinación con Damian (alcance de la contribución)
- [ ] Notebook: `clase_06_prediccion_captura_variables_ambientales.ipynb`
- [ ] Guía PDF (casos de dominio)
- [ ] Revisión con Damian
