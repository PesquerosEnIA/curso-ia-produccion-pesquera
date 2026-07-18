# Clase 1 — Estrategia y Transformación Digital en el Sector Pesquero
## 🔴 Nivel AVANZADO

> **Para gestores, decisores y perfiles técnicos** que necesitan **liderar** la adopción de
> IA, no solo entenderla. Foco en **estrategia de datos, priorización, ROI y gestión del
> cambio**. Asume el marco conceptual de la variante intermedia.
> *(Existen variantes 🟢 Novato y 🟡 Intermedio.)*

**Curso:** IA Aplicada a la Producción Pesquera · UTN FRCh · PesquerosEnIA
**Docentes:** Ariel Giamportone · Soraya Corvalán · **Duración:** 2 horas

---

## Objetivos

1. Evaluar la **madurez digital** de una organización pesquera y ubicarla en un modelo de referencia.
2. **Priorizar** iniciativas de IA por impacto vs. esfuerzo (evitar el "piloto que nunca escala").
3. Estimar **ROI** y construir el caso de negocio de una iniciativa concreta.
4. Anticipar la **gestión del cambio** y las barreras organizacionales, no solo las técnicas.

---

## 1. Modelo de madurez digital pesquera

Ubicar a la organización antes de decidir hacia dónde ir:

| Nivel | Estado | Señales típicas |
|-------|--------|-----------------|
| 1 · Reactivo | Datos en papel/planillas aisladas | Partes de pesca manuales; decisiones "a ojo" |
| 2 · Digitalizado | Datos capturados, no integrados | Excel por área; sin cruce entre fuentes |
| 3 · Integrado | Datos centralizados y accesibles | Dashboards; una fuente de verdad |
| 4 · Predictivo | Modelos que anticipan | Predicción de zonas, mantenimiento, demanda |
| 5 · Autónomo | Decisiones asistidas/automatizadas | Agentes de monitoreo; optimización continua |

**Regla:** no se salta de 1 a 4. La predicción sin datos integrados (nivel 3) fracasa.
La primera inversión suele ser **integrar datos**, no comprar IA.

---

## 2. Priorización: impacto vs. esfuerzo

Toda iniciativa se ubica en una matriz 2×2. Del propio curso (ver también la matriz de
viabilidad de la Clase 10):

- **Alto impacto / bajo esfuerzo (hacer ya):** predicción de zonas con datos abiertos,
  asistentes LLM para reportes, dashboards sobre datos existentes, análisis AIS.
- **Alto impacto / alto esfuerzo (piloto):** visión artificial en planta (hardware),
  trazabilidad blockchain, mantenimiento predictivo con instrumentación.
- **Bajo impacto:** descartar o posponer, por más "de moda" que esté la tecnología.

> Antídoto contra el *pilot purgatory*: definir de entrada el **criterio de escalado**
> (qué métrica, qué umbral) antes de lanzar el piloto.

---

## 3. El caso de negocio (ROI)

Estructura mínima para defender una inversión:

```
ROI = (Beneficio anual − Costo anual) / Inversión inicial
```

- **Beneficios cuantificables:** ahorro de combustible (10–20% de rutas/velocidad),
  reducción de días improductivos (20–30% en búsqueda), menos descarte, menor carga
  administrativa (LLMs), menos mermas por calidad.
- **Costos:** datos/licencias, cómputo, integración, capacitación, mantenimiento del modelo.
- **Intangibles:** cumplimiento regulatorio, certificación (MSC), reputación, retención de talento.

**Ejemplo (orden de magnitud):** una flota de 20 arrastreros que reduce 15% el consumo con
optimización de velocidad/rutas evita ~USD 1–2 M/año en gasoil (ver Clase 8), con una
inversión inicial modesta en analítica. El ROI positivo suele estar en meses, no años,
para las iniciativas de "fruta baja".

---

## 4. Datos como activo estratégico

- **Gobernanza:** definir dueño del dato, calidad, retención y acceso antes de modelar.
- **Silos:** el mayor bloqueante no es el algoritmo, es que los datos viven en sistemas
  desconectados (barco, planta, administración).
- **Dato compartido > dato en silo:** iniciativas como Global Fishing Watch muestran que la
  transparencia agrega valor sectorial. Evaluar consorcios de datos con pares.
- **Sesgo de esfuerzo:** los datos de captura reflejan dónde se pescó, no dónde hay recurso;
  una estrategia de datos madura lo corrige con datos biológicos (INIDEP).

---

## 5. Gestión del cambio (donde mueren los proyectos)

La tecnología rara vez es el problema; la adopción sí. Palancas:
- **Patrocinio ejecutivo** real y una métrica de negocio clara.
- **Quick wins** visibles en 60–90 días para construir confianza.
- **Involucrar al operador** (capitán, jefe de planta): la IA que ignora el saber tácito se
  rechaza. Diseñar IA que **asiste**, no que reemplaza.
- **Capacitación** en el idioma y el dominio (justamente el objetivo de este curso).
- **Medir y comunicar** el impacto; iterar.

---

## Actividad avanzada: mini-plan de transformación

Elegí una organización (real o representativa) y esbozá:

1. Su **nivel de madurez** (1–5) con evidencia.
2. **Tres iniciativas** ubicadas en la matriz impacto/esfuerzo.
3. El **caso de negocio** de la iniciativa prioritaria (beneficio, costo, ROI aproximado).
4. Dos **riesgos de adopción** y su mitigación.

Este mini-plan puede ser la base de tu **proyecto integrador**.

---

## Para profundizar

- FAO (2024). *Digital Technologies and Innovation in Fisheries and Aquaculture*.
- CEPAL/OCDE (2021). *Tecnologías digitales para la transformación productiva en América Latina*.
- Kroodsma, D. A., et al. (2018). Tracking the global footprint of fisheries. *Science*, 359(6378).
- Marco de madurez digital (referencia adaptable): modelos tipo *Industry 4.0 Maturity Index* (acatech).
- PesquerosEnIA — github.com/PesquerosEnIA
