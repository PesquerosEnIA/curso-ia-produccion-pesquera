# Interactivos del curso — hosting

Mini-apps interactivas (HTML autónomo, sin dependencias) que se **embeben por iframe** en el aula de Moodle.
Cada archivo es 100% autocontenido (HTML+CSS+JS inline): se puede abrir con doble clic para probarlo local.

## Widgets
| Archivo | Clase | Concepto |
|---|---|---|
| `c0_kit_herramientas.html` | Pre-clase | Kit de herramientas (Colab/GitHub/Python/Drive/VS Code) + celda de Colab que "corre" |
| `c0_autodiagnostico.html` | Pre-clase | Autodiagnóstico de 5 preguntas → recomienda nivel (novato/intermedio/avanzado) |
| `c0_pasos_colab.html` | Pre-clase | Tutorial guiado de 6 pasos: abrir y correr un notebook del repo en Colab (con maquetas) |
| `c0_glosario.html` | Pre-clase | Glosario buscable con filtros por tema + analogías pesqueras (27 términos) |
| `c1_barco_fabrica_datos.html` | 1 | Barco interactivo: cada sistema genera datos y la IA los usa (hero de bienvenida) |
| `c1_planta_transicion.html` | 1 | Planta de procesamiento: sin vs. con transición digital → KPIs + valor recuperado |
| `c6_umbral_decision.html` | 6 | El umbral de decisión como decisión económica (matriz de confusión + costo en $) |
| `c6_zona_pesca.html` | 6 | ¿A qué zona voy? Sliders SST/clorofila/profundidad → prob. de éxito + kg + por qué |
| `c8_velocidad_optima.html` | 8 | Velocidad óptima de crucero (ley cúbica: combustible vs. tiempo → costo mínimo) |
| `c6_sobreajuste.html` | 6 | Sobreajuste (overfitting): grado del polinomio → error train vs. test (escala log) |
| `dt09_concentracion_renta.html` | Caso DT-009 | Concentración de renta: reparto de cuota → Lorenz + Gini + HHI (datos CFP 4/2024) |
| `dt11_ais_esfuerzo.html` | Caso DT-011 | Rastro AIS: clasificación por velocidad + apagón de transpondedor (PSMA) |
| `c10_sos_el_capitan.html` | 10 (síntesis) | Juego de decisiones: 1 marea, 4 decisiones (zona/velocidad/umbral/ética AIS) → tablero |

## Cómo se sirven (una sola vez)
Estos archivos deben estar **públicos** y servidos por **GitHub Pages** del repo `PesquerosEnIA/curso-ia-produccion-pesquera`.

### 1) Publicar los archivos (rama `master` + `prod`)
Los `.html` de `interactivos/` van al repo público (igual que los decks). Ver el flujo en la memoria del proyecto
(checkout selectivo desde `aula-moodle` → commit en `master` → push a `origin` y `prod`).

### 2) Activar GitHub Pages (en cada repo donde quieras servirlo)
En **GitHub → Settings → Pages**:
- **Source:** Deploy from a branch
- **Branch:** `master` · **Folder:** `/ (root)`
- Guardar. En ~1 min queda disponible.

### 3) URL resultante
```
https://pesquerosenia.github.io/curso-ia-produccion-pesquera/interactivos/c6_umbral_decision.html
```
(Esa es la URL que usan los prompts `05b_*` de cada clase.)

## Alternativa sin Pages (para probar rápido)
jsDelivr sirve el repo público por CDN:
```
https://cdn.jsdelivr.net/gh/PesquerosEnIA/curso-ia-produccion-pesquera@master/interactivos/c6_umbral_decision.html
```
> Nota: jsDelivr es ideal para PDF/PNG (ya probado). Para **.html embebido en iframe**, GitHub Pages es la vía recomendada
> porque garantiza `Content-Type: text/html`. Si Pages no está activo, probá primero la URL de jsDelivr en el navegador.
