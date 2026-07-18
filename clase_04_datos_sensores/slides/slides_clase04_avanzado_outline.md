# Outline de Slides — Clase 4 · 🔴 Nivel AVANZADO
## Datos y Sensores del Dominio Pesquero

**Curso:** IA Aplicada a la Producción Pesquera | UTN FRCh · PesquerosEnIA
**Docentes:** Ariel Giamportone · Soraya Corvalán | **Duración:** 2 horas | ~14 slides
*Tono: técnico. Asume Python/pandas y nociones de ML. Foco en pipeline y features.*

---

### Slide 1 — Portada
**Título:** Datos y Sensores del Dominio Pesquero
**Subtítulo:** 🔴 Nivel Avanzado — Datos reales, frentes e ingeniería de features
*Nota: Público que ya programa. Ir rápido al valor diferencial.*

---

### Slide 2 — Agenda
- Ingesta de datos reales (Copernicus, NOAA ERDDAP) + fallback
- NetCDF y xarray
- Detección de frentes térmicos (gradiente de SST)
- Feature engineering ambiental para modelado
- Calidad de datos y sesgos
- Desafío integrador (frente ↔ esfuerzo)

---

### Slide 3 — Del dato crudo al feature: el pipeline
Diagrama: **Fuente real → ingesta → limpieza → features → modelo (Clase 6)**.
*Nota: Ubicar esta clase como la capa de datos que alimenta el modelado posterior.*

---

### Slide 4 — Ingesta con patrón robusto
`fuente real (con credenciales) → fallback sintético`
Código `copernicusmarine.open_dataset(...)` dentro de try/except.
*Nota: Reproducibilidad: el notebook corre en cualquier entorno, con o sin credenciales.*

---

### Slide 5 — Copernicus Marine vs NOAA ERDDAP
| | Copernicus | NOAA ERDDAP |
|---|---|---|
| Registro | Sí (gratis) | No |
| Resolución SST | 5–9 km (L4) | hasta 1 km (MUR) |
| Acceso | `copernicusmarine` | `erddapy` |
*Nota: L4 = interpolado sin gaps; clave para series continuas.*

---

### Slide 6 — NetCDF y xarray
El cubo `sst[tiempo, lat, lon]` + metadatos. Operaciones etiquetadas:
`groupby("time.month").mean()`, `.differentiate("latitude")`, lazy con dask.
*Nota: Contrastar con pandas: por qué xarray para datos gridados.*

---

### Slide 7 — Frentes térmicos por gradiente
`|∇SST| = sqrt(grad_lat² + grad_lon²)` → umbral P90.
Mostrar el mapa de gradiente del notebook (magma).
*Nota: Suavizar antes de derivar en datos reales (ruido de píxel).*

---

### Slide 8 — Por qué importan los frentes
Convergencia Malvinas-Brasil → nutrientes → agregación de merluza/calamar.
El frente es un **predictor** de zona, no solo un fenómeno físico.
*Nota: Enlazar con acústica (charla/otra unidad) si aplica.*

---

### Slide 9 — Feature engineering ambiental
Tabla de features: `sst_anomalia`, `dist_optimo_termico`, `indice_habitat`, `intensidad_frente`.
*Nota: Mostrar que `indice_habitat` correlaciona mejor que las crudas.*

---

### Slide 10 — El índice de hábitat
`indice = f(SST templada) × f(clorofila alta)`
Combina dos señales físicas en un predictor biológicamente interpretable.
*Nota: Interpretabilidad importa para la aceptación del sector.*

---

### Slide 11 — Calidad de datos: lo que no se ve
- Dark vessels (AIS off) → fusión AIS+SAR
- Gaps por nubosidad → L4 / gap-filling (DINEOF)
- Resolución vs frentes finos
*Nota: Un modelo es tan bueno como sus datos.*

---

### Slide 12 — El sesgo más peligroso: esfuerzo ≠ recurso
Los partes reflejan **dónde se pescó**, no dónde **hay** recurso.
Entrenar sin corregir → el modelo replica el comportamiento de la flota, no la biología.
*Nota: Punto crítico y frecuentemente ignorado.*

---

### Slide 13 — Desafío integrador
SST real 1 semana → anomalía → frente diario → cruzar con GFW effort → correlación frente↔esfuerzo.
¿El esfuerzo sigue al frente o hay retardo?
*Nota: Entregable = notebook reproducible + figura.*

---

### Slide 14 — Cierre
La capa de datos define el techo del modelo (Clase 6).
Referencias: Copernicus, erddapy, xarray, GFW API, Kroodsma 2018.
*Nota: Invitar a traer un caso de datos propio para la próxima.*
