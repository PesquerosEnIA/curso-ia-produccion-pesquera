# Selectividad de artes de pesca — dataset (2015)

Datos experimentales de **selectividad** de artes y dispositivos selectivos en la pesquería de langostino / bycatch de merluza, con estimación de parámetros por **máxima verosimilitud (MVS)**.

- **Autor:** Ariel Giamportone.
- **Fuente original:** https://github.com/arielgiamportone/Selectividad_artes_de_pesca
- **Informe:** *Optimizando la sostenibilidad pesquera — explorando la selectividad artificial con enfoque científico* — https://www.researchgate.net/publication/378582619

## Contenido

- `Calculo_de_selectividad_2015.xlsx` — planilla original (método de **copo cubierto** / *covered codend*). Cuatro hojas, una por arte/dispositivo:
  - **Sobrecopo** — copo desnudo (selectividad de la malla sobre merluza).
  - **Dejupa** — grilla selectiva **DEJUPA**.
  - **FLEXIGIRD** — grilla **Flexigrid**.
  - **Tangonera** — red tangonera (retención de merluza).

Cada hoja tiene, por talla: nº de individuos en el copo y en el sobrecopo, proporción retenida, y el ajuste de la ojiva logística por MVS (verosimilitud / −log verosimilitud).

## Parámetros ajustados (MVS) usados en los interactivos del curso

| Dispositivo | L50 (cm) | RS ≈ L75−L25 (cm) |
|---|---|---|
| Copo desnudo | ≈ 42,6 | ≈ 5,7 |
| DEJUPA | ≈ 35,9 | ≈ 14,6 |
| Flexigrid | ≈ 37,4 | ≈ 11,9 |
| Tangonera | ≈ 29,9 | ≈ 7,2 |

**L50** = talla a la que se retiene el 50%. La **talla mínima** de merluza es 35 cm: los dispositivos con L50 cercano o superior a 35 cm son los que mejor protegen a los juveniles.

## Interactivos del curso que usan estos datos

- `interactivos/selectividad_arte.html` — simulador de curvas reales por dispositivo.
- `interactivos/selectividad_ajuste.html` — ajuste de la ojiva a los datos (puente con ML / Clase 6).
- `interactivos/selectividad_animacion.html` — animación del mecanismo (grilla + malla).

## CSVs limpios por talla (derivados)

Un CSV por dispositivo con la **proporción retenida observada** y la **curva ajustada S(L)**:

| Archivo | Columna observada usada | Dirección |
|---|---|---|
| `dejupa_por_talla.csv` | retenidos_copo / total_que_entró | creciente |
| `sobrecopo_por_talla.csv` | copo / (copo+sobrecopo) | creciente |
| `flexigrid_por_talla.csv` | "Proporción retención" (col. observada) | creciente |
| `tangonera_por_talla.csv` | "Proporción retención" | **decreciente** ⚠ |

## ⚠ Hallazgo — la tangonera tiene selectividad decreciente

Las grillas (DEJUPA, Flexigrid) y el copo tienen ojiva **creciente** (peces chicos escapan, grandes se retienen). La **tangonera es al revés**: su retención de merluza **decrece** con la talla (retiene los chicos, suelta los grandes) — confirmado por la columna S(L) de esa hoja. Los interactivos representan la tangonera con ojiva creciente por simplicidad; **a confirmar con Ariel** si conviene corregir el simulador para reflejar la dirección real (cambia qué tallas retiene, no la conclusión de que retiene juveniles). El resto de los datos y parámetros están verificados.
