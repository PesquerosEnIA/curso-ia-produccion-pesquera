# Clase 4 — Datos y Sensores del Dominio Pesquero

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN Facultad Regional Chubut | PesquerosEnIA
**Docentes:** Ariel Giamportone · Soraya Corvalán
**Duración:** 2 horas
**Modalidad:** Semipresencial / Virtual

---

## Objetivos de la clase

1. Identificar y caracterizar las principales fuentes de datos del dominio pesquero: oceanográficas, satelitales, de rastreo y operativas.
2. Comprender las variables ambientales clave (SST, clorofila-a, profundidad, corrientes) y su relación con la distribución de los recursos pesqueros.
3. Acceder y explorar plataformas de datos abiertos del sector: INIDEP, Copernicus, NOAA y Global Fishing Watch.
4. Entender los formatos de datos más comunes: CSV, NetCDF, JSON, Shapefile.
5. Realizar un análisis exploratorio básico de un dataset oceanográfico en Python (notebook adjunto).

---

## 1. El ecosistema de datos del sector pesquero

Un solo barco pesquero en operación genera múltiples flujos de datos simultáneamente:

| Fuente | Tipo de dato | Frecuencia | Ejemplo |
|--------|-------------|-----------|---------|
| GPS/GNSS | Posición geográfica | Continua | lat: -43.5°, lon: -60.2° |
| AIS transponder | Posición + velocidad + identidad | Cada 2-10 s | MMSI, SOG, COG |
| VMS | Posición + velocidad | Cada 30-60 min | Sistema regulatorio |
| Ecosonda | Profundidad + detección cardúmenes | Continua | Señal acústica (kHz) |
| Sensor temperatura agua | SST superficial | Cada pocos minutos | 9.4°C |
| Sensor temperatura bodega | Temperatura de carga | Continua | -18°C (congelado) |
| Partes de pesca | Capturas + esfuerzo | Por lance | Especie, kg, hora, zona |
| Balanza de pesca | Peso captura | Por lance | 4.200 kg merluza |

A esto se suman los datos **externos** que no genera el barco pero que son críticos para la toma de decisiones:
- **Imágenes satelitales** de temperatura superficial, clorofila y viento
- **Modelos oceanográficos** de corrientes, profundidad y anomalías
- **Datos meteorológicos** de viento, altura de ola y visibilidad
- **Datos regulatorios** de cuotas, vedas y áreas protegidas

> **La paradoja del sector pesquero:** genera grandes volúmenes de datos pero históricamente los ha subutilizado. Un barco con 20 años de partes de pesca tiene un dataset de alto valor que rara vez se analiza con herramientas modernas.

---

## 2. Variables ambientales clave para la pesca

### 2.1. Temperatura Superficial del Mar (SST)

La SST es la variable oceanográfica más relevante para la actividad pesquera. Cada especie tiene un rango de temperatura preferencial:

| Especie | Rango SST óptimo | Donde se encuentra |
|---------|-----------------|-------------------|
| Merluza hubbsi | 4–12 °C | Frente patagónico, zona del frente |
| Calamar illex | 8–16 °C | Zona de convergencia Malvinas-Brasil |
| Langostino patagónico | 6–14 °C | Fondos blandos del golfo San Matías, San Jorge |
| Vieira patagónica | 3–10 °C | Plataforma media y externa |

Los **frentes oceánicos** — zonas donde se mezclan la Corriente de Malvinas (fría, ~5–8°C) y la Corriente de Brasil (cálida, ~20–24°C) — son áreas de alta productividad biológica y concentración de recursos pesqueros.

**Fuentes de datos de SST:**
- **Copernicus Marine Service** (CMEMS): productos de SST con resolución de 0.083° (~9 km), análisis diario
- **NOAA CoralTemp / CoastWatch:** SST satelital de alta resolución (~1 km)
- **MODIS Terra/Aqua (NASA):** imágenes de SST a 1 km de resolución, disponibles en Earthdata

### 2.2. Clorofila-a (Chl-a)

La clorofila-a es el pigmento fotosintético del fitoplancton — la base de la cadena trófica marina. Alta concentración de clorofila indica **alta productividad primaria**, que atrae zooplancton, anchoíta y eventualmente merluza y calamar.

- Unidad: mg/m³ o μg/L
- Rango en la PCA: 0.1–10 mg/m³ (hasta 30 en zonas de surgencia)
- **Floración de primavera** (septiembre-noviembre): explosión de clorofila en el golfo San Matías y sur del golfo San Jorge, relacionada con la llegada del verano austral

**Fuentes:** Copernicus Marine Service (producto de color del océano), NASA MODIS-Aqua

### 2.3. Profundidad batimétrica

La distribución batimétrica determina el hábitat de cada especie:
- Merluza: principalmente 50–300 m (demersal)
- Calamar: 0–300 m (migratorio vertical, pesca nocturna)
- Langostino: 20–80 m (fondos blandos, zona costera)

La isobata de 200 m (borde de la plataforma continental) es una barrera biogeográfica importante: la merluza adulta de mayor talla se concentra típicamente entre 100–200 m.

**Fuentes:** GEBCO (General Bathymetric Chart of the Oceans), ETOPO1 (NOAA)

### 2.4. Corrientes oceánicas

Las corrientes determinan el transporte de larvas, nutrientes y los propios cardúmenes:

- **Corriente de Malvinas (Falkland Current):** fluye hacia el norte a lo largo del talud continental patagónico. Agua fría (~4–8°C), rica en nutrientes.
- **Corriente de Brasil:** fluye hacia el sur por la costa uruguaya. Agua cálida (~20–24°C), pobre en nutrientes.
- **Frente de Brasil-Malvinas:** zona de convergencia en ~38–40°S. Área de alta productividad y concentración de recursos.
- **Corriente Costera Patagónica:** flujo hacia el norte en la plataforma interior patagónica.

**Fuentes:** Copernicus Marine Service (modelo GLORYS12 — reanálisis global), HYCOM (NCEP/NOAA)

---

## 3. Sistemas de monitoreo y rastreo de flotas

### 3.1. AIS — Automatic Identification System

El AIS es un sistema de radiocomunicación marítima que transmite automáticamente:
- **Identificación:** MMSI (Marine Mobile Service Identity), nombre del barco, indicativo de llamada
- **Posición:** latitud, longitud (GPS)
- **Movimiento:** velocidad sobre el fondo (SOG), curso sobre el fondo (COG), rumbo (HDG)
- **Estado:** en navegación, fondeado, restringido en maniobrabilidad, etc.
- **Dimensiones y tipo:** eslora, manga, tipo de barco (pesquero, tanquero, etc.)

**Clases de AIS:**
- **Clase A:** obligatorio para buques ≥300 GT y todos los pasajeros. Transmite cada 2–10 segundos.
- **Clase B:** voluntario para barcos menores. Transmite cada 30 segundos a 3 minutos.

**Limitaciones:**
- Algunos buques pueden **apagar el AIS** voluntariamente (*dark vessels*) para evadir monitoreo
- Cobertura terrestre: ~50 km de costa. En alta mar se requieren satélites
- Posibilidad de falsificación de identidad o posición

### 3.2. VMS — Vessel Monitoring System

El VMS es un sistema de monitoreo satelital **obligatorio** para todos los buques pesqueros argentinos de más de 28 metros de eslora, gestionado por la **Subsecretaría de Pesca y Acuicultura de la Nación**.

- Transmisión cada 30–60 minutos (configurable)
- Satélite Inmarsat o equivalente
- Datos restringidos: no son públicos (a diferencia del AIS)
- Permite verificar el cumplimiento de áreas de veda, zonas de exclusión y límites de ZEE

### 3.3. Global Fishing Watch

[Global Fishing Watch](https://globalfishingwatch.org) es una plataforma open-access que utiliza datos AIS satelitales y modelos de machine learning para:
- Monitorear la actividad de ~70.000 buques en tiempo real
- **Detectar pesca** mediante análisis de patrones de movimiento (velocidad + rumbo irregular = probable pesca)
- Estimar el esfuerzo pesquero por zona, especie objetivo y país
- Identificar *dark vessels* mediante fusión de imágenes SAR + AIS
- Proveer datos descargables para investigación (requiere registro gratuito)

> "El AIS y Global Fishing Watch hacen que el mar sea, por primera vez en la historia, genuinamente transparente." — David Kroodsma, Science 2018

---

## 4. Registros de captura y datos de planta

### 4.1. Partes de pesca (bitácora de pesca)

El **parte de pesca** es el documento principal de registro operativo de cada lance o jornada de pesca. En Argentina, su presentación es obligatoria para obtener la constancia de desembarco.

Variables típicas de un parte de pesca:
- Fecha, hora inicio/fin del lance
- Posición geográfica (lat/lon)
- Profundidad de pesca
- Especie capturada, cantidad (kg o unidades), descarte
- Arte de pesca (arrastre de fondo, palangre, pota, cerco)
- Condiciones meteorológicas

**El desafío:** históricamente estos datos se registraban en papel. La digitalización progresiva permite análisis masivos pero requiere limpieza de datos.

### 4.2. Datos de planta procesadora

Una planta procesadora genera datos de:
- **Rendimiento industrial:** kg de materia prima vs. kg de producto terminado (ej: rendimiento filete ~40%)
- **Control de calidad:** talla media, estado de frescura, presencia de parásitos
- **Trazabilidad de lote:** qué barco, qué zona, qué fecha corresponde a cada lote
- **Temperatura de cadena fría:** registro continuo de temperaturas de cámara y transporte
- **Eficiencia de línea:** tiempo activo vs. tiempo parado por turno

---

## 5. Plataformas de datos abiertos del sector

### 5.1. Copernicus Marine Service (CMEMS)

La plataforma europea de datos oceanográficos es la más completa y accesible para Argentina:

- **SST diaria** a 0.05° resolución (~5 km): producto SST_GLO_SST_L4_NRT_OBSERVATIONS
- **Clorofila-a diaria** a 0.083°: producto OCEANCOLOUR_GLO_BGC_L4_NRT
- **Corrientes diarias** a 0.083°: producto GLOBAL_ANALYSIS_FORECAST_PHY
- **Batimetría:** GEBCO incluida
- **Acceso:** gratuito con registro en [marine.copernicus.eu](https://marine.copernicus.eu)
- **API Python:** `copernicusmarine` (pip install)

### 5.2. NOAA ERDDAP

El servidor de datos de la NOAA es otra fuente excelente:
- SST de alta resolución (GOES, AVHRR, MODIS)
- Anomalías de nivel del mar
- Temperatura subsuperficial
- **Acceso:** [coastwatch.pfeg.noaa.gov/erddap](https://coastwatch.pfeg.noaa.gov/erddap) — sin registro
- **API Python:** `erddapy` (pip install)

### 5.3. INIDEP

El Instituto Nacional de Investigación y Desarrollo Pesquero (INIDEP) es la fuente oficial argentina de:
- Datos de capturas por especie, zona y arte de pesca
- Evaluaciones de stock de merluza, calamar, langostino
- Campañas de investigación (datos batimétricas, oceanográficos, biológicos)
- Publicaciones técnicas en acceso abierto

Sitio: [inidep.edu.ar](https://www.inidep.edu.ar)

### 5.4. Global Fishing Watch (GFW)

Datos AIS descargables para investigación:
- Esfuerzo pesquero por zona y día (1/100° de resolución)
- Trayectorias de barcos individuales
- Clasificación del tipo de actividad (pesca, navegación, transbordo)

Sitio: [globalfishingwatch.org/data-download](https://globalfishingwatch.org/data-download)

---

## 6. Formatos de datos del sector

| Formato | Descripción | Uso en pesquerías | Herramienta |
|---------|-------------|------------------|-------------|
| **CSV/Excel** | Tabular, texto plano | Partes de pesca, capturas, producción | pandas, Excel |
| **NetCDF (.nc)** | Arreglos multidimensionales (lat × lon × tiempo) | SST, clorofila, corrientes | xarray, netCDF4 |
| **GeoTIFF (.tif)** | Imágenes georreferenciadas | Imágenes SAR, productos satelitales | rasterio, GDAL |
| **Shapefile (.shp)** | Vectores geográficos | Áreas de veda, límites ZEE, puertos | geopandas |
| **JSON/GeoJSON** | Texto estructurado, geoespacial | APIs de datos (GFW, NOAA), AIS | pandas, geopandas |
| **Parquet** | Columnar, comprimido | Big data de AIS, datasets grandes | pandas, dask |

### El formato NetCDF

El formato **NetCDF (Network Common Data Form)** merece atención especial porque es el estándar de datos oceanográficos y meteorológicos. Un archivo NetCDF es como un cubo de datos:

```
NetCDF de SST diaria:
- Dimensiones: latitud (n×), longitud (m×), tiempo (365×)
- Variable: sst[tiempo, latitud, longitud] — temperatura en °C
- Atributos: unidades, escala, fecha de creación, fuente
```

En Python, `xarray` es la librería principal para trabajar con NetCDF:
```python
import xarray as xr
ds = xr.open_dataset('sst_plataforma_continental_argentina.nc')
sst_media = ds['analysed_sst'].mean(dim='time')  # media temporal
```

---

## Actividad práctica: Notebook de exploración de datos oceanográficos

El notebook adjunto (`clase04_exploracion_datos_oceanograficos.ipynb`) propone un recorrido completo de exploración de datos del sector:

1. **Setup e importación** de librerías (numpy, pandas, matplotlib, seaborn)
2. **Dataset sintético de SST** de la Plataforma Continental Argentina — similar a datos reales de Copernicus
3. **Visualización de SST** media anual, gradientes latitudinales, ciclo estacional
4. **Clorofila-a**: relación con productividad y distribución de recursos
5. **Datos AIS simulados**: trayectoria de un barco, clasificación de actividad por velocidad
6. **Registros de captura**: análisis de partes de pesca, correlación captura-temperatura
7. **Integración**: cruce de variables ambientales con datos de captura
8. **Código comentado** para acceder a datos reales (Copernicus, NOAA, GFW)

El notebook es ejecutable en Google Colab sin instalación de software.

---

## Referencias

- Copernicus Marine Service (2024). *Product User Manual — Global Sea Physical Analysis and Forecast*. CMEMS.
- NOAA CoastWatch. (2023). *Satellite Oceanography and Remote Sensing Tools*. NOAA.
- Global Fishing Watch. (2023). *Data Documentation and API Reference*. GFW.
- Simmonds, J., & MacLennan, D. (2005). *Fisheries Acoustics: Theory and Practice* (2nd ed.). Blackwell.
- Kroodsma, D. A., et al. (2018). Tracking the global footprint of fisheries. *Science*, 359(6378), 904–908.
- INIDEP. (2023). *Informe de estado de los principales recursos pesqueros 2022*. Mar del Plata.

---

## Para explorar más

- **Copernicus Marine Service:** [marine.copernicus.eu](https://marine.copernicus.eu) — portal de datos y tutoriales
- **NOAA ERDDAP:** [coastwatch.pfeg.noaa.gov/erddap](https://coastwatch.pfeg.noaa.gov/erddap) — datos sin registro
- **Global Fishing Watch Map:** [globalfishingwatch.org/map](https://globalfishingwatch.org/map) — tráfico global de barcos en tiempo real
- **NASA Earthdata:** [earthdata.nasa.gov](https://earthdata.nasa.gov) — imágenes MODIS, VIIRS y más
- **Repo de Ariel — Modelo hidrodinámico:** [github.com/arielgiamportone/Hydrodinamic_model_Aquaculture_nets](https://github.com/arielgiamportone/Hydrodinamic_model_Aquaculture_nets)
- **xarray tutorial:** [tutorial.xarray.dev](https://tutorial.xarray.dev) — para trabajar con NetCDF en Python
