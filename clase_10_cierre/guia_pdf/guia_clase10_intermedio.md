# Clase 10 — Cierre, Conclusiones y Hoja de Ruta
## 🟡 Nivel INTERMEDIO

> Síntesis completa, matriz de viabilidad y hoja de ruta por perfil. *(Existen variantes 🟢 Novato y 🔴 Avanzado.)*

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN Facultad Regional Chubut | PesquerosEnIA
**Docentes:** Soraya Corvalán · Ariel Giamportone
**Duración:** 2 horas
**Modalidad:** Semipresencial / Virtual

---

## Objetivos de la clase

1. Integrar y sintetizar los contenidos del curso en un marco conceptual coherente.
2. Evaluar el potencial real de implementación de IA en el contexto de cada participante.
3. Construir una hoja de ruta personal para continuar el aprendizaje después del curso.
4. Reflexionar sobre el uso ético y sostenible de la IA en el sector pesquero.
5. Presentar y recibir retroalimentación sobre el proyecto integrador.

---

## 1. Síntesis del recorrido: de los datos a las decisiones

### El hilo conductor del curso

A lo largo de 23 horas recorrimos un camino que tiene una lógica interna clara:

```
DATOS → COMPRENSIÓN → MODELOS → DECISIONES → IMPACTO
  │           │           │           │           │
Clase 4    Clase 1     Clase 6     Clase 8     Clase 10
Sensors    Estrategia  ML          Optimiz.    Cierre
```

Cada clase construyó sobre la anterior:

| Bloque | Clases | Lo que aprendimos |
|--------|--------|------------------|
| **Contexto y estrategia** | 1 | Por qué la IA importa para el sector pesquero y cómo pensar estratégicamente su adopción |
| **Herramientas de lenguaje** | 2, 3 | LLMs y prompting para automatizar tareas cognitivas: informes, análisis, cumplimiento |
| **Datos del dominio** | 4, 5 | De dónde vienen los datos pesqueros, cómo estructurarlos y acceder a ellos |
| **Modelos predictivos** | 6 | Cómo construir modelos de ML para predecir zonas de pesca y patrones de captura |
| **Percepción e imagen** | 7 | Cómo la visión artificial automatiza la clasificación en planta |
| **Optimización** | 8 | Cómo reducir costos operativos de flota con algoritmos de optimización |
| **Visualización** | 9 | Cómo convertir datos en dashboards que apoyen decisiones |
| **Cierre** | 10 | Dónde seguir, cómo aplicarlo, cómo contribuir |

### La cadena de valor del dato pesquero

Un dato que empieza como coordenada GPS de un barco a las 3 AM en el Mar Argentino puede convertirse, con las herramientas correctas, en:
- Un **mapa de distribución de esfuerzo pesquero** que informa la política de cuotas
- Un **modelo predictivo de captura** que guía la decisión del capitán
- Un **reporte automático de cumplimiento** para la Subsecretaría de Pesca
- Un **indicador de sostenibilidad** para la certificación MSC de la empresa

Eso es el poder de la cadena datos → IA → decisiones.

---

## 2. Impacto potencial en el sector pesquero argentino

### ¿Qué es viable implementar hoy?

No todas las aplicaciones de IA tienen la misma madurez tecnológica ni el mismo costo de implementación. Esta matriz ayuda a priorizar:

| Aplicación | Madurez tecnológica | Costo de implementación | Impacto potencial | Recomendación |
|-----------|--------------------|-----------------------|------------------|---------------|
| Predicción de zonas de pesca | Alta | Bajo (datos abiertos + Python) | Alto | **Implementar ahora** |
| Asistentes IA para reportes (LLMs) | Alta | Muy bajo | Medio-Alto | **Implementar ahora** |
| Dashboards de toma de decisiones | Alta | Bajo | Alto | **Implementar ahora** |
| Monitoreo AIS y análisis de flota | Alta | Bajo | Alto | **Implementar ahora** |
| Optimización de rutas de flota | Media-Alta | Medio | Alto | **Implementar en 6-12 meses** |
| Visión artificial en planta | Alta | Alto (hardware) | Muy Alto | **Proyecto piloto** |
| Trazabilidad blockchain | Media | Alto | Medio-Alto | **Mediano plazo** |
| Mantenimiento predictivo de motores | Media | Medio | Alto | **Mediano plazo** |

### El principio de la fruta baja

Antes de invertir en infraestructura costosa, hay un conjunto de aplicaciones de alto impacto y bajo costo que pueden implementarse con las herramientas que ya tienen:

1. **Un analista con Python + datos de INIDEP/Copernicus** puede construir un modelo predictivo de zonas de pesca en semanas
2. **Un asistente IA con prompting bien diseñado** puede reducir el tiempo de redacción de reportes técnicos un 60-70%
3. **Un dashboard en Power BI** conectado a los datos de producción existentes puede transformar la toma de decisiones gerenciales
4. **Un análisis de patrones AIS** puede identificar ineficiencias en la operación de la flota sin invertir en un solo sensor nuevo

---

## 3. Hoja de ruta personal: continuar aprendiendo

### Rutas según perfil

**Perfil técnico-operativo (capitán, técnico de planta, supervisor de producción):**

*Prioridad 1 — Herramientas inmediatas:*
- ChatGPT / Claude para asistencia en reportes y comunicación técnica
- Excel avanzado → Power BI para visualización de datos de producción
- Python básico: pandas + matplotlib para análisis de datos de captura

*Prioridad 2 — En 3-6 meses:*
- Notebooks Jupyter: explorar datos oceanográficos de Copernicus
- Modelos de ML simples con scikit-learn
- Global Fishing Watch: monitoreo de actividad de flota

**Perfil científico-académico (investigador, docente, biólogo, ingeniero):**

*Prioridad 1 — Profundización inmediata:*
- Python científico: NumPy, pandas, matplotlib, scikit-learn
- Datos abiertos: Copernicus Marine, NOAA ERDDAP, INIDEP
- Machine Learning aplicado: regresión, clasificación, clustering en datasets pesqueros

*Prioridad 2 — En 3-6 meses:*
- Deep Learning: redes neuronales para clasificación de imágenes (torcha, TensorFlow)
- Series de tiempo: predicción de capturas y variables oceanográficas
- R para estadística pesquera avanzada (paquetes `RMBC`, `ktaucenters`)

**Perfil gestor/regulador (organismo público, gerencia de empresa):**

*Prioridad 1:*
- Visualización y dashboards (Power BI, Tableau)
- Fundamentos de IA para decisores (sin programación)
- Casos de aplicación en regulación pesquera

*Prioridad 2:*
- Gestión de proyectos de transformación digital
- Evaluación de soluciones IA para el sector

### Recursos gratuitos recomendados

| Recurso | Nivel | Idioma | URL |
|---------|-------|--------|-----|
| PesquerosEnIA GitHub | Básico-Avanzado | Español | github.com/PesquerosEnIA |
| Google Colab | Básico | Español (interfaz) | colab.research.google.com |
| Kaggle Learn — Python/ML | Básico-Medio | Inglés | kaggle.com/learn |
| fast.ai | Medio-Avanzado | Inglés | fast.ai |
| Copernicus Marine Academy | Medio | Inglés | marine.copernicus.eu/services/training |
| GFW Research Papers | Avanzado | Inglés | globalfishingwatch.org/research |
| Ciencia de Datos para Pesquerías (FAO) | Medio | Inglés | fao.org |

---

## 4. La comunidad PesquerosEnIA

### Misión y principios

PesquerosEnIA es una comunidad abierta con una misión clara: **construir el puente entre el sector pesquero argentino y la inteligencia artificial**, produciendo materiales en español, contextualizados al dominio, y disponibles para todos.

**Principios:**
- Acceso abierto: todo bajo licencia GPL-3.0
- En español: sin barreras de idioma
- Desde el sector: los materiales los hacen profesionales del sector, no solo del mundo de la IA
- Colaboración horizontal: todos pueden contribuir

### Recursos disponibles

- **curso_alfabetizacion_CONIPE25:** 8 módulos de alfabetización en ciencia de datos para el sector
- **ML_DL_FisheriesEngineers:** compendio de notebooks ML/DL con aplicaciones pesqueras
- **curso-ia-produccion-pesquera (este curso):** todos los materiales de estas 23 horas

### Cómo contribuir

1. **Abrir un Issue** en GitHub si encontrás un error o tenés una sugerencia
2. **Hacer un Fork** del repo y proponer mejoras (Pull Request)
3. **Compartir los materiales** con colegas del sector
4. **Participar en eventos** futuros (CONIPE, webinars, talleres)
5. **Proponer nuevos casos de uso** de tu experiencia concreta en el sector

### Contacto y próximos pasos

- GitHub: [github.com/PesquerosEnIA](https://github.com/PesquerosEnIA)
- Próximos eventos: seguir el repositorio para anuncios

---

## 5. Proyecto integrador: presentación y retroalimentación

### La consigna del proyecto

A lo largo del curso, cada participante fue construyendo (formalmente o informalmente) la comprensión de un problema concreto en su sector donde la IA puede aportar valor.

El **proyecto integrador** consiste en presentar ese caso de uso con la siguiente estructura (5-7 minutos por presentación):

1. **El problema:** ¿qué ineficiencia, riesgo o desafío identificás en tu contexto?
2. **Los datos:** ¿qué datos existen o podrían recolectarse?
3. **La solución IA propuesta:** ¿qué tipo de modelo o herramienta aplicarías?
4. **El impacto esperado:** ¿qué mejora concreta generaría?
5. **Las barreras:** ¿qué obstáculos anticipás para implementarlo?

### Criterios de evaluación

| Criterio | Descripción | Peso |
|----------|-------------|------|
| Relevancia del problema | ¿Es un problema real y significativo del sector? | 25% |
| Factibilidad técnica | ¿La solución propuesta es técnicamente viable? | 25% |
| Conocimiento del dominio | ¿Demuestra comprensión del sector pesquero? | 25% |
| Claridad de presentación | ¿Se comunica claramente la idea? | 25% |

*No se requiere código ni implementación — se evalúa la comprensión conceptual y la capacidad de identificar y formular el problema.*

---

## 6. IA ética y sostenible en pesquerías

### El riesgo de la optimización sin límites

La IA puede optimizar muy eficientemente el esfuerzo pesquero. Pero optimizar sin considerar los límites biológicos del recurso puede llevar a la sobreexplotación.

**Principio fundamental:** la IA en el sector pesquero debe operar *dentro* de los límites que define la ciencia pesquera (cuotas, vedas, tallas mínimas), no *contra* ellos.

### Sesgos en modelos pesqueros

Los modelos de ML aprenden de datos históricos. Si el historial de pesca tiene sesgos (zonas sobreexplotadas, subregistro de capturas, datos de partes de pesca manipulados), el modelo aprenderá esos sesgos y los perpetuará.

**Buenas prácticas:**
- Validar los modelos con datos independientes (no solo con los de entrenamiento)
- Incluir variables biológicas en los modelos (índices de abundancia de INIDEP)
- No usar un modelo de predicción de zonas de pesca para intensificar el esfuerzo en zonas ya bajo presión

### Privacidad y datos de flota

Los datos AIS y VMS contienen información sensible sobre las operaciones de los barcos. El uso responsable implica:
- Anonimización cuando sea necesario
- No usar datos de competidores de forma desleal
- Transparencia con los marineros sobre qué se monitorea y con qué fin

### La IA como herramienta, no como reemplazo

La IA no reemplaza:
- El juicio del capitán (que sabe cosas que el modelo no puede capturar)
- La experiencia del biólogo pesquero
- La decisión del regulador
- La negociación colectiva de los trabajadores del sector

La IA amplifica las capacidades humanas. El capital humano del sector pesquero sigue siendo el recurso más valioso.

---

## Para seguir: recursos curados

### Comunidades y plataformas

- **PesquerosEnIA:** [github.com/PesquerosEnIA](https://github.com/PesquerosEnIA) — punto de partida para todo
- **Global Fishing Watch Community:** [globalfishingwatch.org](https://globalfishingwatch.org) — datos y papers sobre monitoreo global
- **Copernicus Marine Academy:** cursos gratuitos de datos oceanográficos
- **INIDEP:** [inidep.edu.ar](https://www.inidep.edu.ar) — datos y publicaciones del Atlántico Sur

### Papers fundamentales

- Kroodsma, D. A., et al. (2018). *Tracking the global footprint of fisheries*. Science, 359(6378), 904–908.
- Simmonds, J., & MacLennan, D. (2005). *Fisheries Acoustics: Theory and Practice*.
- FAO. (2024). *Digital Technologies and Innovation in Fisheries and Aquaculture*.

### Cursos complementarios (gratuitos)

- **Kaggle — Intro to Machine Learning:** [kaggle.com/learn](https://kaggle.com/learn)
- **fast.ai — Practical Deep Learning for Coders:** [fast.ai](https://fast.ai)
- **Python para ciencia de datos (Google Colab):** accesible sin instalación

### Paquetes R para estadística pesquera avanzada

- `RMBC` — Clustering robusto (Dr. Juan D. González, CRAN)
- `ktaucenters` — Clustering robusto alternativo (Dr. Juan D. González, CRAN)
- `FSA` — Fisheries Stock Assessment
- `TropFishR` — Análisis de poblaciones tropicales (adaptable al Atlántico Sur)
