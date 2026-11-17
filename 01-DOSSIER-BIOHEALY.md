# BioHealy — Reconfigurable Bioelectric Stimulation Platform with Real-Time Bioimpedance Monitoring

**Project dossier — muShenzhen Garage 2026 (Nov 29 – Dec 18, C2 Hub, OCT-LOFT North)**
**Author:** Fernando May Fuentes — B.Eng. Telematics Engineering, UPIITA-IPN (Mexico City)
ORCID 0009-0002-3953-5224 · GitHub: https://github.com/FernandoMay · LinkedIn: https://linkedin.com/in/fernandomay
**Repo:** https://github.com/FernandoMay/biohealy-ipn (C++, MIT license, open source)

---

## 摘要 (Chinese Executive Summary)

BioHealy 是一个开源（MIT 许可）的可重构生物电刺激与实时生物阻抗监测平台，
基于 ESP32-S3（RISC-V）+ BLE 5.0 构建，硬件物料成本约 25 美元，
远低于市面上 500–5000 美元的同类设备（成本降低约 100 倍）。
平台集成 AD9833 DDS 信号源与 Howland 电流泵，支持 10–1000 µA、0.1–100 kHz 的
微电流频率疗法（IMF）；DRV8837 H 桥与平面线圈可输出高达 100 µT、1–10 kHz 的 PEMF；
实时生物阻抗测量范围为 100 Ω–100 kΩ，采用双对电极设计；
配套 Flutter 移动应用通过 BLE 连接。
本项目定位为研究/健康/生物反馈平台，并非已获批的医疗设备。
在 muShenzhen Garage 的 20 天计划中，目标为完成整板集成、校准、
生物阻抗数据集、Flutter 应用与云端仪表盘，以及 3 个可演示场景与 DFM 制造文档。
诚邀 M5Stack、Seeed Studio、ELEGOO、DFRobot、Tuya 等伙伴提供开发板、
传感器、云平台与制造支持。

---

## 1. Problem & Thesis

Bioelectric therapies — microcurrent frequency (IMF) stimulation and pulsed
electromagnetic field (PEMF) — are widely used in rehabilitation and wellness,
but the equipment is priced for clinics and wealthy markets: commercial units
cost **USD 500–5,000**. In low-resource clinics across Latin America (and other
emerging regions), this pricing makes the technology effectively inaccessible,
and the same equipment almost never includes **objective measurement** of tissue
response.

**Thesis:** with modern commodity silicon, a research-grade reconfigurable
stimulation platform with real-time bioimpedance monitoring can be built for
**~USD 25 in BOM** — roughly a **100x cost reduction** — and opened as open
source so local engineers, universities, and clinics can adapt, repair, and
extend it instead of importing closed devices.

The platform is deliberately positioned as **instrumentation + biofeedback**:
measure bioimpedance, apply configurable low-power stimulation, log everything,
and let researchers define protocols. It is **not** a certified medical device
(see Section 6).

## 2. System Architecture

Textual block diagram (as implemented in the repo):

```
                    ┌────────────────────────────────────────────┐
                    │        ESP32-S3 (RISC-V) · BLE 5.0         │
                    │  firmware: protocol engine + safety limits │
                    └──────┬───────────────┬──────────────┬──────┘
                           │ SPI           │ GPIO/PWM     │ ADC (multiplexed)
                    ┌──────▼──────┐ ┌──────▼───────┐ ┌────▼──────────────┐
                    │ AD9833 DDS  │ │ DRV8837      │ │ Bioimpedance      │
                    │ (SPI)       │ │ H-bridge +   │ │ module            │
                    │ waveform    │ │ planar coil  │ │ 100 Ω – 100 kΩ    │
                    │ synthesis   │ │ → PEMF up to │ │ 2-pair electrode  │
                    │ 0.1–100 kHz │ │ 100 µT @     │ │ real-time Z(t)    │
                    └──────┬──────┘ │ 1–10 kHz     │ └────┬──────────────┘
                           │        └──────────────┘      │
                    ┌──────▼───────────────────────────────▼──────┐
                    │ Howland current pump                        │
                    │ → Microcurrent Frequency therapy (IMF)      │
                    │   10–1000 µA @ 0.1–100 kHz                  │
                    └──────────────────┬──────────────────────────┘
                                       │ electrodes (2-pair)
                    ┌──────────────────▼──────────────────────────┐
                    │        Flutter mobile app · BLE GATT        │
                    │  protocol config · live impedance curves    │
                    │  session logging · (cloud dashboard: WIP)   │
                    └─────────────────────────────────────────────┘
```

Key design points:

| Block | Component | Verified spec (repo) |
|---|---|---|
| Controller | ESP32-S3 (RISC-V) | BLE 5.0 host for app + provisioning |
| Waveform | AD9833 DDS over SPI | 0.1–100 kHz programmable output |
| IMF output | Howland current pump | 10–1000 µA, current-controlled |
| PEMF | DRV8837 H-bridge + planar coil | up to 100 µT @ 1–10 kHz |
| Measurement | Bioimpedance ADC module | 100 Ω–100 kΩ, 2-pair electrodes, real time |
| UX | Flutter mobile app | BLE transport, live curves, session logs |
| Cost | Full BOM | ~USD 25 (vs. USD 500–5,000 commercial) |

## 3. Current Status

| Item | Status |
|---|---|
| Public repo, MIT license | ✅ https://github.com/FernandoMay/biohealy-ipn |
| Full electronics specification | ✅ in repo |
| Firmware completion | [COMPLETAR: % completado — indicar módulos listos vs. pendientes] |
| Flutter app completion | [COMPLETAR: % completado] |
| Hardware assembled (bench prototype) | [COMPLETAR: sí/no; si sí, foto/n.º de revisiones] |
| Calibration dataset | ❌ not yet — Garage week 1–2 target |
| Cloud dashboard | ❌ planned in Garage |
| DFM/manufacturing doc | ❌ planned in Garage (week 4) |

## 4. The 20-Day muShenzhen Garage Plan (Stage 1+ functional demo)

Garage dates: **Nov 29 – Dec 18, 2026** (4 working weeks). Every week ends with
a named, measurable deliverable pushed to the public repo.

**Week 1 — Board integration & calibration (Nov 30 – Dec 6)**
- Integrate the full stack on a single carrier PCB/breadboard-to-PCB build
  (ESP32-S3 + AD9833 + DRV8837 + bioimpedance ADC).
- Deliverable `W1-calibration-report.md`: current-pump accuracy curve
  (10/100/1000 µA setpoints vs. measured), DDS frequency sweep
  (0.1–100 kHz, RMS error), PEMF field measurement (µT @ coil surface).

**Week 2 — Functional bioimpedance & dataset (Dec 7–13)**
- Bring bioimpedance module to functional measurement on test phantoms
  (salt-gel / resistor-capacitor networks) and on-skin pilot loggers.
- Deliverable `W2-bioimpedance-dataset.csv` + capture script: ≥ [COMPLETAR:
  target number] labeled measurements across the 100 Ω–100 kΩ range with
  impedance-vs-frequency curves; ethics note for any human pilot logging.

**Week 3 — Flutter app + cloud dashboard (Dec 14–15)**
- BLE pairing, live impedance chart, protocol configuration, session export.
- Deliverable: app build (Android APK) + lightweight cloud dashboard
  ([COMPLETAR: stack — candidate: Tuya AIoT or Firebase]) showing sessions.

**Week 4 — Demos + DFM document (Dec 16–18)**
- **Demo A:** live biofeedback — impedance curve reacts to electrode contact
  and hydration on stage.
- **Demo B:** closed-loop script — read impedance → adjust protocol within
  safety envelope (wellness/research framing).
- **Demo C:** full BOM walkthrough — show the ~USD 25 parts list vs. a
  commercial device's price, and hand out the open-source repo QR.
- Deliverable `DFM-v0.1.md`: enclosure concept, PCB panelization notes,
  supplier candidates, per-unit cost at 100/1k/10k volumes.

## 5. What We Ask From Partners

| Partner | Concrete ask |
|---|---|
| **M5Stack** | CoreS3 / CoreS3-SE dev units; design review of the carrier board (the ESP32-S3 + display form factor is a natural host for BioHealy) |
| **Seeed Studio** | XIAO ESP32-S3 modules for a compact revision; Grove biosensor add-ons; **SenseCAP** channel to explore for the cloud/dashboard path |
| **ELEGOO** | 3D-printed enclosure prototyping (2–3 iterations during Garage); printing materials guidance for skin-contact-safe housings |
| **DFRobot** | Biosensors compatible with the ADC front-end; co-hosting a maker workshop during Maker Faire Shenzhen week |
| **Tuya** | AIoT cloud integration + SDK for the dashboard; guidance on module certification pathways for any future connectivity hardware |

For all partners: the platform is MIT-licensed; co-branding, joint
documentation, and joint demos are welcome. We integrate **your** silicon/modules
into a documented, reproducible open project with a public paper trail.

## 6. Compliance & Safety (CRITICAL)

- BioHealy is **NOT an approved medical device** — not FDA, not CE-MDR, not
  NMPA, not COFEPRIS. **No clinical use is promised or implied.**
- Positioning: **research platform / wellness / biofeedback instrumentation**
  for labs, universities, and hardware builders.
- Every firmware build enforces hard current limits within the verified
  envelope (≤ 1000 µA) and every app screen carries the disclaimer:
  *"Research and wellness instrument. Not a medical device. Not intended to
  diagnose, treat, cure, or prevent any disease."*
- Electrode hygiene and skin-contact guidance included in documentation.
- Future regulatory pathway (to **explore**, not to promise): COFEPRIS (Mexico)
  and NMPA (China) classifications for low-power stimulation/wellness devices;
  this is a research topic for 2027+, documented honestly as "unexplored."

## 7. IP Posture

- **Firmware + software:** MIT license (already applied in repo).
- **Hardware documentation:** open (schematics, BOM, enclosure files planned).
- **Potential patent:** calibration method combining real-time bioimpedance
  feedback with stimulation-parameter adaptation — [COMPLETAR: decide
  file/no-file before Garage; if filed, scope as method claim, keep platform
  open]. Any patent would not restrict the open-source platform baseline.

## 8. Success Metrics in 20 Days

| Metric | Target |
|---|---|
| Working integrated prototype at Garage demo day | ✅ required ("Stage 1+" functional demo) |
| Calibration report (W1) | published in repo |
| Labeled bioimpedance dataset (W2) | ≥ [COMPLETAR: n] records, public CSV |
| App + dashboard (W3) | APK installable + live dashboard link |
| DFM document (W4) | v0.1 with unit-cost model |
| Partner meetings with concrete follow-ups | ≥ [COMPLETAR: n] |
| Repo stars/forks during event period | baseline [COMPLETAR] → track |

---

## Internal notes (ES)

- Pendientes: completar % firmware/app, confirmar si hay hardware ensamblado real
  (con fotos) ANTES de presentar este dossier; no prometer demo A/B/C sin probar
  el demo B en bench.
- Definir número objetivo del dataset W2 y del stack del dashboard (Tuya vs
  Firebase) antes del 29 nov.
- Resolver el tema de la posible patente (método de calibración): decisión
  go/no-go previa al Garage.
- Decisión pendiente: Full Pass $179 vs Alumni $149 para muShenzhen (Garage
  $449 ya cubierto por la selección).
- Presupuesto de viaje total USD [COMPLETAR] — actualizar al cerrar vuelo
  CDMX–SZX, hospedaje, visa y seguro.
