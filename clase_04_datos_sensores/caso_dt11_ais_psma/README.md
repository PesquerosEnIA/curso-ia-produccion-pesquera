# Caso DT-011 — AIS/VMS y verificación del PSMA (AMERP)

**Aporta a:** DT-ALGP-2026-011 (adhesión al PSMA / AMERP)
**Encaje en el curso:** Clase 4 (datos y sensores — fuentes AIS/VMS) y/o Clase 8 (optimización y agentes — monitoreo operativo)
**Autor:** Ariel Giamportone — Ing. Pesquero, Científico de datos e IA, docente-investigador UTN FRTDF, fundador Pesqueros en IA

---

## Idea

El PSMA (AMERP) permite a un puerto negar entrada o inspeccionar a un buque sospechado de pesca INDNR, pero su aplicación necesita datos. El caso reconstruye el tablero: posición, esfuerzo, detección de apagones de AIS y un **score de riesgo previo al arribo** que ordena buques por prioridad de inspección.

> **Frase ancla:** *Lo que no transmite, igual deja rastro. El apagón de AIS es, en sí mismo, un dato.*

## Qué se enseña

| Nivel | Contenido |
|---|---|
| 🟢 Novato | Leer AIS, mapear la flota (folium + estático), separar pesca de tránsito por velocidad |
| 🟡 Intermedio | Esfuerzo por buque (haversine), clasificación de comportamiento, ejercicios (KMeans, umbrales) |
| 🔴 Avanzado | Detección de apagones AIS, score de riesgo PSMA, sensibilidad, apéndice API Global Fishing Watch |

## Datos

Trayectorias **sintéticas y verosímiles** (`ESTIMADO`, formato tipo Global Fishing Watch), en `recursos/ais_flota_sintetica.csv`. El apéndice del notebook avanzado trae la plantilla para reemplazarlas por datos reales de la **GFW API** (abiertos, requiere token). La línea del borde de la ZEE es **ilustrativa** (no es la milla 200 real).

## Huecos declarados

- Número de ley AMERP en Argentina: **CONFIRMADO** — **Ley 27.815** (aprueba la adhesión de Argentina al AMERP; sancionada 24-jun-2026, promulgada y publicada en el Boletín Oficial en julio de 2026).
- Token de la GFW API: **HUECO** — gratuito, se solicita en globalfishingwatch.org.

## Resultado de referencia

De 4 buques, solo "Estrella FOC" (pabellón de conveniencia, apagón de ~15 h cerca del borde) supera el umbral de inspección (score PSMA 82). Los buques de bandera nacional sin apagón quedan en ~2.

## Estructura

```
caso_dt11_ais_psma/
├── notebooks/   → caso_dt11_ais_psma_{novato,intermedio,avanzado}.ipynb
└── recursos/    → ais_flota_sintetica.csv · mapa_flota.html
```
