# 09 — Kits de aplicación (InnoX · SLAI · XbotPark · muShenzhen Garage)

> **Nota interna:** Material listo para armar las 4 aplicaciones. Español para notas internas; lo que se envía en inglés (o chino si el programa lo pide, `[COMPLETAR: confirmar idioma por programa]`). Nada inventado: los huecos van como `[COMPLETAR: …]`.

---

## Kit A — InnoX NexTech (`zhuo.yy@innoxsz.edu.cn`)

**Programa:** NexTech incubación, semilla **RMB 500k–5M**. Proyecto: **BioHealy**.
**Pendientes críticos:** elegibilidad de fundadores internacionales `[COMPLETAR: preguntar / confirmar respuesta]` · idioma del documento (EN o CN) `[COMPLETAR: preguntar]`.

### Checklist de documentos

| # | Documento | Estado |
|---|---|---|
| A1 | Business plan BioHealy (10 secciones, abajo) | Borrador abajo — a pulir |
| A2 | CV del fundador (Fernando May Fuentes) | `[COMPLETAR: CV actualizado — base: B.Eng. Telematics UPIITA-IPN, Springer WITCOM 2025 DOI 10.1007/978-3-032-09735-4_6, ORCID 0009-0002-3953-5224, GitHub 234 repos]` |
| A3 | Demo video (2–3 min) del prototipo | `[COMPLETAR: grabar durante muShenzhen Garage, Nov 29+]` |
| A4 | Link a repos públicos | Listo: github.com/FernandoMay/biohealy-ipn |
| A5 | Respuestas a preguntas de elegibilidad (internacional / single-founder / idioma) | `[COMPLETAR: esperar respuesta InnoX]` |

### Borrador de respuestas a la forma

- **Project name:** BioHealy.
- **One-line description:** *Open-source reconfigurable bio-stimulation and real-time bioimpedance platform on ESP32-S3; research/wellness/biofeedback platform, not an approved medical device.*
- **Stage:** Functional bench prototype (ESP32-S3 + AD9833 DDS + Howland pump + DRV8837 H-bridge + bioimpedance ADC + BLE 5 + Flutter app). `[COMPLETAR: confirmar etapa exacta según definiciones de la forma]`
- **Funding requested:** `[COMPLETAR: definir monto dentro del rango RMB 500k–5M — recomendación interna: pedir el mínimo que cubra 12 meses de prototipado y validación, no el tope]`
- **Founder(s):** `[COMPLETAR: solo founder o cofounder — pendiente]`

### Estructura del business plan (10 secciones, BioHealy)

| Sección | Contenido clave | Notas |
|---|---|---|
| 1. Problema | Equipos de bioestimulación/biofeedback comerciales cuestan $500–5000 USD, cerrados, no reconfigurables; la investigación en biofeedback no tiene hardware accesible ni reproducible. | Basado en comparación BOM vs comercial `[COMPLETAR: citar 3–5 equipos comerciales con fuente]` |
| 2. Mercado | Investigadores, labs académicos, comunidad wellness/biofeedback, talleres educativos. `[COMPLETAR: tamaño de mercado con fuente — no inventar cifras]` | Posición honesta: research/wellness, no dispositivo médico |
| 3. Producto | BioHealy: DDS AD9833 + Howland IMF 10–1000 µA, PEMF ≤100 µT vía DRV8837, bioimpedancia 100 Ω–100 kΩ, BLE 5 + app Flutter, BOM ~$25 USD, open-source. | Specs ya verificadas en repo |
| 4. Tecnología | ESP32-S3, arquitectura modular, app Flutter, telemetría; ventaja: reconfigurabilidad + costo + apertura. | Diagrama de bloques `[COMPLETAR: insertar]` |
| 5. Tracción | Repo público, prototipo funcional, publicación Springer WITCOM 2025, demo en muShenzhen Garage Nov 29–Dic 18. | `[COMPLETAR: métricas del repo — stars, forks, issues]` |
| 6. Modelo de negocio | Hardware kit + suscripción opcional de plataforma + licencias educativas (MIRAI). `[COMPLETAR: definir pricing]` | Coherente con open-source: núcleo abierto, servicios de pago |
| 7. Competencia | Comercial ($500–5000, cerrado) vs open-source académico (fragmentado); nuestro diferencial: costo + reconfiguración + comunidad. | Matriz comparativa `[COMPLETAR: tabla de 5 competidores]` |
| 8. Equipo | Fernando May Fuentes — B.Eng. Telematics UPIITA-IPN, autor Springer WITCOM 2025, 234 repos. `[COMPLETAR: confirmar si hay cofounder]` | |
| 9. Roadmap | Fase 1 (0–3 m): iteración del prototipo en Shenzhen, talleres. Fase 2 (3–12 m): pilot con 5–10 labs/usuarios. Fase 3 (12–24 m): kit productizado. `[COMPLETAR: fechas y hitos exactos]` | |
| 10. Ask | RMB `[COMPLETAR: monto]` para `[COMPLETAR: desglose — materiales, certificación preliminar, comunidad, viajes]` + mentoría de manufactura en Shenzhen. | |

---

## Kit B — SLAI Global Deep Sight Research Program 2027 (`externalaffairs@slai.edu.cn`)

**Programa:** ronda 1: 22 feb–14 may 2027; ronda 2: 1 jun–20 ago 2027. Proyecto: **XING**.
**Deadline ronda 1:** `[COMPLETAR: confirmar]`. **Pendientes:** procedimiento de aplicación · apoyo de vuelo · matching de supervisor.

### Checklist de documentos

| # | Documento | Estado |
|---|---|---|
| B1 | Propuesta de investigación de 2 páginas (estructura abajo) | Borrador abajo |
| B2 | CV académico en formato académico (publicaciones, proyectos, educación) | `[COMPLETAR: adaptar CV a formato académico — encabezar con WITCOM 2025 y paper ICCIA 2026 (en preparación/enviado: usar estado real)]` |
| B3 | Carta de la universidad (si la piden) | `[COMPLETAR: confirmar con UPIITA-IPN si emiten carta de apoyo/egresado — solo si SLAI la solicita]` |
| B4 | Link a repos de XING | Listo: xing-core + xing-iccia2026 `[COMPLETAR: URLs exactas]` |
| B5 | Paper IEEE ICCIA 2026 (status/stage) | `[COMPLETAR: adjuntar versión o resumen según estado permitido]` |

### Estructura de la propuesta de investigación (2 páginas)

- **Título:** *Cognitive infrastructure for multi-agent systems: bi-temporal memory, provenance and MCP-based orchestration at the edge.*
- **Research question:** ¿Cómo afectan la memoria bi-temporal y la provenance verificable al rendimiento, la auditabilidad y el uso de recursos de sistemas multi-agente ejecutados en edge devices? (Hipótesis: provenance + memoria bi-temporal mejoran auditabilidad sin degradar latencia más allá de X% `[COMPLETAR: hipótesis cuantitativa concreta del paper ICCIA]`.)
- **Método:** (1) implementación/benchmark del kernel XING + runtime WASM sobre plataformas edge `[COMPLETAR: plataformas — si hay colabo Sipeed, MaixCAM/K210]`; (2) suite de experimentos del simulador existente; (3) métricas: latencia, memoria, trazas de provenance, tasa de recuperación de memoria bi-temporal.
- **Entregables:** 1 paper (extensión ICCIA o nuevo), suite de benchmarks open-source, dataset público de resultados, informe técnico final del programa.
- **Supervisor deseado:** área de sistemas multi-agente / edge AI / distributed systems. `[COMPLETAR: si SLAI publica lista de supervisores, marcar 2–3 nombres]`
- **Relación con trabajo previo:** paper IEEE ICCIA 2026 con simulador y datos; repos xing-core y xing-iccia2026 públicos.

### Preguntas a responder sobre housing/travel grant (para el correo, ver 10-FOLLOW-UPS plantilla 4)

1. ¿El programa incluye housing o stipend para investigadores internacionales? `[COMPLETAR: respuesta SLAI]`
2. ¿Hay travel grant / apoyo de vuelo? `[COMPLETAR: respuesta SLAI]`
3. ¿El housing es en campus o coordinado por el programa? `[COMPLETAR: respuesta SLAI]`

---

## Kit C — XbotPark (`startX@xbotpark.com`)

**Programa:** incubación hardware/robótica. Proyecto: **BioHealy** (+ XING como capa de software).

### Checklist de documentos

| # | Documento | Estado |
|---|---|---|
| C1 | Respuestas a la forma de participación (abajo) | Borrador abajo |
| C2 | CV fundador | Reutilizar A2 `[COMPLETAR]` |
| C3 | Demo física / video portátil | `[COMPLETAR: grabar demo portable del prototipo con batería]` |
| C4 | Repos | Listo: biohealy-ipn, xing-core |

### Borrador de respuestas a la forma de participación

- **Project title:** BioHealy — open-source reconfigurable bio-stimulation & bioimpedance platform.
- **Current stage:** Functional bench prototype on ESP32-S3 (DDS signal generation 10–1000 µA Howland pump, PEMF ≤100 µT, bioimpedance 100 Ω–100 kΩ, BLE 5 + Flutter app). Open-source, BOM ~USD 25. **Stage:** `[COMPLETAR: categoría exacta que pida la forma — prototype/MVP]`
- **What we are looking for in Shenzhen:** access to hardware incubation mentorship, rapid prototyping/manufacturing partners (enclosure, PCB assembly at volume), and feedback from the XbotPark hardware ecosystem; goal: take BioHealy from bench prototype to manufacturable kit during 2027.
- **Team structure:** `[COMPLETAR: solo founder o cofounder — pendiente; si solo founder: mencionar soporte técnico de la comunidad open-source y mentores muShenzhen]`
- **Demo:** available on-site during Nov 29–Dec 18, 2026 (in Shenzhen for muShenzhen Garage).

---

## Kit D — muShenzhen Garage ($449 · 100 lugares · demo Stage 1+ requerida)

**Programa:** The Mu / muShenzhen Garage, Nov 29–Dic 18 2026. Proyecto demo: **BioHealy**.
**Nota económica interna:** el ticket Full/Alumni **$149–179** es la opción base si Garage no acepta — Garage cuesta $449. `[COMPLETAR: confirmar precios exactos y diferencia Full vs Alumni en la página de The Mu]`

### Pitch de 200 palabras (para la forma)

```
I build open-source hardware and agent infrastructure. I am Fernando May
Fuentes (B.Eng. Telematics, UPIITA-IPN, Mexico; author in Springer Nature
WITCOM 2025; 234 public repos), co-creator of muShanghai 2026.

My Stage 1+ demo is BioHealy: an open-source reconfigurable
bio-stimulation and real-time bioimpedance platform on ESP32-S3 — DDS
signal generation, Howland current pump (10–1000 µA), PEMF via H-bridge
(≤100 µT), bioimpedance measurement (100 Ω–100 kΩ), BLE 5 with a Flutter
app. Full bill of materials: ~USD 25, versus USD 500–5000 for commercial
units. It is a research/wellness/biofeedback platform, not an approved
medical device — open, documented, reproducible.

During the Garage I will iterate the prototype into a manufacturable
design, run a bilingual ES/ZH builder workshop (MIRAI, Human
Flourishing track), and demo at Maker Faire Shenzhen (Dec 12–13). My
second line, XING (cognitive infrastructure for multi-agent systems,
IEEE ICCIA 2026 paper), is ready for edge-AI collaboration.

In Shenzhen I want to compress two years of prototyping into three
weeks: hardware partners, manufacturing feedback, and a community that
builds in public.
```

*Nota interna: contar palabras al pegar; si la forma limita a menos, recortar el párrafo de XING primero.*

### Demo plan de BioHealy — qué se puede mostrar hoy vs en 20 días

| Ventana | Se puede mostrar | Notas |
|---|---|---|
| **Hoy (día 0, aplicación)** | Prototipo en bench: generación de señal DDS, salida del Howland pump medible, PEMF del H-bridge, lectura de bioimpedancia en rango 100 Ω–100 kΩ, conexión BLE 5 con app Flutter. | `[COMPLETAR: confirmar qué módulos están operativos hoy — marcar solo los verificados]` |
| **En 20 días (hito Garage, ~Dic 18)** | Enclosure impreso 3D, firmware con UI completa, telemetría en app (gráficas de bioimpedancia en tiempo real), kit portable con batería, documentación bilingüe ES/ZH lista para taller. | Depende de kits recibidos (M5Stack/Seeed/DFRobot) — plan B: mostrar con el hardware actual si los kits no llegan. |
| **Riesgos** | `[COMPLETAR: listar riesgos técnicos reales — p. ej. estabilidad del Howland a baja corriente, calibración de bioimpedancia]` y mitigación por cada uno. | Ser honesto en la aplicación: Stage 1+ = funciona en bench, no producto. |

### Plan B económico

- Si Garage no acepta: comprar ticket **Full/Alumni $149–179** `[COMPLETAR: elegir tier y confirmar precio exacto]` y asistir igual, con el mismo demo y taller — el programa de 3 semanas se pierde, la presencia en Shenzhen y Maker Faire se mantiene.

---

## Checklist maestro priorizado por deadline

| # | Acción | Deadline / fecha | Estado | Documento |
|---|---|---|---|---|
| 1 | Enviar aplicación muShenzhen Garage con pitch + demo plan (BioHealy Stage 1+) | **ASAP — el evento empieza Nov 29** | `[COMPLETAR]` | Kit D |
| 2 | Confirmar qué módulos del prototipo están operativos hoy (para demo Stage 1+) | Antes de enviar #1 | `[COMPLETAR]` | Kit D, demo plan |
| 3 | Contacto Chaihuo: follow-up sponsor intro (plantilla 5, día 5) | 22-nov-2026 | `[COMPLETAR]` | 10-FOLLOW-UPS |
| 4 | Chaihuo/Maker Faire: confirmar participación 12–13 dic (taller o demo) | `[COMPLETAR: fecha límite de agenda del Faire — confirmar]` | `[COMPLETAR]` | 07 §8 |
| 5 | SLAI: preguntar deadline ronda 1 + procedimiento + housing/travel (plantilla 4) | ASAP (aplicación con lead time) | `[COMPLETAR]` | Kit B |
| 6 | SLAI: propuesta investigación 2 páginas + CV académico listos | `[COMPLETAR: 1 semana antes del deadline ronda 1]` | `[COMPLETAR]` | Kit B |
| 7 | InnoX: enviar preguntas de elegibilidad (plantilla 3) | ASAP (rolling) | `[COMPLETAR]` | Kit A |
| 8 | InnoX: business plan 10 secciones pulido + CV | Rolling — `[COMPLETAR: fijar fecha objetivo]` | `[COMPLETAR]` | Kit A |
| 9 | XbotPark: enviar forma de participación + CV (plantilla 3) | ASAP (rolling) | `[COMPLETAR]` | Kit C |
| 10 | Follow-ups día 7 a dev teams sin respuesta (M5Stack/Seeed/Sipeed: plantilla 2) | 24-nov-2026 | `[COMPLETAR]` | 10-FOLLOW-UPS |
| 11 | Grabar demo video portable + fotos del prototipo | Semana del 23–29 nov | `[COMPLETAR]` | Kits A/C/D |
| 12 | Maker Faire Shenzhen — asistencia + taller/demo 12–13 dic | 12–13 dic 2026 | `[COMPLETAR]` | 07 §8 |
| 13 | SLAI ronda 2 (respaldo si ronda 1 no aplica) | hasta 20 ago 2027 | No urgente | Kit B |
| 14 | InnoX / XbotPark rolling — iterar según respuesta | Rolling | Continuo | Kits A/C |

**Regla de prioridad interna:** Garage (1–2) → Chaihuo (3–4, ventana corta) → SLAI ronda 1 (5–6) → kits de dev (10) → incubadoras rolling (7–9). Máximo 2 follow-ups por contacto (ver 10-FOLLOW-UPS.md).
