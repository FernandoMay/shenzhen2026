# MIRAI — Bilingual AI Education Platform (ES/ZH) for Builders

**Concept dossier — muShenzhen 2026 (Human Flourishing / Future Education track)**
**Author:** Fernando May Fuentes — B.Eng. Telematics Engineering, UPIITA-IPN (Mexico City)
ORCID 0009-0002-3953-5224 · GitHub: https://github.com/FernandoMay · LinkedIn: https://linkedin.com/in/fernandomay

**Status: concept + first pilots [COMPLETAR: especificar estado real de pilotos].**
MIRAI does **not** yet have a public repo or published material. What exists today:
it is cited as the study vehicle in the SDF Academic Research Grant draft
(phase P4: usability study of passkey agent wallets for non-banked users in
Mexico), and it aligns with the **Human Flourishing / Future Education** track
of muShenzhen. This dossier is honest about that stage and proposes concrete,
verifiable 20-day deliverables to materialize it.

---

## 摘要 (Chinese Executive Summary)

MIRAI 是一个面向"建设者（builders）"的双语（西语/中文）AI 教育项目概念，
目前处于概念阶段：已被写入 SDF 学术研究资助草案（P4 阶段，
以 MIRAI 为研究载体，在墨西哥非银用户群体中开展 passkey 智能体钱包可用性研究），
并与 muShenzhen 的"人文繁荣/未来教育"赛道对齐。项目尚无公开仓库，
本文件如实说明这一状态。
核心主张：拉美需要的不是"谈论 AI"的教育，而是"用 AI 动手构建"的教育——
课程模块覆盖硬件/IoT、智能体（agents）、链上金融科技，每个模块都以一个
可演示项目收尾。
在 muShenzhen 的 20 天里，目标交付物为：一个已文档化的试点课程模块、
一场 2 小时的现场工作坊（人文繁荣赛道），以及一套开源课程 kit。
诚邀 Seeed Studio（教育硬件套件）、柴火创客空间（合办工作坊）、
深圳高校与拉美伙伴共同将其落地。

---

## 1. Problem

Latin America has massive AI **consumption** but thin AI **production**:

- Universities teach theory; industry demand is for people who can *ship*:
  wire a sensor, train a small model, deploy an agent, integrate a payment API.
- English-only learning materials lock out a large Spanish-speaking builder
  population; meanwhile the hardware, toolchains, and best pedagogy are largely
  produced in China (Shenzhen especially).
- There is no structured bilingual (ES/ZH) bridge that teaches builders to use
  Shenzhen-grade hardware and modern AI tooling — despite the natural two-way
  opportunity (Chinese hardware + LATAM builders).

**Gap:** builders in LATAM need to learn to **build with AI** — not merely
consume it — with materials in their own language and with hardware they can
actually afford.

## 2. Concept

**MIRAI** = a bilingual (Spanish/Chinese) education program for builders,
structured as hands-on curriculum modules, each ending in a demonstrable
project:

| Module | Track | Demonstrator project (per module) |
|---|---|---|
| M1 | Hardware / IoT | program an ESP32-class board with sensors; publish telemetry to a dashboard |
| M2 | Agents | build a small multi-agent workflow (uses **XING** material as reference) |
| M3 | Fintech on-chain | build a wallet + payment flow with **passkey** UX (uses the SDF P4 study materials; see Dossier 04) |
| M4 | Applied bio / health instrumentation | non-clinical biofeedback telemetry with **BioHealy** as course material (see Dossier 01) |

Design principles:

- **Bilingual from day one:** every lesson ships in ES + ZH (EN as bridge).
- **Project-first:** no module without a working demo artifact.
- **Open curriculum:** materials under an open license, forkable by schools.
- **Honest AI:** teach limits, failure modes, and verification habits, not hype.

## 3. 20-Day Deliverable in muShenzhen (Nov 29 – Dec 18, 2026)

Three concrete artifacts, doable within the trip window:

1. **Documented pilot module:** Module M1 (Hardware/IoT) fully written in ES+ZH,
   with step-by-step build, photos, and a recorded demo — published as the
   seed of the open curriculum repo.
2. **2-hour in-person workshop** in the **Human Flourishing / Future Education**
   track: "Build your first AI hardware project in 2 hours" (ESP32 + a sensor +
   a tiny AI service), bilingual delivery, with participants keeping the
   workspace files.
3. **Open-source curriculum kit:** repo skeleton (lesson template, bilingual
   style guide, module roadmap, hardware BOMs), released under an open license
   so Shenzhen organizations and LATAM schools can co-build.

## 4. The Ask

| Partner | Concrete ask |
|---|---|
| **Seeed Studio** | **Academic support**: classroom hardware kits (XIAO/Grove) to seed pilot classrooms in Mexico/LATAM; guidance on education SKUs |
| **Chaihuo ( maker space )** | Co-host the 2h workshop during muShenzhen; venue + facilitation know-how; ongoing exchange with LATAM maker communities |
| **Shenzhen universities** | Content exchange: translate/adapt one module each way (ES↔ZH); student project exchange | [COMPLETAR: named universities/contact points]
| **LATAM allies** | Pilot classrooms and workshop hosts in Mexico; local language QA of the ES materials | [COMPLETAR: named institutions]

## 5. Link With the Other Lines

MIRAI is the **education vehicle** for the portfolio, not an isolated project:

- **BioHealy** (Dossier 01) → course material for applied instrumentation
  (research/wellness framing, with the same compliance disclaimers).
- **STB Suite / agentic finance** (Dossier 04) → Module M3 fintech content and
  the SDF P4 usability study vehicle (passkey wallets for non-banked users).
- **XING** (Dossier 02) → Module M2 agent content.

This gives MIRAI immediate, verified teaching content built from real projects —
an advantage typical education initiatives do not have.

### What a module looks like (template for M1 and later modules)

Every module follows the same skeleton so Shenzhen and LATAM partners can
co-author modules independently:

1. **Lesson (ES + ZH, EN bridge):** 30–60 min of material, hardware photo-led.
2. **Build lab:** step-by-step wiring/programming with expected outputs at
   each step (so a self-learner can verify progress).
3. **Demo project:** the module's artifact — something that works on a desk
   and can be shown on video in < 3 minutes.
4. **Safety & honesty box:** what the project is NOT (e.g., BioHealy modules
   carry the research/wellness disclaimer verbatim; fintech modules state
   Testnet-only until audit).
5. **Assessment:** a checklist the learner self-scores; completion = working
   demo, not a quiz.

### Success metrics (pilot phase)

| Metric | Target |
|---|---|
| Published pilot module (M1, ES+ZH) | 1, before/during muShenzhen |
| In-person workshop delivered | 1 (2h, Human Flourishing track) |
| Curriculum kit (repo + template + BOMs) | public, open license |
| Workshop participants | tracked with feedback form [COMPLETAR: target n] |
| Shenzhen partner commitments (Seeed/Chaihuo/university) | ≥ 1 written |
| LATAM pilot classroom (Mexico) | ≥ 1 identified with date [COMPLETAR] |

| Risk | Mitigation |
|---|---|
| No repo/materials exist yet (concept only) | 20-day deliverables are scoped to produce the repo + 1 module + 1 workshop, all verifiable by Dec 18, 2026 |
| Translation quality | ZH review by native speaker [COMPLETAR: who]; machine drafts never ship unreviewed |
| Workload overlap with Garage/BioHealy | MIRAI focus kept to week 3; workshop slotting coordinated with muShenzhen team |
| Overpromising to education partners | All partner asks are material-specific and small (kits, one venue, one exchange) |

## 6. Next Steps to Materialize

1. Create the public repo + brand kit (`mirai-*`): [COMPLETAR: repo name].
2. Publish Module M1 pilot (ES+ZH) — target: before or during muShenzhen.
3. Run the first 2h workshop (muShenzhen, Human Flourishing track).
4. Recruit 1 Shenzhen partner (Seeed/Chaihuo) + 1 LATAM pilot classroom.
5. Post-Garage: define M2/M3 timelines and a funding path
   [COMPLETAR: grant/institutional options].

---

## Internal notes (ES)

- NO existe repo ni material público todavía — mantener la honestidad de esta
  página hasta que se publique; no enviar este dossier a nadie antes de tener
  al menos el esqueleto del repo.
- Confirmar qué pilotaje (si alguno) ya ocurrió en México antes del
  [COMPLETAR: fecha] para poder actualizar el campo "Status".
- Coordinar la propuesta del taller 2h con el equipo de muShenzhen (track
  Human Flourishing) — fechas y logística pendientes.
- Traducción ES→ZH del Módulo M1: necesita revisor nativo [COMPLETAR: quién].
- Presupuesto de viaje total USD [COMPLETAR] — actualizar al cerrar vuelo,
  hospedaje, visa y seguro.
