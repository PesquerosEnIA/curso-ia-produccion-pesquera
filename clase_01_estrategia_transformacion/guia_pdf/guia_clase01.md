# Clase 1 — Estrategia y Transformación Digital en el Sector Pesquero

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN Facultad Regional Chubut | PesquerosEnIA
**Docentes:** Ariel Giamportone · Soraya Corvalán
**Duración:** 2 horas
**Modalidad:** Semipresencial / Virtual

---

## Objetivos de la clase

Al finalizar esta clase, el participante será capaz de:

1. Describir el estado actual de la transformación digital en el sector pesquero global y argentino.
2. Comprender el concepto de *Smart Fisheries* y sus componentes tecnológicos.
3. Identificar al menos cinco casos de uso concretos de IA en barcos, monitoreo marino y plantas pesqueras.
4. Reconocer las principales barreras y oportunidades para la adopción tecnológica en el sector pesquero patagónico.

---

## 1. El sector pesquero argentino en cifras

Argentina posee una de las plataformas continentales más extensas del mundo. La Zona Económica Exclusiva (ZEE) abarca aproximadamente **1.000.000 km²** de Mar Argentino, con una profundidad media de 200 metros que favorece ecosistemas altamente productivos.

### Datos clave del sector (2023)

| Indicador | Valor |
|-----------|-------|
| Exportaciones pesqueras | ~USD 2.100 millones/año |
| Capturas totales | ~800.000–900.000 toneladas/año |
| Empleo directo | ~25.000 trabajadores embarcados |
| Empleo en tierra (plantas) | ~35.000 puestos |
| Buques habilitados (pesca costera y altura) | ~600 |
| Principales puertos | Puerto Madryn, Mar del Plata, Rawson, Ushuaia, Comodoro Rivadavia |

Las principales especies de exportación son:
- **Merluza hubbsi** (*Merluccius hubbsi*): ~40% del volumen total
- **Calamar illex** (*Illex argentinus*): ~30% del volumen total
- **Langostino patagónico** (*Pleoticus muelleri*): alto valor unitario
- **Vieira patagónica** (*Zygochlamys patagonica*): creciente relevancia

El sector contribuye con el **~3% de las divisas nacionales** y es estratégico para la economía patagónica, donde representa entre el 15 y el 40% del producto bruto provincial en Chubut, Santa Cruz y Tierra del Fuego.

> **Reflexión:** Con este volumen de capturas y exportaciones, una mejora del 5% en eficiencia operativa vía IA representaría más de USD 100 millones anuales en valor agregado.

---

## 2. La Cuarta Revolución Industrial y el sector pesquero

### ¿Qué es la Industria 4.0?

La Industria 4.0 —también llamada Cuarta Revolución Industrial— describe la integración digital de los procesos productivos mediante:

- **IoT (Internet of Things):** sensores conectados que capturan datos en tiempo real
- **Big Data & Analytics:** procesamiento masivo de datos para identificar patrones
- **Inteligencia Artificial:** algoritmos que aprenden de datos y toman decisiones
- **Automatización y robótica:** sistemas autónomos que reducen intervención humana
- **Conectividad:** redes de comunicación que permiten flujo de datos continuo

### ¿Cómo llega la Industria 4.0 al mar?

El sector pesquero tiene características únicas que hacen que la adopción tecnológica sea tanto más desafiante como más valiosa:

| Característica del sector | Desafío tecnológico | Oportunidad IA |
|--------------------------|--------------------|--------------------|
| Recurso biológico variable | Incertidumbre en captura | Predicción de zonas y abundancia |
| Ambiente hostil (mar abierto) | Robustez de sensores | Monitoreo remoto satelital |
| Cadena fría crítica | Trazabilidad compleja | Blockchain + sensores temperatura |
| Regulación estricta | Reporte y cumplimiento | Automatización de partes de pesca |
| Alta variabilidad de precios | Planificación difícil | Modelos predictivos de mercado |

### Comparación con otras industrias primarias

Argentina tiene una experiencia exitosa en digitalización del agro (*precision farming*, drones, datos satelitales para soja y maíz) y la minería. El sector pesquero puede aprender de esas trayectorias, adaptando soluciones al ambiente marino.

---

## 3. Smart Fisheries: pesquerías inteligentes

### Definición

Una **Smart Fishery** (*pesquería inteligente*) integra datos, conectividad, sensores y algoritmos de decisión para optimizar simultáneamente:
- La **eficiencia operativa** del barco y la planta
- La **sostenibilidad** del recurso pesquero
- La **trazabilidad** del producto desde el mar hasta el consumidor
- El **cumplimiento regulatorio** con menor carga administrativa

### Los cuatro pilares de una Smart Fishery

```
Datos ────────► Análisis ────────► Decisión ────────► Acción
  │                 │                   │                │
Sensores a      Algoritmos         IA sugiere        Capitán,
bordo, AIS,     ML/IA, dashboards  ruta, zona,       planta,
imágenes sat.,  tiempo real        velocidad,        regulador
partes pesca                       parada de pesca   actúan
```

### Casos globales líderes

**Noruega:** líder mundial en digitalización pesquera. Los barcos noruegos transmiten datos en tiempo real de capturas, calidad de agua y consumo de combustible. La empresa **Kongsberg Maritime** desarrolla sistemas de gestión de flota basados en IA.

**Islandia:** el 90% de la flota transmite datos de captura en tiempo real al gobierno. El sistema **Rafrænt fiskvog** (balanza digital) elimina el fraude en reportes de captura.

**Chile:** uso creciente de imágenes satelitales para monitoreo de acuicultura (salmón) y detección de flotas extranjeras no autorizadas en la ZEE.

**Global Fishing Watch:** plataforma open-access que monitorea ~60.000 barcos en tiempo real usando AIS, modelos de ML para detección de pesca ilegal y análisis de esfuerzo pesquero por especie y zona.

---

## 4. Casos de uso de IA en el sector pesquero

### 4.1. Predicción de zonas de pesca

Los modelos de ML pueden predecir dónde es más probable encontrar cardúmenes en función de:
- Temperatura superficial del mar (SST)
- Concentración de clorofila-a (productividad)
- Batimetría y gradientes de profundidad
- Corrientes oceánicas (Malvinas, frente patagónico)
- Datos históricos de captura por zona y temporada

**Impacto:** reducción del 20-30% en días de búsqueda improductiva, con la consiguiente reducción de combustible y aumento de rendimiento por marea.

### 4.2. Monitoreo satelital y sistemas AIS/VMS

- **AIS (Automatic Identification System):** transponder obligatorio en barcos >300 GT que transmite posición, velocidad y rumbo cada pocos segundos
- **VMS (Vessel Monitoring System):** sistema de monitoreo satelital obligatorio para buques pesqueros argentinos, gestionado por la Subsecretaría de Pesca
- **Imágenes SAR:** radar de apertura sintética para detectar barcos que apagan el AIS (*dark vessels*)

Global Fishing Watch procesa ~50 TB de datos AIS diarios con modelos de ML para clasificar el tipo de actividad (pesca, navegación, transbordo) con >95% de precisión.

### 4.3. Control de calidad en planta por visión artificial

Las plantas procesadoras generan miles de decisiones de clasificación por hora:
- Clasificación por especie (merluza vs. polaca vs. castañeta)
- Medición de talla individual (reemplaza medición manual)
- Detección de parásitos o defectos en filetes
- Evaluación de frescura por color y textura

Sistemas como **Marel**, **Baader** o **TriVision** usan cámaras de alta velocidad con modelos de visión artificial para procesar >100 peces/minuto con mayor consistencia que la inspección humana.

### 4.4. Trazabilidad digital del producto

Desde el anzuelo hasta el supermercado. La cadena de valor pesquera involucra:
barco → puerto → cámara frigorífica → planta procesadora → exportador → importador → consumidor final

Cada paso puede registrarse digitalmente. El estándar **GS1** y tecnologías blockchain permiten que un consumidor en Europa pueda escanear un código QR y ver exactamente en qué barco, en qué zona y en qué fecha fue capturado su filete de merluza.

**En Argentina:** la Subsecretaría de Pesca está avanzando en el Sistema de Trazabilidad Pesquera (SiTP) para los productos de exportación.

### 4.5. Optimización de flota y logística portuaria

- **Rutas optimizadas:** reducción del 10-20% de consumo de gasoil aplicando algoritmos de optimización que consideran corrientes, vientos y zonas de pesca
- **Mantenimiento predictivo:** sensores en motores detectan anomalías antes de averías costosas
- **Planificación de desembarco:** coordinación de llegada de barcos con disponibilidad de muelle, frigorífico y planta
- **Gestión de tripulación:** planificación de rotaciones y certificaciones con menor carga administrativa

---

## 5. El sector pesquero argentino ante la transformación digital

### La brecha tecnológica

A pesar del potencial, el sector pesquero argentino presenta una adopción tecnológica más lenta que otras industrias primarias. Las principales barreras identificadas son:

| Barrera | Descripción |
|---------|-------------|
| **Formación** | Falta de profesionales con competencias en datos e IA dentro del sector |
| **Conectividad** | Cobertura limitada de internet satelital en zonas de pesca alejadas |
| **Inversión** | Alto costo percibido de tecnología para empresas medianas y pequeñas |
| **Idioma** | Escasez de materiales técnicos de calidad en español y adaptados al sector |
| **Cultura** | Resistencia al cambio en industria con lógicas operativas consolidadas |
| **Regulación** | Marco regulatorio que no siempre acompaña la velocidad de la innovación |

### Señales positivas

A pesar de las barreras, hay señales claras de cambio:
- El gobierno argentino impulsa el programa **Pampa Azul** con foco en economía del conocimiento marina
- Empresas líderes (Pesquera Austral, Argen, Newsan) están incorporando tecnología de trazabilidad
- La conectividad satelital (Starlink, OneWeb) está llegando a los barcos a costos decrecientes
- INIDEP dispone de datos históricos de gran valor que aún no están plenamente explotados
- Iniciativas como **PesquerosEnIA** demuestran que hay demanda de capacitación específica

### El rol de este curso

Este curso nace de la experiencia directa con la brecha tecnológica del sector. No enseñamos IA genérica: enseñamos IA **con datos pesqueros, para problemas pesqueros, en español y desde el propio sector**.

---

## 6. Antecedentes: PesquerosEnIA y CONIPE

### I Congreso Nacional de Ingeniería Pesquera (CONIPE 2019)

En noviembre de 2019, en la UTN FRCh, se realizó el **I Congreso Nacional de Ingeniería Pesquera (CONIPE 2019)**. En ese marco, el equipo docente de este curso dictó el minicurso **"Industria 4.0: ¿es posible?"** (8 horas) y coordinó la mesa redonda **"Industria 4.0 en el sector pesquero"**.

Ese evento fue uno de los primeros antecedentes sistemáticos de formación en transformación digital específicamente para profesionales del sector pesquero argentino.

### CONIPE 2025 — Puerto Madryn

En el CONIPE 2025, la comunidad PesquerosEnIA impartió el curso **"Alfabetización en Ciencia de Datos e Inteligencia Artificial para Profesionales del Sector Pesquero y Acuícola"** (8 módulos), validando la demanda y ajustando los contenidos a las necesidades reales del sector.

### La comunidad PesquerosEnIA

**PesquerosEnIA** es una comunidad abierta fundada para conectar a los profesionales del sector pesquero con las herramientas de IA y ciencia de datos. Sus principios:
- Contenido en español, contextualizado al sector
- Acceso abierto (GPL-3.0)
- Colaboración entre pares (investigadores, ingenieros, técnicos, operadores)
- GitHub como plataforma de colaboración y distribución de materiales

Repositorio: [github.com/PesquerosEnIA](https://github.com/PesquerosEnIA)

---

## Actividad práctica

### Mapeo de oportunidades de IA en tu contexto

**Duración:** 20 minutos (individual + puesta en común)

**Instrucción:**

1. Pensá en tu rol actual o más reciente en el sector pesquero (barco, planta, organismo regulador, investigación, consultoría, etc.).
2. Identificá **un problema concreto** que enfrentás o que observás frecuentemente en tu ámbito de trabajo.
3. Completá la siguiente ficha:

| Campo | Tu respuesta |
|-------|-------------|
| Mi rol en el sector | |
| El problema que identifico | |
| ¿Qué datos existen o podrían existir sobre este problema? | |
| ¿Qué tipo de IA podría ayudar? (predicción / clasificación / optimización / automatización) | |
| ¿Cuál sería el beneficio esperado? | |

4. Compartí tu caso en el grupo. El docente guiará la discusión para identificar patrones comunes y prioridades del sector.

> **Nota del docente:** Esta actividad tiene doble propósito: romper el hielo y construir el mapa de necesidades reales del grupo, que guiará los ejemplos de las clases siguientes.

---

## Referencias bibliográficas

- FAO. (2022). *The State of World Fisheries and Aquaculture 2022*. Food and Agriculture Organization of the United Nations.
- FAO. (2024). *Digital Technologies and Innovation in Fisheries and Aquaculture*. FAO Technical Paper.
- Kroodsma, D. A., et al. (2018). Tracking the global footprint of fisheries. *Science*, 359(6378), 904–908.
- CEPAL. (2021). *Tecnologías digitales para la transformación productiva en América Latina*. CEPAL/OCDE.
- Subsecretaría de Pesca y Acuicultura. (2023). *Informe de gestión y estadísticas pesqueras*. Ministerio de Economía, Argentina.
- Global Fishing Watch. (2023). *Annual Report on Global Fishing Activity*. GFW.

---

## Para explorar más

- **Global Fishing Watch — Mapa interactivo:** [globalfishingwatch.org/map](https://globalfishingwatch.org/map) — explorá el tráfico de barcos pesqueros en tiempo real en el Mar Argentino
- **Copernicus Marine Service:** [marine.copernicus.eu](https://marine.copernicus.eu) — datos oceanográficos abiertos de toda la plataforma continental
- **INIDEP:** [inidep.edu.ar](https://www.inidep.edu.ar) — datos de capturas, evaluaciones de stock y monitoreo del Atlántico Sur
- **PesquerosEnIA — GitHub:** [github.com/PesquerosEnIA](https://github.com/PesquerosEnIA) — material del curso y notebooks en acceso abierto
- **FAO FishFinder:** [fao.org/fishery/en/fishfinder](https://www.fao.org/fishery/en/fishfinder) — base de datos de especies, pesquerías y regulaciones globales
- **Paper seminal:** Kroodsma et al. (2018) en *Science* — disponible en [globalfishingwatch.org/research](https://globalfishingwatch.org/research)
