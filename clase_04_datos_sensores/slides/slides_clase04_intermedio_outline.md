# Outline de Slides — Clase 4 · 🟡 Nivel INTERMEDIO
## Datos y Sensores del Dominio Pesquero

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera | UTN FRCh · PesquerosEnIA
**Docentes:** Ariel Giamportone · Soraya Corvalán | **Duración:** 2 horas | ~20 slides

---

### Slide 1 — Portada
**Título:** Datos y Sensores del Dominio Pesquero
**Subtítulo:** Clase 4 — De la señal del sensor al insight para la pesca
*Nota: Abrir con pregunta: "¿Qué datos generó su barco/planta ayer?"*

---

### Slide 2 — Agenda
- El ecosistema de datos de un barco pesquero
- Variables oceanográficas clave: SST, clorofila, corrientes
- AIS y VMS: el rastro digital de la flota
- Plataformas de datos abiertos: INIDEP, Copernicus, GFW, NOAA
- Formatos de datos: CSV, NetCDF, Shapefile
- Notebook práctico: exploración de datos oceanográficos de la PCA

---

### Slide 3 — ¿Qué datos genera un barco pesquero en un día?

**Título:** Un arrastrero genera datos 24/7 — ¿cuántos explotamos?

**Tabla visual:**
| Sensor/Sistema | Dato | Frecuencia |
|----------------|------|-----------|
| GPS | Posición (lat/lon) | Continua |
| AIS | Posición + velocidad + identidad | Cada 2-10 s |
| VMS | Posición satelital | Cada 30 min |
| Ecosonda | Profundidad + cardúmenes | Continua |
| Sensor SST | Temperatura del agua | Cada pocos min |
| Sensor bodega | Temperatura de carga | Continua |
| Balanza | Peso captura por lance | Por lance |
| Parte de pesca | Especie, kg, zona, hora | Por lance |

*Nota: Hacer notar que un barco de altura genera decenas de miles de registros por viaje. La mayoría no se analizan.*

---

### Slide 4 — Los datos externos que también importan

**Título:** El contexto ambiental: datos que no vienen del barco pero son críticos

- 🛰️ **Imágenes satelitales:** SST, clorofila-a, nivel del mar (cada 1-3 días, gratis)
- 🌊 **Modelos oceanográficos:** corrientes, temperatura subsuperficial, salinidad
- 🌬️ **Meteorología:** viento, altura de ola, visibilidad (seguridad + eficiencia)
- 📋 **Regulatorios:** cuotas por especie, áreas de veda, límites de ZEE
- 🐟 **Biológicos (INIDEP):** índices de abundancia, datos de campañas de evaluación

*Nota: La predicción de zonas de pesca (Clase 6) integra exactamente estos datos externos con el historial de capturas del barco.*

---

### Slide 5 — Temperatura Superficial del Mar (SST)

**Título:** La SST — el termómetro que guía la pesca

**Mapa visual:** Plataforma Continental Argentina con isotermas (Corriente de Malvinas vs. Brasil)

- Cada especie tiene su rango térmico preferencial
- Merluza: **4–12°C** | Calamar: **8–16°C** | Langostino: **6–14°C**
- Los **frentes oceánicos** (mezcla Malvinas-Brasil) = alta productividad
- Resolución disponible: hasta ~1 km por día (satélites MODIS, Sentinel)

**Fuentes:** Copernicus Marine Service · NOAA CoastWatch · NASA Earthdata (todas gratuitas)

*Nota: Mostrar imagen de SST real del Mar Argentino (disponible en Copernicus sin registro).*

---

### Slide 6 — Clorofila-a: productividad del mar

**Título:** Verde en el mar = alimento para los peces

- Clorofila-a = fitoplancton = base de la cadena trófica marina
- Alta clorofila → zooplancton → anchoíta/juveniles → merluza/calamar
- **Floración de primavera** (sep-nov): explosión de productividad en los golfos patagónicos
- Rango en la PCA: 0.1 – 30 mg/m³

**Combinación poderosa:**
SST óptima + alta clorofila = zona de alta probabilidad de captura

*Nota: Mostrar imagen satelital de clorofila del Mar Argentino en primavera. El verde intenso en el golfo San Jorge es espectacular.*

---

### Slide 7 — Corrientes oceánicas de la PCA

**Título:** Malvinas vs. Brasil — el gran motor de la productividad pesquera argentina

**Diagrama:**
```
Brasil (cálida, ~22°C)  →→→
                              ↕ FRENTE (alta productividad)
Malvinas (fría, ~6°C)  ←←←
```

- **Corriente de Malvinas:** fría, nutrientes, fluye al norte por el talud
- **Corriente de Brasil:** cálida, pobre en nutrientes, fluye al sur
- **Frente de confluencia:** ~38-40°S — zona de máxima diversidad y captura
- El frente varía estacionalmente → cambia la distribución de recursos

*Nota: Este es el "corazón oceanográfico" de la pesquería argentina. Los modelos de ML van a aprender estos patrones.*

---

### Slide 8 — AIS: el pasaporte digital del barco

**Título:** AIS — cada barco tiene una huella en el mar

**Tabla de ejemplo de mensaje AIS:**
```
MMSI:     701234567
Nombre:   BP PATAGÓNICO
Lat:      -43.582°
Lon:      -60.213°
SOG:      3.2 kn     ← velocidad lenta → probablemente pescando
COG:      278°
Tipo:     Buque pesquero (código 30)
Timestamp: 2026-01-15 03:42:17 UTC
```

- MMSI: identificador único de 9 dígitos (Argentina: comienza con 701)
- SOG < 4 kn = probablemente en actividad de pesca
- SOG > 8 kn = navegando hacia zona o de regreso a puerto

*Nota: Global Fishing Watch clasifica el tipo de actividad de ~70.000 barcos con esta lógica (+ ML).*

---

### Slide 9 — VMS: el sistema de control argentino

**Título:** VMS — el sistema obligatorio para la flota argentina

- Obligatorio para buques ≥28 m de eslora
- Satélite Inmarsat C
- Transmisión cada 30-60 minutos
- Gestionado por la Subsecretaría de Pesca y Acuicultura
- Datos **no públicos** (a diferencia del AIS) — son información regulatoria
- Verificación de cumplimiento: áreas de veda, límites de ZEE, horarios de veda

**AIS vs VMS:**
| Aspecto | AIS | VMS |
|---------|-----|-----|
| Obligatoriedad | Buques ≥300 GT | Buques pesqueros ≥28 m |
| Datos | Públicos | Reservados |
| Frecuencia | 2-10 s | 30-60 min |
| Propósito | Seguridad náutica | Control regulatorio |

---

### Slide 10 — Global Fishing Watch

**Título:** Ver el mar como nunca antes

- Monitorea ~70.000 barcos en tiempo real
- 50 TB de datos AIS procesados por día con modelos de ML
- Clasifica: pesca · navegación · transbordo · buques oscuros
- Precisión >95% en clasificación de actividad pesquera
- Datos descargables para investigación (registro gratuito)
- Detecta pesca ilegal en zonas protegidas y vedas

**Para Argentina:** permite ver la actividad de flota extranjera en los límites de la ZEE y el esfuerzo pesquero histórico por zona.

*Nota: Mostrar el mapa en vivo si hay conexión: globalfishingwatch.org/map — seleccionar el Mar Argentino.*

---

### Slide 11 — Plataformas de datos abiertos

**Título:** El sector tiene más datos gratuitos de los que imaginamos

| Plataforma | Qué tiene | Acceso |
|-----------|---------|--------|
| **Copernicus Marine** | SST, clorofila, corrientes, nivel del mar | Registro gratuito |
| **NOAA ERDDAP** | SST, anomalías, temp. subsuperficial | Sin registro |
| **INIDEP** | Capturas ARG, evaluaciones de stock | Web pública |
| **Global Fishing Watch** | AIS, esfuerzo pesquero, rutas | Registro gratuito |
| **NASA Earthdata** | MODIS, VIIRS, datos de satélite | Registro gratuito |
| **GEBCO** | Batimetría global | Sin registro |

*Nota: Todos son gratuitos. El obstáculo no es el acceso a los datos — es saber cómo procesarlos.*

---

### Slide 12 — Formatos de datos: ¿qué vamos a encontrar?

**Título:** CSV, NetCDF, GeoJSON — el lenguaje de los datos oceánicos

| Formato | Descripción | Cuándo aparece |
|---------|-------------|----------------|
| CSV/Excel | Tabular, filas y columnas | Partes de pesca, producción planta |
| NetCDF (.nc) | Cubo 3D: lat × lon × tiempo | SST, clorofila, corrientes satelitales |
| GeoTIFF (.tif) | Imagen georreferenciada | SAR, imágenes satelitales |
| Shapefile (.shp) | Vectores geográficos | Áreas de veda, límites ZEE, costas |
| JSON/GeoJSON | Texto estructurado | APIs de GFW, NOAA; datos AIS |

**El NetCDF en detalle:**
- Dimensiones: latitud (500), longitud (400), tiempo (365) → ~73 millones de valores por año
- Una variable: `sst[tiempo, lat, lon]` en °C
- Python: `import xarray as xr; ds = xr.open_dataset("archivo.nc")`

---

### Slide 13 — Transición al notebook

**Título:** Ahora vamos a hacerlo nosotros

**Notebook:** `clase04_exploracion_datos_oceanograficos.ipynb`
**Ejecutar en:** Google Colab (sin instalación)
**Link:** github.com/PesquerosEnIA/curso-ia-produccion-pesquera

**Lo que vamos a hacer:**
1. Generar un dataset de SST realista de la PCA (lat -55° a -34°, lon -65° a -44°)
2. Visualizar SST media anual y variación estacional
3. Analizar clorofila-a y frentes productivos
4. Explorar datos AIS simulados de un barco pesquero
5. Cruzar datos de captura con variables ambientales

*Nota: Abrir el notebook en Colab, ejecutar la primera celda juntos. Los participantes siguen desde sus dispositivos.*

---

### Slide 14 — SST de la PCA: lo que vamos a ver

**Título:** La Plataforma Continental Argentina desde el satélite

*(Placeholder para imagen generada por el notebook — mapa de SST media anual)*

- Gradiente latitudinal claro: norte ~18°C → sur ~5°C
- Zona de frente (mezcla Malvinas-Brasil) visible en ~40°S
- Baja SST en invierno austral (jun-ago) → calamar migra al norte
- Alta SST en verano → langostino se activa en los golfos

---

### Slide 15 — Datos AIS: velocidad como proxy de actividad

**Título:** ¿Cómo saber si un barco está pescando sin verlo?

*(Placeholder para gráfico del notebook — trayectoria del barco + velocidad)*

**Regla empírica para arrastrero:**
- Velocidad < 4 kn → probable arrastre (pescando)
- Velocidad 4-7 kn → transitando entre lances
- Velocidad > 7 kn → navegación de ida/vuelta a puerto

Este criterio es la base del algoritmo de detección de pesca de Global Fishing Watch (con mejoras adicionales de ML).

---

### Slide 16 — Captura vs SST: el patrón que buscamos

**Título:** ¿A qué temperatura pesca más la merluza?

*(Placeholder para scatter plot del notebook — SST vs toneladas de captura)*

- El scatter muestra una relación no lineal
- Pico de captura en el rango 8–12°C → consistente con biología de merluza hubbsi
- Por debajo de 5°C o encima de 14°C → capturas significativamente menores
- Esta relación es la que el modelo de ML de la Clase 6 va a aprender

*Nota: Conectar explícitamente lo de hoy (exploración) con la Clase 6 (modelado). Los datos explorados hoy serán los predictores del modelo de mañana.*

---

### Slide 17 — Síntesis: el flujo de trabajo con datos pesqueros

**Título:** De los datos crudos al insight — el workflow

```
Fuente de datos       Acceso          Procesamiento      Análisis
─────────────────────────────────────────────────────────────────
Copernicus (SST)   →  API Python  →  xarray/pandas   →  EDA + viz
NOAA (batimetría)  →  ERDDAP      →  pandas          →  correlación
Partes de pesca    →  CSV         →  pandas          →  patrones
AIS/VMS            →  GFW API     →  geopandas       →  actividad
```

- Todos los pasos son realizables en Python + Jupyter (ya lo hicimos hoy)
- El workflow completo está en el notebook que pueden llevar a su trabajo

---

### Slide 18 — Cierre y próxima clase

**Título:** Lo que aprendimos + lo que viene

**Hoy:**
- El sector pesquero tiene un ecosistema rico de datos (sensores, satélites, capturas)
- Las variables ambientales (SST, clorofila, corrientes) explican la distribución de recursos
- AIS y VMS son el rastro digital de la flota
- Copernicus, NOAA, GFW e INIDEP proveen datos gratuitos y accesibles
- Exploramos datos oceanográficos reales en Python

**Próxima clase (5) — Arquitectura de Datos y Big Data en Pesca:**
Docente: Damian Adolfo Giacone
Cómo integrar, almacenar y procesar grandes volúmenes de datos del sector.

**Materiales disponibles:**
`github.com/PesquerosEnIA/curso-ia-produccion-pesquera`
