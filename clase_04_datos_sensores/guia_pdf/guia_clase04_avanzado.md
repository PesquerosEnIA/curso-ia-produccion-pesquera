# Clase 4 — Datos y Sensores del Dominio Pesquero
## 🔴 Nivel AVANZADO

> **Para participantes cómodos con Python/pandas y nociones de ML.** Esta guía asume el
> marco conceptual de la variante intermedia y se concentra en **datos reales, pipelines,
> detección de frentes e ingeniería de features**. Acompaña al notebook
> `clase04_datos_avanzado.ipynb`.
> *(Existen variantes 🟢 Novato y 🟡 Intermedio de esta misma clase.)*

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Docentes:** Ariel Giamportone · Soraya Corvalán · **Duración:** 2 horas

---

## Objetivos

1. Ingerir datos oceanográficos **reales** (Copernicus Marine, NOAA ERDDAP) con patrón robusto *fuente-real → fallback*.
2. Manejar **NetCDF** con `xarray` (el estándar de datos gridados espacio-temporales).
3. Detectar **frentes térmicos** por gradiente espacial de SST.
4. Construir **features ambientales** (anomalías, índice de hábitat) para modelado.
5. Auditar **calidad y sesgos** de los datos antes de modelar.

---

## 1. Acceso programático a datos reales

### Copernicus Marine (CMEMS)
El servicio operacional europeo. Vía la *Copernicus Marine Toolbox* (`pip install copernicusmarine`):

```python
import copernicusmarine as cm
ds = cm.open_dataset(
    dataset_id="cmems_obs-sst_glo_sst_l4_nrt_observations_010_001",
    variables=["analysed_sst"],
    minimum_longitude=-65, maximum_longitude=-44,
    minimum_latitude=-55, maximum_latitude=-34,
)
sst_c = ds["analysed_sst"] - 273.15   # Kelvin → °C
```

Requiere registro gratuito. Productos clave para la PCA: SST L4 (interpolada, sin gaps),
color del océano (clorofila), física GLORYS12 (corrientes/temperatura subsuperficial).

### NOAA ERDDAP (sin credenciales)
```python
from erddapy import ERDDAP
e = ERDDAP(server="https://coastwatch.pfeg.noaa.gov/erddap", protocol="griddap")
e.dataset_id = "jplMURSST41"     # MUR SST 1 km
e.variables = ["analysed_sst"]
e.constraints = {"latitude>=": -55, "latitude<=": -34,
                 "longitude>=": -65, "longitude<=": -44}
ds = e.to_xarray()
```

### Patrón robusto de ingesta
En producción, **intentá la fuente real y degradá a sintético** si falla (sin credenciales,
sin red, servicio caído). Así el pipeline es reproducible en cualquier entorno (incluido Colab).
El notebook implementa exactamente este patrón.

---

## 2. NetCDF y xarray

El **NetCDF** es un "cubo" de datos: `sst[tiempo, lat, lon]` más metadatos (unidades, escala,
fuente). `xarray` lo maneja con semántica etiquetada:

```python
import xarray as xr
ds = xr.open_dataset("sst_pca.nc")
clim = ds["analysed_sst"].groupby("time.month").mean()      # climatología mensual
anomalia = ds["analysed_sst"].groupby("time.month") - clim  # anomalía
frente = anomalia.differentiate("latitude")                 # derivada espacial
```

Ventajas sobre pandas para datos gridados: indexado por coordenadas reales, operaciones
por dimensión (`.mean("time")`), y lazy loading con `dask` para series grandes.

---

## 3. Detección de frentes térmicos

Los frentes concentran nutrientes y recursos. Se detectan con la **magnitud del gradiente
espacial** de SST:

```python
grad_lat, grad_lon = np.gradient(sst)
gradiente = np.sqrt(grad_lat**2 + grad_lon**2)   # |∇SST|
frentes = gradiente >= np.percentile(gradiente, 90)
```

Un umbral por percentil (P90) marca las celdas frontales. En datos reales conviene suavizar
(filtro gaussiano) antes de derivar, para no amplificar ruido de píxel. Los frentes así
detectados son un **predictor clásico** de agregación de merluza y calamar.

---

## 4. Ingeniería de features ambientales

Las variables crudas rara vez son la mejor entrada a un modelo. Features útiles en pesca:

| Feature | Definición | Por qué aporta |
|---------|-----------|----------------|
| `sst_anomalia` | SST − media (o climatología) | Aísla lo inusual de lo esperable |
| `dist_optimo_termico` | \|SST − 10 °C\| | Relación no lineal con la merluza |
| `indice_habitat` | f(SST templada) × f(clorofila alta) | Combina dos señales en una |
| `intensidad_frente` | \|∇SST\| en la celda de la marea | Proxy de frente productivo |
| features estacionales | seno/coseno del mes | Captura ciclo anual sin saltos |

El `indice_habitat` suele **correlacionar mejor** con la captura que cualquier variable
cruda — esa es la ganancia del feature engineering, y alimenta directamente la Clase 6.

---

## 5. Calidad de datos y sesgos

- **Dark vessels:** AIS apagado → GFW subestima esfuerzo. Corrección: fusión **AIS + SAR**.
- **Gaps por nubosidad:** SST/clorofila ópticas fallan con nubes. Usar productos **L4**
  interpolados o *gap-filling* (DINEOF, kriging).
- **Resolución:** 5–9 km puede perder frentes costeros finos; evaluar productos de 1 km (MUR).
- **Sesgo de esfuerzo:** los partes reflejan **dónde se pescó**, no dónde **hay** recurso.
  Entrenar sin corregir este sesgo produce modelos que replican el comportamiento pasado
  de la flota, no la biología.
- **Alineación espacio-temporal:** unir captura con la variable ambiental **del mismo día y
  celda**, nunca con la media climatológica.

---

## Desafío integrador

Descargá una semana de SST real (Copernicus), calculá la anomalía respecto de la
climatología mensual, detectá el frente diario por gradiente, bajá el *fishing effort* de
GFW para la misma zona/fecha y evaluá la correlación **frente ↔ esfuerzo**. Discutí si el
esfuerzo sigue al frente o hay retardo, y qué implica para la predicción de zonas (Clase 6).

---

## Referencias técnicas

- Copernicus Marine Toolbox — https://marine.copernicus.eu
- erddapy (NOAA ERDDAP) — https://ioos.github.io/erddapy
- xarray — https://tutorial.xarray.dev
- Global Fishing Watch API — https://globalfishingwatch.org/our-apis
- Kroodsma, D. A., et al. (2018). Tracking the global footprint of fisheries. *Science*, 359(6378), 904–908.
- Alemany, D., et al. — Frentes oceánicos y distribución de recursos en la PCA (INIDEP).
