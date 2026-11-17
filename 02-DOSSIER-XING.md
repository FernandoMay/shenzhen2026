# XING — Agentic Cognitive Infrastructure for Distributed Multimodal Intelligence

**Research dossier — Shenzhen 2026/2027 collaboration campaign**
**Author:** Fernando May Fuentes — B.Eng. Telematics Engineering, UPIITA-IPN (Mexico City)
ORCID 0009-0002-3953-5224 · GitHub: https://github.com/FernandoMay · LinkedIn: https://linkedin.com/in/fernandomay · Email: fmay130@gmail.com

**Verified repos:**
- https://github.com/FernandoMay/xing-core (Python)
- https://github.com/FernandoMay/xing-iccia2026 (IEEE ICCIA 2026 paper package)
- https://github.com/FernandoMay/xing-adan-resilience (resilience work)

---

## 摘要 (Chinese Executive Summary)

XING（eXecutable INtelligent Graph）是一个开源的多智能体系统（MAS）认知基础设施，
旨在解决当前智能体系统缺乏可审计性这一核心问题：提供双时间线（bi-temporal）记忆、
全程溯源追踪（provenance）、确定性执行语义与自愈能力。
项目包含正式规范框架（RFC 流程）、参考运行时与多语言 SDK，
架构分为四层：Kernel（规划器/调度器/上下文管理）→ Runtime（执行引擎 +
WASM 沙箱）→ Fabric（MCP 总线、事件总线、API 网关）→ Memory（工作/情景/语义图）。
配套的 IEEE ICCIA 2026 论文包提供完整随机模拟器（numpy/networkx/scipy）、
自愈 DAG 生命周期、语义记忆织物与成本模型的实验数据和可复现脚本。
作者拥有 Springer WITCOM 2025 发表，并有 2025–2027 年约 20 篇 IEEE/Springer
论文的活跃研究管线。
现寻求：SLAI Global Deep Sight 2027 研究项目合作、InnoX NexTech 孵化、
Sipeed（K210/MaixCAM 基准测试）与 Tuya（AIoT 智能体编排）的技术合作。

---

## 1. Research Problem

Current multi-agent systems (MAS) work well in demos but lack the properties
needed for **production, auditable deployments**:

- **Memory** is bolted on (vector stores with no temporal semantics), so agents
  cannot answer "what did I know *when*?".
- **Provenance** is absent: no per-decision record of which context, which
  model, which tool call produced an output.
- **Execution semantics** are non-deterministic: identical agent graphs replay
  differently, making debugging, regression testing, and audit impossible.
- **Self-healing** is anecdotal: when a subtask or node fails mid-DAG, the
  system has no principled recovery model.

**Claim:** agentic systems need a **cognitive infrastructure layer** — the way
databases underlie applications and schedulers underlie operating systems.
XING is that layer: an open, formally specified substrate for multi-agent
execution with auditable memory, provenance, and deterministic semantics.

## 2. Architecture

XING (`xing-core`) is organized in four layers:

```
┌─────────────────────────────────────────────────────────────┐
│ KERNEL                                                       │
│   Planner · Scheduler · Context Manager                      │
│   (goal decomposition, resource allocation, context windows) │
├─────────────────────────────────────────────────────────────┤
│ RUNTIME                                                      │
│   Execution Engine · WASM Sandbox Manager                    │
│   (deterministic semantics, tool isolation)                  │
├─────────────────────────────────────────────────────────────┤
│ FABRIC                                                       │
│   MCP Bus · Event Bus · API Gateway                          │
│   (agent-to-tool interconnect, streaming, external ingress)  │
├─────────────────────────────────────────────────────────────┤
│ MEMORY                                                       │
│   Working · Episodic · Semantic-Graph                        │
│   (bi-temporal memory: valid-time + tx-time per fact)        │
└─────────────────────────────────────────────────────────────┘
```

Engineering disciplines applied in `xing-core`:

| Discipline | Implementation |
|---|---|
| Formal specification | RFC process for the graph + execution semantics spec |
| Reference runtime | Python reference implementation of the spec |
| Deterministic execution | defined semantics for replay-identical runs |
| Bi-temporal memory | every fact carries validity time and transaction time |
| Full provenance | per-node trace: inputs, model, tool calls, outputs |
| SDKs | client SDKs for embedding agents on the runtime |

## 3. Evidence

The `xing-iccia2026` repository is the paper package for
**"XING: An Agentic Cognitive Infrastructure for Distributed Multimodal
Intelligence and Adaptive AI Orchestration"** (IEEE ICCIA 2026). It contains:

- A **complete stochastic simulator** (numpy / networkx / pandas / matplotlib /
  scipy) of agent-graph workloads.
- **Figures** with generated sources: self-healing DAG lifecycle, semantic
  memory fabric, Responsible-AI (RAI) comparison, GRE (graph recovery/
  enforcement) self-healing, and cost & CRL (cognitive resource load) curves.
- **Raw experimental data** as CSV files.
- **Replication notes** so any reviewer can regenerate every figure.

This is a working evidence discipline, not a concept deck. It complements the
applicant's active research line of **~20 IEEE/Springer packages (2025–2027)**
spanning semantic communication, THz covert detection, quantum cognitive
networking, ISAC, and agentic science — anchored by the Springer WITCOM 2025
publication: *"NeuroDigital Interfaces and Adaptive Cognitive Networking:
Towards a Human-AI Telepathic Framework"* (DOI 10.1007/978-3-032-09735-4_6).

## 4. The Ask, by Destination

| Destination | Concrete proposal |
|---|---|
| **SLAI Global — Deep Sight Research Program 2027** | Cohort 1: **Feb 22 – May 14, 2027**; Round 2: **Jun 1 – Aug 20, 2027**. Open to international undergrad/master researchers; housing provided + possible travel grant [COMPLETAR: confirm exact grant terms]. Proposal: supervised research project — **extend XING with edge-AI orchestration** (routing agent graphs onto edge devices) and evaluate on **Chinese edge hardware** (Sipeed K210/MaixCAM, Tuya modules), producing benchmarks + a paper. |
| **InnoX NexTech** | XING as the **core of an agentic-infrastructure startup**: open-core spec/runtime, commercial SDKs and enterprise deployment tooling. Seeking entry into the program with this thesis. |
| **Sipeed** | Joint benchmarks: XING runtime scheduling lightweight agent graphs on **K210 / MaixCAM**; publish results as open report + ICCIA follow-up. [COMPLETAR: contact channel] |
| **Tuya** | Agentic orchestration over **Tuya AIoT**: XING as the coordination layer for agent-controlled device routines; joint demo at Maker Faire Shenzhen week. [COMPLETAR: contact channel] |

## 5. Deliverables 2027

1. **Survey paper:** agentic cognitive infrastructure — memory, provenance,
   deterministic execution, self-healing (systematic mapping).
2. **Dataset:** agent-graph execution traces (provenance + recovery events)
   released openly.
3. **Reference implementation:** extended XING runtime with edge-AI
   orchestration target (v0.2 spec + RFCs).
4. **Peer-reviewed paper** at an IEEE/ACM venue presenting benchmarks and
   findings (building on the ICCIA 2026 package).

## 6. IP Posture (open-core)

| Component | License posture |
|---|---|
| Formal spec + RFCs | open |
| Reference runtime (`xing-core`) | open source |
| Paper packages, datasets, figures | open, reproducible |
| SDKs, enterprise connectors, ops tooling | closed / commercial (future) |

No transfer of the open core. Commercialization happens on top of the
open substrate, keeping the research layer citable and auditable.

## 7. Fit With the Shenzhen Ecosystem

Why this research travels well to Shenzhen partners:

- **Edge-AI density:** Shenzhen hosts the strongest ecosystem of low-cost AI
  edge boards (Sipeed K210/MaixCAM, Tuya modules, ESP-family from Espressif
  partners). XING's deterministic, small-footprint runtime semantics are a
  natural match for orchestrating agent graphs across such devices — the
  planned SLAI/edge research track would evaluate exactly this.
- **Manufacturing-to-agent loop:** the same factories producing the hardware
  will soon run agentic software on it. A spec-first infrastructure with
  provenance and replay makes industrial agent deployments auditable — a
  property industrial buyers will require.
- **Event cadence:** muShenzhen Garage (Nov 29 – Dec 18, 2026), Maker Faire
  Shenzhen (Dec 12–13, Vanke Design Commune), and the ICCIA 2026 paper give
  three concrete contact points within one trip window.

**Honest scope note:** XING is research infrastructure. It is not presented as
a production product; partner conversations should treat it as a joint research
/ co-benchmarking opportunity in 2027, with commercialization via InnoX NexTech
only after the reference implementation and paper deliverables land.

## 8. Risks & Mitigations

| Risk | Mitigation |
|---|---|
| Runtime maturity vs. claims | Dossier cites only repo-verified artifacts (spec, runtime, simulator, data); no production claims |
| Paper acceptance not yet confirmed | ICCIA 2026 package is complete and reproducible; fallback venues exist in the active pipeline (~20 IEEE/Springer packages 2025–2027) |
| Partner interest in edge benchmarks uncertain | Proposal is modular: Sipeed benchmark, Tuya orchestration, and SLAI edge track are separable deliverables |
| Timezone/distance for supervision | SLAI program is residential (housing provided); [COMPLETAR: confirm on-site requirements] |

---

## Internal notes (ES)

- Confirmar fecha exacta y términos del travel grant de SLAI Deep Sight 2027
  antes de enviar la postulación (ronda 1: 22 feb–14 may; ronda 2: 1 jun–20 ago).
- [COMPLETAR: contactos reales en Sipeed y Tuya] — buscar canales por muShenzhen/
  Maker Faire; sin contacto, no enviar frío.
- Verificar estado actual de `xing-core` (RFCs escritos vs. faltantes) para no
  sobreprometer en el dossier enviado.
- Preparar traducción al chino del resumen del paper ICCIA para reuniones.
- Linkear este dossier con 03-DOSSIER-MIRAI (XING como tema de curso) si aplica.
