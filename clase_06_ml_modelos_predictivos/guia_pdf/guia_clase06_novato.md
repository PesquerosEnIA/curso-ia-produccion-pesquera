# Clase 6 — Machine Learning y Modelos Predictivos en Pesca
## 🟢 Nivel NOVATO

> Para participantes **sin experiencia previa** en programación ni estadística. Esta guía explica, sin
> tecnicismos, cómo una computadora "aprende" a predecir zonas de pesca. Se acompaña del notebook
> `clase06_ml_novato.ipynb`, pensado para correr **sin escribir código**.
> *(Existen variantes 🟡 Intermedio y 🔴 Avanzado de esta misma clase.)*

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN Facultad Regional Chubut | PesquerosEnIA
**Docentes:** Damián Giacone · Ariel Giamportone
**Duración:** 2 horas
**Modalidad:** Semipresencial / Virtual

---

## Qué vas a poder decir al terminar esta clase

- "El Machine Learning es una computadora que **aprende de ejemplos**, no de reglas que le escribimos."
- "Un modelo no me da órdenes: me **ordena las zonas por probabilidad**, y la última palabra la tengo yo."
- "Ningún modelo es perfecto; lo importante es saber **cuánto y cómo se equivoca**."
- "Elegir el umbral —a partir de qué chance salgo a pescar— es una **decisión de negocio**, mía."

---

## 1. ¿Qué significa que una máquina "aprenda"?

En la programación de siempre, una persona le escribe a la computadora **todas las reglas**: "si pasa esto, hacé aquello". Funciona para cosas simples, pero la pesca es demasiado variable para escribir una regla para cada caso.

El **Machine Learning** (aprendizaje automático) le da vuelta la lógica: en vez de reglas, le mostramos **muchos ejemplos del pasado** —cientos o miles de mareas, con sus condiciones y su resultado— y la computadora **encuentra sola el patrón**.

> **En criollo:** es como un capitán con años de mar. Nadie le escribió un manual con "si el agua está a 9°C y hay mucha clorofila, andá al norte". Lo aprendió **mirando** muchas mareas. El ML hace lo mismo, pero mirando cientos de variables a la vez, algo imposible para una persona.

**La idea clave:** el modelo no memoriza, **generaliza**. Aprende la lógica de fondo para poder opinar sobre mareas que **nunca vio**.

---

## 2. El modelo ordena las zonas por probabilidad

Un buen modelo no te dice "andá acá" como una orden. Toma las condiciones de cada zona posible (temperatura, clorofila, profundidad) y te devuelve una **probabilidad de éxito** para cada una:

| Zona | Probabilidad de marea exitosa |
|------|------------------------------|
| Zona A — frente a Rawson | 82 % ✅ recomendada |
| Zona B — norte, aguas cálidas | 55 % |
| Zona C — sur, profunda | 23 % |

Con esto, en vez de salir a probar a ciegas, salís con las zonas **ordenadas de mejor a peor**. Menos vueltas, menos gasoil. Pero la decisión final —con tu experiencia, el estado del mar, lo que sabés que el modelo no ve— la seguís tomando vos.

---

## 3. Ningún modelo es perfecto: los dos errores

Un modelo se equivoca, siempre. Lo profesional no es buscar la perfección, sino **entender cómo se equivoca**. Hay dos tipos de error, y a cada uno lo sentís en el bolsillo:

- **Falso positivo:** el modelo dijo "hay", fuiste… y no había. → **Perdiste el viaje** (gasoil y tiempo).
- **Falso negativo:** el modelo dijo "no", no fuiste… y había una zona buenísima. → **Perdiste la oportunidad.**

No se pueden eliminar los dos a la vez: si querés estar más seguro antes de salir, vas a perder algunas buenas; si salís ante la menor chance, vas a hacer más viajes en vano. **Es un equilibrio, y depende de vos.**

---

## 4. El umbral lo elegís vos

Acá está la decisión más importante, y **no es técnica: es de negocio**. El umbral es la **chance mínima** a partir de la cual decidís salir.

- ¿Tu costo de gasoil es alto? Te conviene un umbral **exigente** (solo salís con alta probabilidad).
- ¿Estás en plena temporada y no querés perderte nada? Un umbral **más bajo** (salís aunque la chance sea media).

No hay un número "correcto" para todos. El modelo te da la probabilidad; **vos ponés el umbral** según tu realidad. Eso es usar la IA con criterio.

---

## 5. La actividad de hoy (notebook)

Abrí `clase06_ml_novato.ipynb` (en Google Colab, sin instalar nada) y corré las celdas con el botón ▶. Vas a ver, sin escribir código:

1. Cómo el modelo aprende de mareas pasadas.
2. Cómo le da una probabilidad a tres zonas y recomienda una.
3. Qué pasa con los kilos estimados si cambian las condiciones.

**Tu tarea:** cambiá un valor (por ejemplo, subí la clorofila de una zona) y volvé a correr. ¿Cambió la zona recomendada? Anotá qué observaste.

---

## Síntesis

- El **Machine Learning** aprende patrones de ejemplos; no le escribimos reglas, le mostramos datos.
- Un modelo **ordena las zonas por probabilidad** — te ayuda a decidir, no decide por vos.
- Todo modelo se equivoca: hay **falsos positivos** (viaje en vano) y **falsos negativos** (oportunidad perdida).
- El **umbral** es tuyo: dependiendo de tu costo, elegís con qué chance salir.
- **La IA complementa al capitán, no lo reemplaza.**

---

## Para seguir (sin apuro)

- Volvé a correr el notebook con distintas condiciones y mirá cómo cambia la recomendación.
- Probá el **simulador interactivo del umbral** que está en el aula: movés el umbral y ves la plata que ganás o perdés.
- Si te quedó gusto a poco, la variante 🟡 **Intermedio** de esta clase muestra cómo se entrena y evalúa un modelo por dentro.
