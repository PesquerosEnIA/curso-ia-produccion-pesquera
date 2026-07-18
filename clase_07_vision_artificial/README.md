# Clase 7 — Visión Artificial en Plantas Pesqueras

**Responsables:** Damian Giacone (principal) + Soraya
**Duración:** 2 horas
**Notebook de apoyo:** Ariel Giamportone

---

## Objetivo

Que los participantes comprendan qué es la visión artificial y cómo se aplica al control de calidad y la clasificación de producto en plantas de procesamiento pesquero, sin necesidad de infraestructura GPU.

> **Nota de coordinación:** Damian cubre los fundamentos de visión artificial y redes neuronales. El notebook de apoyo (Ariel) aporta un caso aplicado al dominio pesquero con features simuladas, ejecutable en cualquier equipo.

---

## Contenido del notebook

- Características de imagen para clasificar especies y evaluar calidad (color, textura, morfología)
- Dataset simulado de 2.000 piezas con análisis exploratorio visual
- Clasificador de calidad de producto y evaluación de desempeño
- Arquitectura de una red neuronal convolucional (CNN), explicada sin GPU
- Simulación de throughput industrial y predicción en tiempo real ("en producción")
- Reflexión: aplicaciones adicionales y qué necesita una planta para implementarlo

---

## Estructura de carpetas

```
clase_07_vision_artificial/
├── notebooks/   → clase07_vision_artificial_plantas.ipynb
└── (slides / guía → a coordinar con Damian)
```

---

## Notebook principal

**`clase07_vision_artificial_plantas.ipynb`**
- Extracción de features de imagen aplicadas a merluza hubbsi
- Clasificador de calidad con métricas de evaluación
- Explicación conceptual de CNN y del pipeline de inferencia
- Simulación de línea industrial (200-400 piezas/minuto)
- Contexto real: proveedores operando en Argentina (Marel, Baader, TriVision)

---

## Recursos a reutilizar

- [`ML_DL_FisheriesEngineers`](https://github.com/PesquerosEnIA/ML_DL_FisheriesEngineers) — base educativa ML/DL para ingenieros pesqueros

---

## Estado

- [x] Notebook: `clase07_vision_artificial_plantas.ipynb`
- [ ] Slides / guía (coordinar con Damian)
- [ ] Revisión con Damian
