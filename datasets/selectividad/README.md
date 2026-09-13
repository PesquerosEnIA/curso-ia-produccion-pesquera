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

## Pendiente / a confirmar con el autor

La semántica exacta de algunas columnas (hay varias "proporción retenidos") y la dirección/parametrización de la ojiva en cada hoja conviene **confirmarla con Ariel** antes de derivar CSVs limpios y publicables por talla. Este README y los interactivos usan por ahora los **parámetros ajustados** (L50/RS) como fuente de verdad.
