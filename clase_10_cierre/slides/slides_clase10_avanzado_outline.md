# Outline de Slides — Clase 10 · 🔴 Nivel AVANZADO
## Cierre, Conclusiones y Hoja de Ruta

**Curso:** IA Aplicada a la Producción Pesquera | UTN FRCh · PesquerosEnIA
**Docentes:** Soraya Corvalán · Ariel Giamportone | ~12 slides
*Tono: técnico. De prototipo a producción; liderar la transformación.*

---

### Slide 1 — Portada
**Título:** Cierre — del notebook a producción
**Subtítulo:** Nivel Avanzado — Despliegue, monitoreo y mejora continua
*Nota: El modelo que anda en la laptop es el 10% del trabajo.*

---

### Slide 2 — Agenda
- El 90% que falta (producción)
- MLOps mínimo viable
- Integración de todo el curso
- Ética y sesgos en profundidad
- Hoja de ruta técnica

---

### Slide 3 — El 90% que falta
Datos → validación → despliegue → monitoreo → reentrenamiento → gobernanza.
*Nota: El océano no es estacionario; todo modelo pesquero caduca sin monitoreo.*

---

### Slide 4 — Validación honesta (el error más común)
Split temporal, no aleatorio. Calibración. Backtesting por temporada.
*Nota: El split aleatorio infla métricas y sorprende en producción.*

---

### Slide 5 — MLOps mínimo viable (sin plataforma cara)
Reproducibilidad · endpoint/batch simple · monitoreo de drift · gatillo de reentrenamiento.

---

### Slide 6 — Integración del curso como un sistema
C4 features → C6 predicción → C8 optimización+agente → C9 tablero → C10 gobierno.
*Nota: Un caso integrador realista une todos los bloques.*

---

### Slide 7 — Monitoreo de drift
Vigilar distribuciones de features y caída de performance en datos nuevos.
*Nota: La degradación es silenciosa; hay que instrumentarla.*

---

### Slide 8 — Ética y sesgos (profundo)
Sesgo de esfuerzo · restricciones duras (cuotas/vedas) · externalidades · privacidad.
*Nota: Eficiencia dentro del marco sostenible, medida sobre el stock.*

---

### Slide 9 — Explicabilidad
Modelos interpretables o SHAP cuando la decisión afecta a personas/recurso.
*Nota: Clave para adopción y para el regulador.*

---

### Slide 10 — Hoja de ruta técnica
Ahora: validación temporal + versionado.
3–6 m: modelo en servicio + monitoreo + ingesta real.
6–12 m: política por costo esperado (agente) + backtesting.

---

### Slide 11 — Proyecto integrador (exigencia avanzada)
Pipeline reproducible + validación temporal + plan de despliegue + restricciones de sostenibilidad.

---

### Slide 12 — Cierre + contribución
Contribuir a PesquerosEnIA (issues, PRs, casos). Publicar resultados reproducibles.
*Nota: El capital humano del sector sigue siendo el recurso más valioso.*
