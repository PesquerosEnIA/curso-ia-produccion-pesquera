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
├── notebooks/   → clase07_vision_artificial_plantas.ipynb + clase07_cnn_en_vivo_opencv.ipynb
└── slides/      → presentacion_clase07.html (caso aplicado, Ariel) + versión offline
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

## Notebook: una CNN en vivo sobre un video real

**`clase07_cnn_en_vivo_opencv.ipynb`** — [abrir en Colab](https://colab.research.google.com/github/PesquerosEnIA/curso-ia-produccion-pesquera/blob/master/clase_07_vision_artificial/notebooks/clase07_cnn_en_vivo_opencv.ipynb) (activar GPU T4)
- Video real de la sala de clasificación del N/O *Thalassa* (Ifremer, CC BY 4.0, Wikimedia Commons)
- Convolución a mano con OpenCV (desenfoque, bordes, realce) y qué ve ResNet18 capa por capa
- Un detector general (YOLO11, COCO) no reconoce peces: el punto de partida honesto
- Transfer learning con fotos abiertas de peces (*fish market*, Roboflow 100, CC BY 4.0)
- Detección cuadro por cuadro sobre el video, umbral de confianza y lo que el modelo todavía no sabe

---

## Caso aplicado: «La cámara en la línea» (Ariel Giamportone)

- **Presentación:** [`slides/presentacion_clase07.html`](https://pesquerosenia.github.io/curso-ia-produccion-pesquera/clase_07_vision_artificial/slides/presentacion_clase07.html) (versión [offline](https://pesquerosenia.github.io/curso-ia-produccion-pesquera/clase_07_vision_artificial/slides/presentacion_clase07_offline.html)): inspección actual con mesa de luz, qué ya puede ver una cámara en la industria, el circuito en la línea, los dos errores, la zona de duda con una persona en la mesa, la deriva de datos y seis preguntas para empezar.
- **Simuladores:** [La cámara en la línea](https://pesquerosenia.github.io/curso-ia-produccion-pesquera/interactivos/c7_camara_linea.html) (umbral, zona de duda, cambio de luz) y [El ojo y la IA](https://pesquerosenia.github.io/curso-ia-produccion-pesquera/interactivos/planta_inspector.html) (matriz de confusión). Datos didácticos.

---

## Recursos a reutilizar

- [`ML_DL_FisheriesEngineers`](https://github.com/PesquerosEnIA/ML_DL_FisheriesEngineers) — base educativa ML/DL para ingenieros pesqueros

---

## Estado

- [x] Notebook: `clase07_vision_artificial_plantas.ipynb`
- [x] Notebook: `clase07_cnn_en_vivo_opencv.ipynb` (CNN en vivo sobre video real)
- [x] Presentación del caso aplicado (Ariel) + simulador «La cámara en la línea»
- [ ] Slides / guía de fundamentos (Damian)
- [ ] Revisión con Damian
