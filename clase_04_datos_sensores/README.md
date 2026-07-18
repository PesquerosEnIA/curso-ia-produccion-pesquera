# Clase 4 — Datos y Sensores del Dominio Pesquero

**Responsables:** Ariel Giamportone + Soraya
**Duración:** 2 horas
**Rol de Ariel:** Principal

---

## Objetivo

Que los participantes identifiquen y comprendan los tipos de datos disponibles en la actividad pesquera y cómo estructurarlos para análisis con IA.

---

## Contenido previsto

- Mapa de fuentes de datos: oceanográficos, satelitales, AIS/VMS, GPS, sensores de captura, registros de planta
- Concepto de **Small Data operativo** en barcos y plantas vs. Big Data
- Variables ambientales clave: temperatura superficial del mar (SST), corrientes, profundidad, clorofila
- Plataformas de datos abiertos: INIDEP, Copernicus, NOAA, Global Fishing Watch
- Ejercicio práctico: exploración de un dataset oceanográfico real

---

## Estructura de carpetas

```
clase_04_datos_sensores/
├── slides/      → Presentación principal
├── guia_pdf/    → Guía teórica para participantes
├── notebooks/   → clase04_datos_novato / _intermedio / _avanzado .ipynb
└── recursos/    → Datasets de ejemplo, esquemas de arquitectura
```

---

## Notebook principal

**Notebooks por nivel:** `clase04_datos_novato` · `clase04_datos_intermedio` · `clase04_datos_avanzado`
- Carga de datos SST desde Copernicus o NOAA (dato abierto)
- Exploración visual de variables ambientales por zona de pesca
- Introducción a registros de captura como tabla estructurada
- Base para los modelos de la Clase 6

---

## Recursos a reutilizar

- [`Hydrodinamic_model_Aquaculture_nets`](https://github.com/arielgiamportone/Hydrodinamic_model_Aquaculture_nets) — variables ambientales reales, modelo hídrodinámico
- [`Trawl_net_model_in_Advanced_Excel`](https://github.com/arielgiamportone/Trawl_net_model_in_Advanced_Excel) — datos operativos de captura canal Beagle
- [`ML_DL_FisheriesEngineers`](https://github.com/PesquerosEnIA/ML_DL_FisheriesEngineers) — datasets pesqueros de ejemplo

---

## Estado

- [ ] Coordinación con Soraya (división de contenido)
- [ ] Slides
- [ ] Guía PDF
- [x] Notebooks por nivel (novato / intermedio / avanzado)
- [ ] Revisión conjunta
