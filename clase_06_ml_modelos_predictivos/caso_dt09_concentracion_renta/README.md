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
| 🔴 Avanzado | Bootstrap sobre datos REFERENCIALES (IC 95 %), contrafáctico de redistribución, desafío |

## Datos

Participaciones en la CMP de merluza negra: Estremar ~37,83 %, Argenova ~23,02 %, Pesantar ~19,94 % (**REFERENCIAL**, DT-009). La cola de operadores menores es **ESTIMADO / ilustrativa** (para el ejercicio distributivo, no es una afirmación sobre firmas concretas). **Cerrar antes de publicar:** acto de asignación de CITC del CFP.

## Resultado de referencia

CR3 ≈ 80,8 % · HHI ≈ 2440 (moderada bajo guía 2010 / **alta** bajo guía 2023) · Gini ≈ 0,55. Bajar el HHI a 1800 exigiría "achatar" ~82 % a los tres grandes.

## Estructura

```
caso_dt09_concentracion_renta/
├── notebooks/   → caso_dt09_concentracion_{novato,intermedio,avanzado}.ipynb
└── recursos/
```
