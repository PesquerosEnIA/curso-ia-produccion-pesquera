# Clase 9 — Visualización y Dashboards para la Toma de Decisiones

**Responsable:** Damian Giacone (principal)
**Duración:** 2 horas
**Notebook de apoyo:** Ariel Giamportone

---

## Objetivo

Que los participantes construyan visualizaciones interactivas y dashboards operativos de flota pesquera, y comprendan cuándo usar Python frente a herramientas de BI (Power BI, Tableau) para presentar datos a gerencias y organismos.

> **Nota de coordinación:** Damian cubre los fundamentos de visualización y BI. El notebook de apoyo (Ariel) aporta un dashboard operativo de flota aplicado al dominio pesquero.

---

## Contenido del notebook

- Visualizaciones interactivas con **Plotly** sobre datos de operaciones de flota
- **Dashboard operativo** con KPIs clave (producción, eficiencia, costos, cuotas)
- Análisis temporal (producción y eficiencia por mes) y ranking de barcos
- **Mapa interactivo** de actividad de flota con Folium
- Análisis por especie y seguimiento de cuotas de captura
- Exportación del reporte (CSV para Power BI) + dashboard consolidado para presentar
- Discusión: **Python vs Power BI / Tableau** — cuándo conviene cada uno

---

## Estructura de carpetas

```
clase_09_visualizacion_dashboards/
└── notebooks/
    ├── clase09_dashboard_pesquero.ipynb
    ├── dashboard_flota_pesquera.png   → render del panel consolidado
    └── reporte_flota_powerbi.csv      → export de ejemplo para Power BI
```

---

## Notebook principal

**`clase09_dashboard_pesquero.ipynb`**
- Dataset de operaciones de flota (buques, mareas, especies, cuotas, combustible)
- KPIs operativos y visualizaciones interactivas listas para gerencia
- Mapa de actividad de flota (Folium)
- Exportación a formatos consumibles por herramientas de BI

---

## Recursos a reutilizar

- [`Machine_Learning_for_Sales_and_operations_Planning`](https://github.com/arielgiamportone/Machine_Learning_for_Sales_and_operations_Planning) — patrones de reporting operativo
- [`ML_DL_FisheriesEngineers`](https://github.com/PesquerosEnIA/ML_DL_FisheriesEngineers) — datasets pesqueros de ejemplo

---

## Estado

- [x] Notebook: `clase09_dashboard_pesquero.ipynb`
- [x] Outputs de ejemplo (dashboard PNG + CSV Power BI)
- [ ] Slides / guía (coordinar con Damian)
- [ ] Revisión con Damian
