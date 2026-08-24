# Clase 8 — Optimización de Operaciones y Agentes de IA
## 🟢 Nivel NOVATO

> Para participantes **sin experiencia previa** en programación. Esta guía explica, sin tecnicismos, cómo la IA
> ayuda a gastar menos y operar mejor una flota: velocidad óptima, mantenimiento y un "asistente" que vigila.
> Se acompaña del notebook `clase08_optimizacion_novato.ipynb`, pensado para correr **sin escribir código**.
> *(Existen variantes 🟡 Intermedio y 🔴 Avanzado de esta misma clase.)*

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN Facultad Regional Chubut | PesquerosEnIA
**Docentes:** Damián Giacone · Ariel Giamportone
**Duración:** 2 horas
**Modalidad:** Semipresencial / Virtual

---

## Qué vas a poder decir al terminar esta clase

- "El combustible es el mayor costo de una marea, y ahí es donde más se ahorra con datos."
- "Ir más rápido gasta muchísimo más: existe una **velocidad óptima** que minimiza el costo del viaje."
- "El motor **avisa antes de romperse** si le ponemos sensores y miramos los datos."
- "Un **agente de IA** puede vigilar la flota y avisar solo, sin reemplazar al capitán."

---

## 1. El combustible: el gran costo de la marea

En la pesca de altura, el gasoil se lleva entre el **25% y el 40%** del costo de una marea. Es, por lejos, la mayor palanca de ahorro: cada gota que optimizás es plata directa. Por eso la optimización empieza por entender **dónde se va el combustible**.

> **En criollo:** no importa cuánto pesques si el viaje te come la ganancia en gasoil. Primero cuidamos la nafta.

---

## 2. La velocidad óptima: ir rápido cuesta al cubo

Acá hay una ley física clave (la **ley cúbica** del consumo naval): si **duplicás la velocidad, el consumo se multiplica por 8**, más o menos. Apurarse es carísimo.

Pero ir muy lento tampoco conviene: más días en el mar = más costo de tripulación y operación. Entonces existe un punto justo, una **velocidad óptima**, que hace **mínimo el costo total** del viaje — ni la más rápida ni la más lenta.

> El notebook (y el **simulador de velocidad** del aula) te dejan mover la velocidad y ver cómo cambia el costo. Vas a encontrar el punto donde gastás menos.

---

## 3. Anticipar la falla: el motor avisa antes de romperse

Romper el motor en medio del mar es lo peor que puede pasar. La IA permite pasar de **arreglar cuando se rompe** a **intervenir antes**: con sensores de temperatura, presión y vibración, el sistema **reconoce el patrón previo a una falla** y avisa para revisarlo en puerto. Se llama **mantenimiento predictivo**.

---

## 4. Un asistente que vigila la flota

Un **agente de IA** es un sistema que **percibe** (lee los datos de cada barco), **razona** (usa los modelos) y **actúa** (avisa: bajar velocidad, volver a puerto, revisar el motor) — de forma autónoma y en tiempo real. No es un chat: es un vigía que prioriza lo importante y **le acerca al capitán las decisiones**, sin reemplazarlo.

---

## 5. La actividad de hoy (notebook)

Abrí `clase08_optimizacion_novato.ipynb` en Google Colab y corré las celdas con ▶. Vas a ver, sin escribir código:

1. Cómo el consumo sube con la velocidad y dónde está el punto óptimo.
2. Cómo se agrupan las zonas por eficiencia para planificar la campaña.
3. Cómo el "agente" mira la flota y prioriza qué barco necesita atención.

**Tu tarea:** cambiá el precio del gasoil en el simulador y mirá si se corre la velocidad óptima. Anotá qué observaste.

---

## Síntesis

- El **combustible** es el mayor costo: ahí rinde más la optimización.
- Hay una **velocidad óptima** de mínimo costo (ni rápido ni lento).
- El **mantenimiento predictivo** anticipa fallas antes de que rompan.
- Un **agente de IA** vigila la flota y avisa solo — complementa al capitán, no lo reemplaza.

---

## Para seguir (sin apuro)

- Jugá con el **simulador de velocidad óptima** del aula: mové la velocidad, el precio del gasoil y la distancia.
- Pensá en tu operación: ¿a qué velocidad navegás hoy? ¿Sabés cuánto gasoil gastás por marea?
- Si querés más, la variante 🟡 **Intermedio** muestra cómo se arma el modelo de consumo y la curva de costo.
