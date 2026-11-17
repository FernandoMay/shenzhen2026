# 00 — AUDITORÍA DE PORTAFOLIO · Campaña Shenzhen 2026

**Fecha:** 17 de noviembre de 2026 · **Autor del trabajo:** Fernando May Fuentes · **Uso:** interno (no enviar a sponsors)

Esta auditoría evalúa las 4 líneas de investigación/desarrollo y el portafolio completo que las sostiene, con tres objetivos: (1) saber qué se puede afirmar con evidencia, (2) cerrar brechas antes del **29 de noviembre** (inicio de muShenzhen), y (3) fijar los *guardrails* de integridad para todo material público.

---

## 1. Credenciales del perfil (verificadas vs. pendientes)

| Credencial | Evidencia | Estado |
|---|---|---|
| B.Eng. Telemática, UPIITA-IPN (2015–2021) | Perfil público IPN/LinkedIn | ✅ Verificada |
| ORCID 0009-0002-3953-5224 | Registro ORCID | ✅ Verificada |
| Springer Nature, WITCOM 2025, DOI `10.1007/978-3-032-09735-4_6` | Springer + Google Scholar | ✅ Verificada |
| Papers IEEE 2026 en curso (ICCIA/ICCPR/ISCMI + ~20 paquetes) | Repos `*-package` en GitHub | ✅ En curso (no afirmar "aceptado") |
| Co-Creator muShanghai 2026 (10 may–6 jun, Alibaba Hongqiao) | LinkedIn (repost propio) + cobertura China Daily/PR Newswire del evento | ✅ Verificada |
| Trayectoria industria: Citi (iOS private bank), Intersistemas (apps médicas), Supernova (app audición), DSL Tech / CTO Dominic Sltns | LinkedIn/Torre | ✅ Verificada |
| GitHub: 234 repos públicos | API GitHub | ✅ Verificada |
| Experiencia Beihang | **Sin evidencia pública encontrada** | ⚠️ [COMPLETAR] — se necesita un documento propio: programa, fechas, profesor anfitrión, carta. Mientras no exista, el deck lo declara como [COMPLETAR] y no se usa en material público |

---

## 2. Las 4 líneas — evaluación y mejora

### 2.1 BioHealy (github.com/FernandoMay/biohealy-ipn) — fortaleza principal para Shenzhen

- **Evidencia actual:** repo público MIT, spec completa (ESP32-S3, AD9833 → Howland pump 10–1000 µA @ 0.1–100 kHz, DRV8837 + coil PEMF ≤100 µT @ 1–10 kHz, bioimpedancia 100 Ω–100 kΩ, BLE 5 + Flutter), BOM ~$25 USD. Repo es el único material público — no hay fotos de prototipo montado ni logs de medición.
- **Fortalezas:** costo 100x menor que alternativas; encaja exacto con los sponsors de Maker Faire (M5Stack, Seeed, ELEGOO, DFRobot, Tuya); narrativa accesibilidad LATAM; demo física posible en 20 días.
- **Brechas:**
  1. **Sin prototipo visible.** El spec sin hardware ensamblado es un paper, no un demo. Para muShenzhen Garage (Stage 1+, demo obligatoria) esto es el bloqueador #1.
  2. **Sin datos de calibración.** Bioimpedancia y corriente entregada sin curvas medidas no son defendibles ante un ingeniero de Shenzhen.
  3. **Riesgo regulatorio mal manejado sería fatal:** cualquier insinuación de uso clínico sin aprobación mata la conversación (y el permiso de trabajar en China).
- **Mejoras (P0):** (a) ensamblar 1 prototipo funcional con devkit prestado o comprado; (b) capturar 3 mediciones reales (curva de corriente del pump, respuesta PEMF del coil, lectura de bioimpedancia en 2–3 sujetos voluntarios con consentimiento) y publicarlas en el repo con fotos; (c) banner de disclaimer médico en README y en cada demo; (d) página de "safety limits" con los máximos de corriente/campo del diseño.
- **Veredicto:** la línea con mayor probabilidad de financiamiento en Shenzhen. Prioridad máxima de trabajo hasta el 29-nov.

### 2.2 XING (xing-core + xing-iccia2026 + xing-adan-resilience) — fortaleza académica

- **Evidencia actual:** repo `xing-core` con spec y runtime (kernel, WASM sandbox, MCP bus, memoria bi-temporal, provenance); paper IEEE ICCIA 2026 con simulador ejecutable, figuras, CSV de resultados y notas de replicación; ~20 paquetes IEEE/Springer 2025–2027 alrededor.
- **Fortalezas:** línea de investigación coherente y profunda; encaja con SLAI (Global Deep Sight 2027), InnoX y Sipeed; el simulador es reproducible — eso le da credibilidad real.
- **Brechas:**
  1. `xing-core` es spec + runtime inicial; falta un benchmark ejecutable contra un edge device (p. ej. MaixCAM de Sipeed) que convierta "arquitectura" en "medición".
  2. Los papers están "en preparación" — nunca afirmar aceptación hasta tener el notice.
  3. Sin supervisión formal declarada — para SLAI se necesita un supervisor matcheado.
- **Mejoras (P1):** (a) un notebook/repo `xing-edge-benchmarks` con 1 benchmark reproducible; (b) shortlist de 3 profesores SLAI/Beihang alineados a agentic infrastructure + borrador de email de supervisor; (c) sincronizar `xing-core` README con el paper (números consistentes).

### 2.3 MIRAI — la línea más débil en evidencia

- **Estado real:** concepto citado en el SDF Academic Grant (P4, vehículo de estudio de usabilidad) y alineado al track Human Flourishing de muShenzhen. **No existe repo, brand ni material.**
- **Mejoras (P1, costo bajo):** (a) crear repo `mirai-edu` con manifiesto y el primer módulo; (b) definir 1 taller de 2 h con material descargable (usa BioHealy y STB Suite como material de curso — mata dos pájaros); (c) agendar el taller dentro de muShenzhen (Human Flourishing acepta co-creación de sesiones); (d) foto/firma de asistencia del primer taller como evidencia.
- **Regla:** mientras no exista el taller, MIRAI se presenta como "pilot planned", jamás como plataforma activa.

### 2.4 Agentic Finance (SentinelX402 + STB Suite + voltx + Arceus) — fortaleza de ejecución

- **Evidencia actual (verificada en workspace):**
  - SentinelX402: x402 v2 real sobre stellar:testnet con facilitador Coinbase, 16+ patrones, txHash persistido.
  - STB Suite **v2 desplegada 2026-11-17** tras hardening: contratos con `__constructor` (el `initialize` invocable fue eliminado — hallazgo de auditoría **cerrado**), TÓMBOLA con **Stellar VRF Oracle real (drand quicknet)**.
  - Arceus escrow + donation-NFT: 17/17 y 10/10 tests, campañas/NFTs verificados on-chain.
  - voltx: 9 contratos, 71 tests, passkey AA + social recovery.
- **Brechas:**
  1. El hub público `stb-suite` en GitHub **todavía lista contract IDs v1** — actualizarlo tras completar bindings/E2E es obligatorio antes de enviarlo a cualquiera.
  2. Bindings TS + E2E Flutter pendientes contra los WASM v2.
  3. Ningún contrato tiene auditoría externa — declararlo siempre.
- **Mejoras (P1):** cerrar bindings + E2E + hub (todo está en `DEPLOYMENTS.md` como pendiente); usar esta línea como **prueba de rigor de ingeniería** en pitchs a incubadoras (InnoX/XbotPark), no como producto a vender.

---

## 3. Hallazgos transversales

| # | Hallazgo | Riesgo | Acción | Prioridad |
|---|---|---|---|---|
| 1 | BioHealy sin prototipo montado ni mediciones | Garage requiere demo Stage 1+ | Ensamblar + medir + publicar evidencia en repo | **P0 (antes 29-nov)** |
| 2 | Hub `stb-suite` con contract IDs v1 (obsoletos) | Due diligence inconsistente | Regenerar bindings, E2E, actualizar hub | P0 |
| 3 | Beihang sin documento propio | Claim no defendible en pitch | Documento de 1 página (fechas, programa, profesor) + escaneo de carta | P0 |
| 4 | MIRAI sin repo ni taller | Se percibe vaporware | Repo + taller agendado en muShenzhen | P1 |
| 5 | Repos de la suite (si-o-nel, tombola, bandera-roja) privados | Sponsor no puede verificar el código | Abrir repos o dar acceso de lectura bajo NDA informal | P1 |
| 6 | Cifras de portfolio inconsistentes (`fmf-ecosystem` dice "447 proyectos"; GitHub público = 234) | Percibido como inflado | En material público usar solo "234 public repos" y contar los 4 como proyectos actuales | P0 |
| 7 | `apps/PRODUCT-AUDIT.md` con QA pendiente (flujos admin privilegiados) | Sorpresa en demo en vivo | Completar la suite de tests privilegiados o demostrar solo flujos no-admin | P1 |
| 8 | Correos enviados (19) sin adjuntos | Sin material que aprobar internamente | Este paquete (`shenzhen2026/`) es el adjunto; enviar deck+dossier en el follow-up | **P0** |
| 9 | Email propio no fijado en documentos | Imposible que respondan | Definir email de contacto único y propagarlo en todos los archivos [COMPLETAR] | P0 |
| 10 | Sin plan de visa/seguro China | Riesgo del viaje | Iniciar visa (muShenzhen tiene "Express Visa Program") y seguro de viaje ya | P0 |

---

## 4. Matriz de prioridad con deadline

**Antes del 29-nov (Salida a Shenzhen):**
1. Prototipo BioHealy funcional + 3 mediciones documentadas (hallazgo 1).
2. Paquete adjunto listo y primer round de follow-ups con deck (hallazgos 8, 9).
3. Visa + seguro + vuelo + hospedaje reservados (hallazgo 10) — presupuesto [COMPLETAR].
4. Documento Beihang (hallazgo 3) — 1 hora de trabajo.

**Antes del 12-dic (Maker Faire Shenzhen):**
5. Hub `stb-suite` actualizado a v2 con E2E (hallazgo 2) + repos abiertos (hallazgo 5).
6. Taller MIRAI agendado y material listo (hallazgo 4).

**Enero–febrero 2027:**
7. Aplicación SLAI ronda 1 con propuesta XING + supervisor contactado.
8. Business plan InnoX NexTech (kit A en `09-KITS-APLICACION.md`) con BioHealy post-Garage (con datos reales de las 3 mediciones).

---

## 5. Guardrails de integridad (obligatorios en todo material público)

1. **Testnet only.** Toda evidencia on-chain es Stellar Testnet; jamás "Mainnet" o "producción".
2. **No device claims.** BioHealy es plataforma de investigación/wellness/biofeedback; nunca "dispositivo médico", "tratamiento" ni "aprobado".
3. **Papers en preparación ≠ aceptados.** ICCIA/ICCPR/ISCMI se describen como "submitted/in preparation" hasta tener notice.
4. **Contratos sin auditoría externa** se declara siempre que se muestran.
5. **Cifras verificables:** 234 repos públicos, no "447 proyectos"; contract IDs solo los v2 vigentes de `DEPLOYMENTS.md`.
6. **Beihang** no se menciona sin documento propio que lo respalde.
7. En cualquier colaboración con posibilidad de patente: firmar el acuerdo de PI (`08-ACUERDO-PI.md`) **antes** de compartir spec, firmware o datos.
