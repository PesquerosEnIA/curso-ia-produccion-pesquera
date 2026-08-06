# Caso DT-009 — Concentración de la renta pesquera

**Aporta a:** DT-ALGP-2026-009 (dependencia tecnológica naval y concentración de renta en merluza negra) y DT-ALGP-2026-012 (captura silenciosa de la renta pesquera)
**Encaje en el curso:** Clase 6 (ML y modelos predictivos — como caso de analítica de dominio) y/o Clase 9 (visualización y dashboards)
**Autor:** Ariel Giamportone — Ing. Pesquero, Científico de datos e IA, docente-investigador UTN FRTDF, fundador Pesqueros en IA

---

## Idea

La CITC es un instrumento legítimo; su *aplicación* puede concentrar la renta sin que eso sea evidente en un texto. El caso convierte esa afirmación de economía política en índices de concentración estándar (CR, HHI, Gini, curva de Lorenz), reproducibles y trazables.

> **Frase ancla:** *La concentración no se declama; se calcula. Un solo índice vuelve visible lo que el discurso mantiene difuso.*

## Qué se enseña

| Nivel | Contenido |
|---|---|
| 🟢 Novato | Participaciones, CR3, lectura intuitiva de HHI y Gini, curva de Lorenz |
| 🟡 Intermedio | Gini y HHI desde cero, umbrales de política, ejercicios (fusión, redistribución) |
| 🔴 Avanzado | Análisis de sensibilidad (dato CONFIRMADO), dos universos de medición, contrafáctico de nuevos entrantes, desafío |

## Datos

Participaciones en la CMP de merluza negra: **Estremar/San Arawa 37,83 %, Argenova 23,02 %, Pesantar 19,94 %** — **CONFIRMADO** (Resolución CFP 4/2024, Anexo IF-2024-00000277-CFP-CFP, Acta CFP 15/2024, BO 10-sep-2024). Las tres empresas concentran el **80,80 % de la CMP = el 100 % de la CITC** asignada; el resto es **Reserva de Administración (18,80 %) + Fondo de Reasignación (0,40 %)**, que no son empresas (no hay "operadores menores").

## Resultado de referencia

Sobre la CMP (incluye la reserva estatal): **CR3 ≈ 80,8 %** · **HHI ≈ 2712** (alta bajo ambas guías) · **Gini ≈ 0,32**. Sobre la CITC asignada (3 empresas = 100 %): **HHI ≈ 3614**, CR3 = 100 %. Con solo 3 titulares el HHI no puede bajar de 3.333: **desconcentrar exige incorporar nuevos actores** — la Reserva de Administración, hoy repartida entre los mismos 3, no alcanza.

## Estructura

```
caso_dt09_concentracion_renta/
├── notebooks/   → caso_dt09_concentracion_{novato,intermedio,avanzado}.ipynb
└── recursos/
```
