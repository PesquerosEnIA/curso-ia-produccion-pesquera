# Outline de Slides — Clase 1 · 🟡 Nivel INTERMEDIO
## Estrategia y Transformación Digital en el Sector Pesquero

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera | UTN FRCh · PesquerosEnIA
**Docentes:** Ariel Giamportone · Soraya Corvalán | **Duración:** 2 horas | ~22 slides

---

### Slide 1 — Portada

**Título:** Estrategia y Transformación Digital en el Sector Pesquero
**Subtítulo:** Clase 1 — Inteligencia Artificial Aplicada a la Producción Pesquera
**Logos:** UTN FRCh | PesquerosEnIA
**Docentes:** Ariel Giamportone · Soraya Corvalán

*Nota: Abrir con una pregunta al grupo: "¿Cuántos de ustedes usan alguna herramienta digital en su trabajo cotidiano en el sector?" Mostrar manos/chat.*

---

### Slide 2 — Agenda de la clase

- El sector pesquero argentino en números
- La Cuarta Revolución Industrial llega al mar
- ¿Qué es una Smart Fishery?
- Casos de uso de IA: 5 aplicaciones concretas
- La brecha tecnológica y las oportunidades
- PesquerosEnIA: de dónde venimos
- Actividad práctica: mapeá tu oportunidad de IA

*Nota: Recorrer la agenda brevemente. Aclarar que la clase es conceptual — las herramientas concretas vienen en las clases siguientes.*

---

### Slide 3 — El mar argentino en números

**Título:** Argentina: una potencia pesquera con enorme potencial digital

- ZEE: **~1.000.000 km²** de Mar Argentino
- Exportaciones: **~USD 2.100 millones/año**
- Capturas totales: **~850.000 toneladas/año**
- Empleo directo: **~60.000 personas** (embarcados + tierra)
- ~600 buques habilitados — puertos en Patagonia, Bs.As., TDF

> "Con estos números, una mejora del 5% en eficiencia vía IA vale más de USD 100 millones."

*Nota: Usar mapa visual de la ZEE argentina con los principales puertos. Hacer referencia a la región de los participantes.*

---

### Slide 4 — Principales especies y su valor

**Título:** Las especies que mueven la economía pesquera argentina

| Especie | Participación | Destino principal |
|---------|--------------|-------------------|
| Merluza hubbsi | ~40% del volumen | UE, Brasil |
| Calamar illex | ~30% del volumen | Asia, UE |
| Langostino patagónico | ~15% del valor | UE, EE.UU. |
| Vieira patagónica | En crecimiento | Asia |

*Nota: Cada especie tiene sus particularidades de datos: el calamar tiene alta variabilidad interanual ligada a El Niño; el langostino tiene estrictos requisitos de trazabilidad para exportar a la UE.*

---

### Slide 5 — La Cuarta Revolución Industrial

**Título:** Industria 4.0: ya está pasando, también en el mar

- **IoT:** sensores que capturan datos 24/7 (temperatura, posición, captura)
- **Big Data:** millones de registros de AIS, partes de pesca, sensores oceanográficos
- **Inteligencia Artificial:** algoritmos que aprenden y predicen
- **Conectividad:** Starlink ya está en barcos de altura

**¿Qué lo hace diferente de otras revoluciones?**
Las máquinas ya no solo ejecutan — también *aprenden* y *deciden*.

*Nota: Analogía con el agro argentino: la agricultura de precisión ya usa drones, imágenes satelitales y ML para soja. El sector pesquero puede hacer lo mismo.*

---

### Slide 6 — ¿Qué hace diferente al sector pesquero?

**Título:** El mar tiene sus propias reglas

| Característica | Desafío | Oportunidad IA |
|----------------|---------|----------------|
| Recurso invisible y variable | No podés ver los peces | Predicción por datos ambientales |
| Ambiente hostil | Los sensores deben ser robustos | Monitoreo remoto satelital |
| Cadena fría crítica | Trazabilidad compleja | Sensores + blockchain |
| Regulación estricta | Carga de reportes | Automatización de partes de pesca |

*Nota: Preguntar al grupo: ¿qué otras características del sector pesquero hacen difícil o diferente la adopción tecnológica?*

---

### Slide 7 — Smart Fisheries: el concepto

**Título:** Smart Fishery = Datos + Conectividad + Algoritmos + Decisión

**Diagrama central:**
```
Sensores/AIS/Satélites → [DATOS] → Algoritmos IA → [DECISIÓN] → Capitán / Planta / Regulador
```

**Los 4 pilares:**
1. **Eficiencia operativa** — menos combustible, más captura por marea
2. **Sostenibilidad** — pesca dentro de los límites del stock
3. **Trazabilidad** — del anzuelo al plato, verificable
4. **Cumplimiento** — reportes automáticos, menos carga burocrática

*Nota: Mostrar video corto de Global Fishing Watch si hay conexión. Alternativamente, screenshot del mapa en tiempo real.*

---

### Slide 8 — Casos globales líderes

**Título:** El mundo ya avanzó — esto es lo que hacen los líderes

- 🇳🇴 **Noruega:** flota con transmisión en tiempo real de capturas + IA para optimización de redes de arrastre (Kongsberg Maritime)
- 🇮🇸 **Islandia:** 90% de la flota reporta captura digitalmente en tiempo real al gobierno
- 🇨🇱 **Chile:** imágenes SAR para monitoreo de acuicultura y detección de flota irregular
- 🌐 **Global Fishing Watch:** monitorea 60.000 barcos con ML — detección de pesca ilegal con >95% de precisión

*Nota: Estos países tienen flota comparable a Argentina en tamaño. No son "países del futuro" — ya lo implementaron.*

---

### Slide 9 — Caso de uso 1: Predicción de zonas de pesca

**Título:** IA que predice dónde están los peces

**El problema:** El capitán decide a qué zona ir basándose en experiencia + información limitada.
**La solución IA:** Modelos de ML que procesan SST, clorofila, corrientes, batimetría e historial de capturas para recomendar zonas de alta probabilidad.

**Impacto demostrado:**
- Reducción 20-30% en días de búsqueda improductiva
- Ahorro de combustible: ~15-20% por marea
- Aumento del rendimiento (ton/día en mar)

**Datos necesarios:** Copernicus Marine Service, NOAA, datos históricos de partes de pesca

*Nota: Esto lo vamos a hacer nosotros en la Clase 6 con un modelo de Random Forest real.*

---

### Slide 10 — Caso de uso 2: Monitoreo satelital y AIS

**Título:** Cada barco tiene una huella digital en el mar

**AIS (Automatic Identification System):**
- Obligatorio en buques >300 GT
- Transmite: posición, velocidad, rumbo, ID del barco cada 2-10 segundos
- Global Fishing Watch: 50 TB de datos AIS procesados por día

**VMS (Vessel Monitoring System):**
- Obligatorio para pesqueros argentinos
- Gestionado por la Subsecretaría de Pesca
- Cada 30-60 minutos, transmisión satelital

**Dark vessels:** barcos que apagan el AIS — detectados por imágenes SAR + IA

*Nota: Mostrar el mapa de Global Fishing Watch en el Mar Argentino. Los puntos en movimiento son barcos en tiempo real.*

---

### Slide 11 — Caso de uso 3: Visión artificial en planta

**Título:** Cámaras que ven mejor y más rápido que el ojo humano

**El problema:** Clasificar y medir miles de peces por hora es costoso, lento y variable.
**La solución:** Cámaras de alta velocidad + modelos de visión artificial.

**Aplicaciones reales:**
- Clasificación por especie (merluza / polaca / castañeta) a >100 peces/minuto
- Medición automática de talla individual (reemplaza medición manual)
- Detección de parásitos o defectos en filetes
- Evaluación de frescura por color y textura

**Tecnología disponible:** Marel, Baader, TriVision (ya operan en plantas en Argentina)

*Nota: Video de línea de procesamiento automatizada si disponible.*

---

### Slide 12 — Caso de uso 4: Trazabilidad digital

**Título:** Del anzuelo al plato — verificable con un escaneo

**El recorrido:** Barco → Puerto → Frigorífico → Planta → Exportador → Supermercado

**La cadena de trazabilidad digital:**
- Cada paso registrado con timestamp y firma digital
- Código QR en el producto final
- El consumidor escanea y ve: barco, zona, fecha, certificaciones

**En Argentina:** el Sistema de Trazabilidad Pesquera (SiTP) en desarrollo
**En Europa:** requisito obligatorio para importar desde 2025+

*Nota: La trazabilidad no es solo un requisito regulatorio — es una ventaja comercial. Los mercados premium pagan más por producto trazable.*

---

### Slide 13 — Caso de uso 5: Optimización de flota

**Título:** Cada litro de gasoil cuenta — la IA lo sabe

- **Rutas optimizadas:** algoritmos que consideran corrientes, vientos, zonas de pesca → ahorro 10-20% de combustible
- **Velocidad óptima:** la ley cúbica del combustible naval — cada nudo extra cuesta el triple
- **Mantenimiento predictivo:** sensores en motores detectan anomalías antes de la avería
- **Logística portuaria:** coordinación de desembarco, frigorífico y planta

**Ejemplo:** Una flota de 20 arrastreros de altura en Argentina. Ahorro proyectado con optimización IA: USD 800.000–1.200.000/año en combustible.

*Nota: En la Clase 8 vamos a construir este modelo de optimización juntos.*

---

### Slide 14 — La brecha tecnológica: diagnóstico honesto

**Título:** ¿Por qué el sector pesquero argentino todavía no despegó?

**Barreras reales:**

1. 🎓 **Formación:** pocos profesionales del sector con competencias en datos e IA
2. 📡 **Conectividad:** internet satelital recién llega a los barcos a costos accesibles
3. 💰 **Inversión:** costo percibido alto para empresas medianas
4. 🗣️ **Idioma:** casi todo el material de calidad está en inglés
5. 🧠 **Cultura:** "siempre lo hicimos así" — resistencia al cambio
6. ⚖️ **Regulación:** el marco regulatorio no siempre acompaña la innovación

*Nota: No se trata de criticar al sector — estas barreras existen en todas las industrias primarias. La buena noticia: todas son superables.*

---

### Slide 15 — Las señales de cambio

**Título:** El viento está cambiando — y hay que estar preparado

- **Pampa Azul:** programa del MINCYT con foco en economía del conocimiento marina
- **Starlink en barcos:** ya en operación en flotas argentinas de altura
- **INIDEP abre datos:** datasets históricos de gran valor, disponibles para análisis
- **Empresas líderes** adoptando trazabilidad para cumplir con requisitos de exportación UE
- **PesquerosEnIA:** comunidad activa de profesionales del sector aprendiendo IA

> "No se trata de si el sector se va a digitalizar — se trata de si vamos a ser protagonistas o espectadores de esa transformación."

*Nota: Este es el momento de motivación. El curso que están cursando los pone en el grupo de los protagonistas.*

---

### Slide 16 — PesquerosEnIA: quiénes somos

**Título:** PesquerosEnIA — IA para el sector pesquero, desde el sector pesquero

**Historia:**
- 2019: I CONIPE — minicurso Industria 4.0 (8 horas) + mesa redonda
- 2025: CONIPE 2025 — curso alfabetización en IA (8 módulos, Puerto Madryn)
- 2026: Este curso — 23 horas de formación aplicada

**Principios:**
- Contenido en español, contextualizado al sector
- Acceso abierto (GPL-3.0)
- Colaboración entre pares
- Desde el sector, para el sector

**GitHub:** github.com/PesquerosEnIA

*Nota: Mostrar el repositorio en vivo si hay conexión.*

---

### Slide 17 — El equipo docente

**Título:** Quiénes están detrás del curso

- **Ariel Giamportone** — Ing. Pesquero UTN FRCh | Data Science & IA | MBA Log. y Operaciones | Intervalor Data, Madrid
- **Soraya Corvalán** — Ing. Pesquera | INIDEP | FAO | Profesora Asociada UTN FRCh | Primera graduada Ing. Pesquera Argentina
- **Damian Adolfo Giacone** — Lic. Sistemas | Máster Industria 4.0 IEBS | Docente UGR | Ex-Alpesca S.A.
- **Dr. Juan D. González** — Dr. Mat. Aplicada UBA | SENASA IA | CONICET | paquetes RMBC + ktaucenters en CRAN

*Nota: Presentación breve de cada docente. Hacer hincapié en que todos tienen experiencia concreta en el sector pesquero, no solo en IA genérica.*

---

### Slide 18 — Estructura del curso

**Título:** 23 horas de IA aplicada al sector pesquero

| Clase | Tema | |
|-------|------|--|
| **1** | Estrategia y Transformación Digital | ← Estamos aquí |
| 2 | Fundamentos de IA y LLMs | |
| 3 | Prompting y Asistentes de IA | |
| **4** | Datos y Sensores del Dominio Pesquero | |
| 5 | Arquitectura de Datos y Big Data | |
| **6** | Machine Learning y Modelos Predictivos | |
| 7 | Visión Artificial en Plantas | |
| **8** | Optimización y Agentes de IA | |
| 9 | Visualización y Dashboards | |
| **10** | Cierre y Hoja de Ruta | |
| + | Charlas Dr. González (acústica + clustering) | |

*Nota: Clases en negrita son las de Ariel. Mostrar el recorrido completo del curso para que los participantes entiendan la progresión.*

---

### Slide 19 — ¿Qué van a poder hacer al terminar el curso?

**Título:** El horizonte: competencias concretas para el sector

Al terminar este curso, vas a poder:

✅ Usar LLMs y prompting para automatizar reportes y análisis
✅ Acceder y explorar datos oceanográficos y de captura reales
✅ Construir modelos de ML para predecir zonas de pesca
✅ Entender y comunicar los resultados de un modelo de visión artificial
✅ Optimizar rutas y operaciones con herramientas de IA
✅ Armar dashboards de toma de decisiones para tu organización
✅ Diseñar un caso de uso de IA para tu contexto específico

*Nota: Vincular cada competencia con una clase específica del programa.*

---

### Slide 20 — Actividad práctica: mapeá tu oportunidad

**Título:** Actividad — 20 minutos

**Instrucción:**
Identificá un problema concreto de tu sector donde la IA podría agregar valor.

| Campo | Tu respuesta |
|-------|-------------|
| Mi rol en el sector | |
| El problema que identifico | |
| Datos existentes sobre este problema | |
| Tipo de IA (predicción / clasificación / optimización) | |
| Beneficio esperado | |

**Luego:** compartís con el grupo. El docente guía la puesta en común.

*Nota: Circular por el grupo durante la actividad. Esta información es valiosa para orientar ejemplos en las clases siguientes.*

---

### Slide 21 — Cierre y síntesis

**Título:** Lo que vimos hoy

- El sector pesquero argentino es estratégico y tiene enorme potencial de digitalización
- La IA no es magia — son algoritmos que aprenden de datos que ya existen en el sector
- Smart Fisheries integra sensores + conectividad + datos + algoritmos
- Hay 5 aplicaciones concretas ya disponibles: predicción de zonas, monitoreo AIS, visión artificial, trazabilidad, optimización de flota
- La brecha existe pero es superable — y este curso es un paso concreto
- PesquerosEnIA: una comunidad que ya está construyendo este puente

*Nota: Invitar a hacer preguntas. Recordar que los materiales de la clase (guía + slides) están disponibles en el repo GitHub.*

---

### Slide 22 — Próxima clase

**Título:** Clase 2 — Fundamentos de IA y Modelos de Lenguaje (LLMs)

**Docente:** Damian Adolfo Giacone

**¿Qué vamos a aprender?**
- Diferencia entre IA tradicional y IA generativa
- Cómo funcionan los LLMs (GPT, Claude, Llama)
- Aplicaciones concretas en el sector pesquero: análisis de reportes, informes técnicos, asistencia para cumplimiento normativo

**Para la próxima clase:** si podés, probá ChatGPT o Claude con una pregunta de tu sector pesquero. Traé la experiencia para compartir.

**Materiales de hoy disponibles en:**
github.com/PesquerosEnIA/curso-ia-produccion-pesquera

*Nota: Despedir con energía. Recordar la actividad: los casos de uso que levantaron hoy van a aparecer en clases futuras como ejemplos.*
