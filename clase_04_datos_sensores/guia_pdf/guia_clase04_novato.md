# Clase 4 — Datos y Sensores del Dominio Pesquero
## 🟢 Nivel NOVATO

> **Para participantes sin experiencia previa en programación ni datos.** Esta guía usa
> lenguaje llano y analogías del oficio. No hay que escribir código: el notebook
> `clase04_datos_novato.ipynb` se ejecuta apretando ▶.
> *(Existen variantes 🟡 Intermedio y 🔴 Avanzado de esta misma clase.)*

**Curso:** Inteligencia Artificial Aplicada a la Producción Pesquera
**Institución:** UTN FRCh · PesquerosEnIA
**Docentes:** Ariel Giamportone · Soraya Corvalán
**Duración:** 2 horas

---

## Qué vas a poder decir al terminar esta clase

1. "Mi barco y mi planta **generan datos todo el tiempo**, y sé cuáles son."
2. "La **temperatura del mar** y la **clorofila** me dan pistas de dónde hay pesca."
3. "Sé que existen **plataformas gratuitas** con datos del mar argentino."

No necesitás saber programar. Necesitás **entender qué información hay y para qué sirve.**

---

## 1. Tu barco es una fábrica de datos

Pensá en un día normal de pesca. Sin darte cuenta, se están registrando muchos números:

| Lo que pasa a bordo | El dato que queda |
|---------------------|-------------------|
| El GPS marca dónde estás | Posición (latitud y longitud) |
| La ecosonda "ve" el fondo y los cardúmenes | Profundidad y señal de peces |
| Un sensor mide el agua | Temperatura del mar |
| Se pesa la captura | Kilos por lance |
| Se llena el parte de pesca | Especie, zona, hora |

**El problema histórico:** todos esos datos casi nunca se miran juntos. Es como tener
20 años de cuadernos de pesca guardados en un cajón. La IA sirve, justamente, para
**sacarles el jugo a datos que ya tenés.**

---

## 2. La temperatura del mar: la primera pista

Cada especie prefiere una temperatura de agua, igual que cada cultivo prefiere un clima:

- 🐟 **Merluza:** agua fresca, 4 a 12 °C
- 🦑 **Calamar:** un poco más cálida, 8 a 16 °C
- 🦐 **Langostino:** 6 a 14 °C

Los **satélites** miden la temperatura de todo el mar, todos los días, **gratis**. Si sabés
que la merluza anda en agua de 9–12 °C, podés mirar el mapa **antes de salir** y elegir
mejor la zona. Menos vueltas = menos gasoil = más ganancia.

> **Frentes:** donde se junta el agua fría del sur (Corriente de Malvinas) con la cálida
> del norte (Corriente de Brasil) se arma una zona muy rica en pesca. Se llama
> "frente Malvinas-Brasil" y está más o menos a la altura de la provincia de Buenos Aires.

---

## 3. La clorofila: la comida del mar

La **clorofila** mide cuánto **fitoplancton** hay (unas plantitas microscópicas invisibles).
Es el primer eslabón de la cadena: más fitoplancton → más comida → más peces.

**Regla simple:** donde hay mucha clorofila, suele haber pesca. Los satélites también la
miden gratis. Un buen ojo cruza los dos mapas: **temperatura adecuada + mucha comida = buena zona.**

---

## 4. ¿Dónde están estos datos? (todos gratis)

No hay que comprar nada. Basta con saber que existen:

| Plataforma | Qué te da |
|-----------|-----------|
| **Copernicus Marine** (Europa) | Temperatura y clorofila del mar por satélite |
| **NOAA** (EE.UU.) | Temperatura del mar de alta calidad |
| **Global Fishing Watch** | Dónde están pescando los barcos en el mundo |
| **INIDEP** (Argentina) | Capturas y estado de los recursos del país |

En esta clase no vas a descargar nada: solo queremos que sepas que **la información está ahí**,
lista para quien la sepa aprovechar.

---

## 5. La actividad de hoy (notebook)

Vas a abrir el notebook `clase04_datos_novato.ipynb` y **apretar ▶** en cada bloque.
Vas a ver, con tus propios ojos:

1. Un **mapa de temperatura** del mar argentino (frío al sur, cálido al norte).
2. Un **mapa de clorofila** (dónde está la comida).
3. Un **gráfico** que muestra que la merluza se pesca más en agua templada (9–12 °C).

No se puede romper nada. Si algo sale mal, se vuelve a apretar ▶ y listo.

---

## Síntesis

- Tus operaciones **ya producen datos**; el valor está en **usarlos**.
- **Temperatura + clorofila** son las dos pistas ambientales más importantes.
- La merluza rinde más en agua **templada (9–12 °C)**.
- Hay **datos gratuitos** del mar argentino esperando ser aprovechados.

## Para seguir (sin apuro)

- Repetí el notebook y cambiá algún número para perderle el miedo.
- Cuando te sientas cómodo, pasá al **Nivel Intermedio** de esta clase.
- Comunidad **PesquerosEnIA:** https://github.com/PesquerosEnIA
