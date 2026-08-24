# Clase 8 — Optimización de Operaciones y Agentes de IA
## 🟡 Nivel INTERMEDIO

> **Para participantes con base básica de Python** que leen y modifican código. Esta guía desarrolla el marco
> completo de la optimización operativa de una flota pesquera con datos: consumo, velocidad óptima, clustering,
> mantenimiento predictivo y agentes de IA. Se acompaña del notebook `clase08_optimizacion_intermedio.ipynb`.
> *(Existen variantes 🟢 Novato y 🔴 Avanzado de esta misma clase.)*

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN Facultad Regional Chubut | PesquerosEnIA
**Docentes:** Damián Giacone · Ariel Giamportone
**Duración:** 2 horas
**Modalidad:** Semipresencial / Virtual

---

## Objetivos de la clase

1. Dimensionar el **peso del combustible** en el costo operativo y entender por qué es la principal palanca de ahorro.
2. Construir un **modelo predictivo de consumo** a partir de variables operativas.
3. Determinar la **velocidad óptima** de crucero minimizando el costo total del viaje (ley cúbica).
4. Agrupar zonas por eficiencia con **clustering (K-Means)** para planificar la campaña.
5. Introducir el **mantenimiento predictivo** y un **agente de IA** de monitoreo autónomo.
6. Estimar el **impacto económico** de la optimización y discutir su uso sostenible.

---

## 1. El combustible, el mayor costo operativo

En la pesca argentina de altura, el gasoil representa entre el **25% y el 40%** de los costos operativos de una marea. Cifras de referencia de un arrastrero de altura: 15–25 toneladas de gasoil por marea; ~USD 800–900/tonelada; 10–14 mareas por año. Estudios internacionales muestran ahorros del **10–20%** optimizando velocidad y rutas. Para una flota de 20 barcos, eso puede significar **USD 0,8–2 millones/año**.

---

## 2. Modelo predictivo de consumo

Con un histórico de mareas (distancia, días en el mar, velocidad media, viento, estado del mar, horas de arrastre, profundidad, antigüedad del motor, mantenimiento reciente) se entrena un modelo que **predice el consumo de combustible** de una marea. Se usa un **Random Forest Regressor** y se evalúa con **MAE** (error en toneladas) y **R²**. Esto permite presupuestar mejor cada viaje, detectar qué factores elevan el consumo y comparar la eficiencia entre barcos de la misma flota.

---

## 3. La velocidad óptima de crucero

El consumo sigue la **ley cúbica del consumo naval** (ley de Admiralty): duplicar la velocidad multiplica el consumo por ~8. Pero navegar muy lento aumenta los días en el mar (más costo de tripulación y operación). Existe entonces una **velocidad de mínimo costo total**.

El modelo simplificado del notebook:

- Consumo del viaje ≈ `k · v³ · (distancia / v)` → crece fuerte con la velocidad.
- Costo de combustible = consumo × precio del gasoil.
- Costo del tiempo = horas de navegación × costo operativo por hora.
- **Costo total = combustible + tiempo** → se busca la velocidad que lo minimiza.

El resultado es una **curva en forma de U**: hay un punto óptimo, ni la velocidad máxima ni la mínima. El **simulador de velocidad** del aula permite mover velocidad, precio del gasoil y distancia y ver cómo se desplaza ese óptimo.

---

## 4. Clustering de zonas para planificar la campaña

No todas las zonas rinden igual. Con **K-Means** (aprendizaje no supervisado) se agrupan las zonas históricas según su **eficiencia** (captura por unidad de consumo). Así se identifican clusters de **alta, media y baja** eficiencia, y se planifica la campaña **priorizando** las zonas que más rinden por litro de gasoil, en vez de decidir por costumbre.

---

## 5. Mantenimiento predictivo

La telemetría del motor (temperatura, presión de aceite, vibración) permite pasar de un mantenimiento **correctivo** (arreglar cuando rompe) a uno **predictivo** (intervenir antes). Un modelo reconoce el **patrón que precede a la falla** y dispara una alerta para revisar el equipo en puerto, evitando averías costosas en alta mar. Es más barato, más seguro y evita paradas no planificadas.

---

## 6. Un agente de IA para monitoreo autónomo

Un **agente** integra todo lo anterior en un ciclo permanente: **percibe** (lee motor, consumo y posición de cada barco en tiempo real), **razona** (aplica los modelos como herramientas) y **actúa/recomienda** (seguir, bajar velocidad, volver a puerto), priorizando la **seguridad del motor** sobre el ahorro. No es un chatbot: es un sistema de **reglas + ML** que ordena la flota por prioridad y le acerca decisiones al operador.

---

## 7. Impacto económico de la optimización

Combinando velocidad óptima, mejor planificación y menos averías, la simulación del notebook estima el ahorro por marea y por temporada. La sensibilidad al **precio del gasoil** es alta: cuando sube, la velocidad óptima baja y el ahorro por optimizar crece. Es un caso claro de **IA que se paga sola**.

---

## 8. Ética y sostenibilidad

Optimizar **no debe traducirse en más esfuerzo pesquero**. El objetivo es hacer más eficiente el esfuerzo **permitido** (menos gasoil, menos averías, mejor logística), no aumentar capturas más allá de las cuotas. La tecnología atiende lo urgente; la **sostenibilidad marca el rumbo**.

---

## Actividad práctica: Notebook `clase08_optimizacion_intermedio.ipynb`

En Google Colab, recorré: modelo de consumo (Random Forest), curva de costo vs. velocidad y velocidad óptima, clustering de zonas, introducción al mantenimiento predictivo, el agente de monitoreo y la simulación de impacto económico.

**Ejercicios 🟡 incluidos:**
1. Cambiá el precio del gasoil y observá cómo se desplaza la velocidad óptima.
2. Ajustá el agente para que sea más o menos conservador y mirá cómo cambian sus recomendaciones.

---

## Referencias

- FAO — *Fuel and energy use in the fisheries sector* (consumo energético en la pesca de captura).
- scikit-learn — `RandomForestRegressor`, `KMeans`, `StandardScaler`.
- Estudios de eficiencia de flotas (rangos de ahorro 10–20%).
- Materiales de la Clase 6 (modelos predictivos) y del caso DT (AIS/esfuerzo).

## Ejercicios (nivel intermedio)

1. Sumá una variable al modelo de consumo (por ej. tipo de arte de pesca) y evaluá si mejora el R².
2. Probá K-Means con distinto número de clusters (k=2,3,4) y decidí cuál interpreta mejor las zonas.
3. Estimá el ahorro anual de una flota de 20 barcos aplicando un 15% de reducción de combustible.

## Para explorar más

- Simulador del aula: **velocidad óptima de crucero**.
- Repo del curso: https://github.com/PesquerosEnIA/curso-ia-produccion-pesquera
- Próxima clase (10): Cierre, conclusiones y hoja de ruta.
