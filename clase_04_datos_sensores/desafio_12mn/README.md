# Desafío — ¿Dentro o fuera de las 12 millas? (peritaje VMS, caso simulado)

> 🟥 **DATOS SIMULADOS.** Este desafío recrea un expediente de sumario pesquero, pero **el buque *DON FICTICIO*, el armador, las personas, el número de expediente, las posiciones y las cifras son ficticios**. Solo son reales y públicas las **normas** citadas y las **capas oficiales** del Servicio de Hidrografía Naval (publicadas por el IGN).

**Encaje en el curso:** Clase 4 (datos y sensores: VMS, cartografía oficial) · Clase 6 (incertidumbre) · Clase 8 (asistentes de IA para expedientes)
**Inspirado en:** un caso real que trajo una alumna del curso (gestoría pesquera), recreado con datos ficticios.

---

## La situación

La armadora *Pesquera del Este Simulada S.R.L.* recibe un sumario: su buque *DON FICTICIO* habría navegado **a menos de 6 nudos dentro de la Zona de Veda Permanente** (Res. CFP 26/2009). El límite oeste de esa veda es el **límite exterior del Mar Territorial**, a 12 millas de las líneas de base de la Ley 23.968. Hacia tierra de esa línea las aguas son provinciales (Chubut) y la veda nacional no rige.

Ustedes son el **equipo técnico** de la armadora. Tienen el expediente y los datos. La armadora quiere saber la verdad técnica, **le convenga o no**.

> **Frase ancla:** *El barco no estaba "cerca" de la línea: estaba de un lado o del otro. El trabajo del perito es decir de cuál, y con cuánta seguridad.*

## El expediente (simulado)

| # | Archivo | Qué trae |
|---|---|---|
| 01 | [`expediente/01_notificacion_sumario_SIMULADA.pdf`](expediente/01_notificacion_sumario_SIMULADA.pdf) | Hecho imputado, fecha, normas, sanción |
| 02 | [`expediente/02_informe_monitoreo_autoridad_SIMULADO.pdf`](expediente/02_informe_monitoreo_autoridad_SIMULADO.pdf) | Las 5 posiciones que usa la autoridad |
| 03 | [`expediente/03_detalle_posiciones_proveedor_SIMULADO.html`](expediente/03_detalle_posiciones_proveedor_SIMULADO.html) | Export del VMS del proveedor de la armadora (96 posiciones, cada 15 min) |
| 04 | [`expediente/04_parte_de_pesca_SIMULADO.pdf`](expediente/04_parte_de_pesca_SIMULADO.pdf) | Declaración jurada del capitán: horarios, lances, captura, zona |
| 05 | [`expediente/05_croquis_capitan_SIMULADO.png`](expediente/05_croquis_capitan_SIMULADO.png) | Captura del ploter del capitán con *su* línea de 12 mn |
| 06 | [`expediente/06_normativa_extractos.md`](expediente/06_normativa_extractos.md) | Normativa citada (real) |

## Datos para el análisis

| Archivo | Contenido | Naturaleza |
|---|---|---|
| `recursos/vms_don_ficticio_SIMULADO.csv` | El mismo VMS del documento 03, en CSV | **Simulado** |
| `recursos/posiciones_autoridad_SIMULADO.csv` | Las posiciones del documento 02, en CSV | **Simulado** |
| `recursos/espacios_maritimos_chubut.geojson` | Límite exterior del Mar Territorial, líneas de base rectas y polígono del Mar Territorial (recorte 42,6°–44,6° S) | **Real**: SHN vía IGN (WFS) |
| `recursos/puntos_linea_base_ley23968_chubut_norte.csv` | Puntos 29–40 del Anexo I de la Ley 23.968 | **Real** |

## Consigna

Abrir [`notebooks/desafio_12mn_inicio.ipynb`](notebooks/desafio_12mn_inicio.ipynb) ([Colab](https://colab.research.google.com/github/PesquerosEnIA/curso-ia-produccion-pesquera/blob/master/clase_04_datos_sensores/desafio_12mn/notebooks/desafio_12mn_inicio.ipynb)). Ya trae cargados los datos y las funciones básicas (conversión de coordenadas, distancia firmada a la línea oficial). Hay que resolver 8 puntos:

1. Leer el expediente y armar la tabla de lo que afirma la autoridad.
2. Determinar en qué huso horario está el VMS.
3. Encontrar las posiciones de la autoridad en el VMS. Si no coinciden, explicar por qué.
4. Decidir dentro o fuera, con distancias en metros.
5. Cuantificar la incertidumbre (GPS y cartografía): qué es firme y qué es dudoso.
6. Comparar la línea del ploter del capitán con la oficial.
7. Verificar la coherencia con el parte de pesca.
8. Redactar conclusiones técnicas (máximo 1 página) honestas y útiles para decidir.

La rúbrica está al final del notebook. Se puede usar IA generativa para leer y resumir el expediente, pero **cada dato se verifica contra el documento** y los cálculos se hacen en código.

## Estructura

```
desafio_12mn/
├── expediente/  → 01..05 documentos SIMULADOS · 06 normativa (real)
├── notebooks/   → desafio_12mn_inicio.ipynb
└── recursos/    → CSV simulados · capas oficiales SHN/IGN (reales)
```
