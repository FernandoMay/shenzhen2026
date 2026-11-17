# Shenzhen 2026 — Paquete Profesional de Colaboración

**Preparado:** 17-nov-2026 · **Fernando May Fuentes** · B.Eng. Telemática UPIITA-IPN · ORCID 0009-0002-3953-5224
**Destinos:** muShenzhen (29-nov → 18-dic) · Maker Faire Shenzhen (12–13 dic) · SLAI 2027 · InnoX NexTech · XbotPark · 12 empresas/instituciones contactadas (19 correos enviados al 17-nov)

Este paquete convierte los 19 correos enviados en un **material aprobable internamente**: cada empresa puede tomar un dossier, un deck y una propuesta y responder con una decisión.

---

## Mapa del paquete

| Archivo | Qué es | Idioma | Enviar a |
|---|---|---|---|
| `00-AUDITORIA-PORTAFOLIO.md` | Auditoría completa: evidencia, brechas, 10 hallazgos, prioridades P0/P1, guardrails de integridad | ES | Nadie (interno) |
| `01-DOSSIER-BIOHEALY.md` | Dossier flagship hardware: arquitectura, BOM $25, plan 20 días, asks por empresa, compliance | EN + 摘要 | M5Stack, Seeed, ELEGOO, DFRobot, Tuya, XbotPark, InnoX |
| `02-DOSSIER-XING.md` | Dossier de investigación: infraestructura cognitiva agéntica, paper ICCIA 2026, programa 2027 | EN + 摘要 | SLAI, InnoX, Sipeed, Tuya |
| `03-DOSSIER-MIRAI.md` | Dossier educativo (estado honesto: concepto + primer taller) | EN + 摘要 | Seeed Academic, Chaihuo, universidades |
| `04-DOSSIER-AGENTIC-FINANCE.md` | Dossier fintech: SentinelX402 (x402 real), STB Suite v2, voltx, estado honesto | EN + 摘要 | Incubadoras, Stellar SDF, pasarelas |
| `05-PITCH-DECK.md` | Fuente editable del deck bilingüe, 10 diapositivas | EN + 中文 | — |
| `06-PITCH-DECK.html` | Deck visual autocontenido (16:9, navegación con flechas, P = presentación, botón Imprimir/PDF) | EN + 中文 | **Adjunto principal** en follow-ups |
| `07-PROPUESTAS-EMPRESAS.md` | 12 propuestas de 1 página: ángulo, 3 opciones de ask, aporte, estado | ES interno / EN+中文 | Base para cada correo |
| `08-ACUERDO-PI.md` | Acuerdo marco de colaboración y PI bilingüe con anexo por proyecto | EN + 中文 | **Firmar antes de compartir spec/datos** |
| `09-KITS-APLICACION.md` | Kits A–D: InnoX NexTech, SLAI 2027, XbotPark, muShenzhen Garage + checklist por deadline | ES interno / EN+中文 | Trabajo interno |
| `10-FOLLOW-UPS.md` | 6 plantillas de follow-up (día 7) con regla de máx. 2 bumps | EN + 中文 | Correo |

---

## Los 4 proyectos (cada uno su línea)

| Línea | Repo | Estado | Encaje |
|---|---|---|---|
| **BioHealy** | `biohealy-ipn` (MIT, C++) | Spec completa; prototipo montado = P0 | Maker Faire sponsors, Garage, XbotPark, InnoX |
| **XING** | `xing-core` + `xing-iccia2026` | Runtime + paper con simulador | SLAI 2027, InnoX, Sipeed |
| **MIRAI** | (por crear) | Concepto + taller planeado | Human Flourishing, Seeed Academic |
| **Agentic Finance** | SentinelX402, STB Suite, voltx | v2 desplegada 17-nov (hardening + VRF real) | Incubadoras, SDF, rigor de ingeniería |

---

## Checklist de acción (próximos 10 días)

**Hoy / mañana:**
- [ ] Definir email de contacto único y propagarlo en todos los archivos `[COMPLETAR]` (hallazgo #9 de auditoría)
- [ ] Enviar `06-PITCH-DECK.html` + dossier correspondiente como adjunto a los follow-ups de día 7
- [ ] Iniciar visa China + seguro + reservar vuelo CDMX–SZX (muShenzhen Express Visa Program) — presupuesto [COMPLETAR]
- [ ] Escribir documento Beihang de 1 página (fechas, programa, profesor)

**Esta semana (P0):**
- [ ] Ensamblar prototipo BioHealy + capturar 3 mediciones + publicar en repo (bloqueador #1 del Garage)
- [ ] Regenerar bindings TS v2 + E2E + actualizar hub público `stb-suite` a contract IDs v2
- [ ] Corregir cifras: usar "234 public repos" en todo material

**Antes del 12-dic (Maker Faire):**
- [ ] Abrir repos si-o-nel / tombola / bandera-roja (o acceso de lectura)
- [ ] Crear repo MIRAI + material del taller + agendar sesión Human Flourishing
- [ ] Reunión Chaihuo/sponsors confirmada

**Enero–febrero 2027:**
- [ ] SLAI ronda 1: propuesta XING + 3 profesores contactados
- [ ] InnoX NexTech: business plan BioHealy con datos reales del Garage

## Guardrails (de `00-AUDITORIA-PORTAFOLIO.md`)

1. Todo on-chain = **Testnet only**. 2. BioHealy = plataforma de investigación/wellness, **nunca** dispositivo médico. 3. Papers = "in preparation" hasta notice. 4. Declarar "no external audit" siempre. 5. Contract IDs solo los v2 vigentes. 6. Beihang solo con documento propio. 7. **Acuerdo de PI (`08-ACUERDO-PI.md`) firmado antes de compartir spec/firmware/datos.**
