# 05-PITCH-DECK — Fernando May Fuentes · Shenzhen 2026

> Bilingual pitch deck (English | 简体中文). Visual version: `06-PITCH-DECK.html`.
> Integrity note at bottom of deck. Unknown facts marked `[COMPLETAR: …]` — nothing invented.

---

## Slide 1 — Cover: Builder Profile · Shenzhen 2026 | 封面：创客档案 · 深圳 2026

| EN | 中文 |
|---|---|
| **Fernando May Fuentes** — Builder Profile · Shenzhen 2026 | **Fernando May Fuentes** — 创客档案 · 深圳 2026 |
| B.Eng. Telematics Engineering (UPIITA-IPN, Mexico City). Software + hardware + research builder. | 电信工程学士（墨西哥 IPN-UPIITA）。软件 + 硬件 + 科研型创客。 |
| GitHub: github.com/FernandoMay · LinkedIn: linkedin.com/in/fernandomay · ORCID: 0009-0002-3953-5224 · Email: **fmay130@gmail.com** | GitHub / LinkedIn / ORCID 同左 · 邮箱：**fmay130@gmail.com** |
| **Badge: muShanghai 2026 Co-Creator** (May 10 – Jun 6, Alibaba Hongqiao Center) | **徽章：muShanghai 2026 联合发起人**（5月10日–6月6日，阿里虹桥中心） |
| Trip: muShenzhen, Nov 29 – Dec 18 2026 · C2 Hub OCT-LOFT North | 行程：muShenzhen，2026年11月29日–12月18日 · OCT-LOFT 北区 C2 Hub |

---

## Slide 2 — Who I Am | 我是谁

| EN | 中文 |
|---|---|
| **Timeline:** CECyT 3 → UPIITA-IPN (Telematics) → Mobile industry: iOS at Citi (private bank), medical training apps at Intersistemas, hearing-wellness Flutter app at Supernova Apps → IEEE/Springer research 2025–2027 → muShanghai Co-Creator 2026. | **时间线：** CECyT 3 → IPN-UPIITA（电信工程）→ 移动行业：花旗 iOS（私行）、Intersistemas 医疗培训应用、Supernova 听力健康 Flutter 应用 → 2025–2027 IEEE/Springer 研究 → 2026 muShanghai 联合发起人。 |
| Beihang University experience: **[COMPLETAR: programa, fechas, professor — no verificable públicamente; debe documentarse]** | 北航经历：**[待补全：项目、时间、导师 — 公开渠道无法核实；需提供文件]** |
| Strength: **software + hardware + research** in one builder. | 优势：**软件 + 硬件 + 科研**，集于一身。 |

---

## Slide 3 — What I'm Building | 我在做什么

| Línea (EN) | Repo | Estado | 中文简介 | Ask |
|---|---|---|---|---|
| 1. BioHealy — reconfigurable bio-stimulation + real-time bioimpedance | github.com/FernandoMay/biohealy-ipn | Working prototype, open source (C++, MIT) | 可重构生物刺激 + 实时生物阻抗平台，BOM ~$25 vs 商业 $500–5000 | Dev kits: M5Stack / Seeed / ELEGOO / DFRobot / Tuya |
| 2. XING — open cognitive infrastructure for multi-agent systems | github.com/FernandoMay/xing-core | Kernel + runtime; ICCIA 2026 paper | 多智能体系统的开源认知基础设施（内核/运行时/记忆/溯源） | SLAI / InnoX / Sipeed / Tuya |
| 3. MIRAI — bilingual ES/ZH builder education platform | — | Concept + first workshop | 面向创客的中西双语教育平台；SDF 学术资助可用性研究载体 | Partners for pilot workshop |
| 4. Agentic Finance — SentinelX402 / voltx / STB Suite | github.com/FernandoMay | Testnet, 16+ fraud patterns, 71 tests | 智能体金融：x402 真实链上支付 + Soroban 合约（仅测试网） | Ecosystem visibility |

---

## Slide 4 — BioHealy Deep-Dive | BioHealy 详解

| EN | 中文 |
|---|---|
| **Reconfigurable bio-stimulation platform:** ESP32-S3 + BLE 5 · AD9833 DDS → Howland current pump (10–1000 µA @ 0.1–100 kHz) · DRV8837 H-bridge + planar coil (PEMF ≤100 µT @ 1–10 kHz) · ADC bioimpedance (100 Ω–100 kΩ) · Flutter app. | **可重构生物刺激平台：** ESP32-S3 + BLE 5 · AD9833 DDS → Howland 恒流源（10–1000 µA @ 0.1–100 kHz）· DRV8837 H 桥 + 平面线圈（PEMF ≤100 µT @ 1–10 kHz）· ADC 生物阻抗（100 Ω–100 kΩ）· Flutter 应用。 |
| **BOM ~$25 USD** vs commercial $500–5000. Open source (C++, MIT). | **物料成本约 $25 美元**，商业设备 $500–5000。开源（C++，MIT）。 |
| Honest position: research / wellness / biofeedback platform — **NOT an approved medical device**. | 诚实定位：科研/健康/生物反馈平台——**非获批医疗设备**。 |
| **Ask:** dev kits + review from M5Stack, Seeed, ELEGOO, DFRobot, Tuya. | **诉求：** M5Stack、Seeed、ELEGOO、DFRobot、Tuya 提供开发套件与技术评审。 |

---

## Slide 5 — XING Deep-Dive | XING 详解

| EN | 中文 |
|---|---|
| **Open-source cognitive infrastructure for multi-agent systems** (github.com/FernandoMay/xing-core). | **面向多智能体系统的开源认知基础设施**（github.com/FernandoMay/xing-core）。 |
| 4-layer architecture: ① Kernel — planner / scheduler / context · ② Runtime + WASM sandbox · ③ Fabric — MCP bus / event bus / API gateway · ④ Memory — working / episodic / semantic-graph, bi-temporal, provenance, deterministic execution, RFCs. | 四层架构：① 内核——规划器/调度器/上下文 · ② 运行时 + WASM 沙箱 · ③ Fabric——MCP 总线/事件总线/API 网关 · ④ 记忆——工作/情景/语义图记忆，双时态，溯源，确定性执行，RFC 流程。 |
| Paper accepted track: **IEEE ICCIA 2026** + stochastic simulator + data. ~20 IEEE/Springer packages 2025–2027. | **IEEE ICCIA 2026** 论文 + 随机模拟器 + 数据。2025–2027 约 20 项 IEEE/Springer 成果。 |
| **Ask:** SLAI / InnoX / Sipeed / Tuya — edge AI hardware + community. | **诉求：** SLAI / InnoX / Sipeed / Tuya——边缘 AI 硬件与社区支持。 |

---

## Slide 6 — MIRAI + Agentic Finance | MIRAI 与智能体金融

**MIRAI (EN):** Bilingual ES/ZH education platform for builders. Status: concept + first workshop delivered. Vehicle for the SDF Academic Grant usability study. Fits muShenzhen's Human Flourishing track. **Ask:** partners for a pilot workshop in Shenzhen.
**MIRAI（中文）：** 面向创客的中西双语教育平台。状态：概念验证 + 首场工作坊。SDF 学术资助可用性研究的载体，契合 muShenzhen「人类繁荣」方向。**诉求：** 深圳试点工作坊合作方。

**Agentic Finance (EN):** SentinelX402 — fraud-scoring API with REAL on-chain x402 payments (v2, stellar:testnet, Coinbase facilitator, 16+ fraud patterns, txHash persisted). voltx — 9 Soroban contracts, 71 tests, passkey + social recovery. STB Suite — 3 contracts on Testnet with explorers. **Ask:** ecosystem visibility.
**智能体金融（中文）：** SentinelX402——欺诈评分 API，真实链上 x402 支付（v2，stellar 测试网，Coinbase facilitator，16+ 欺诈模式，txHash 持久化）。voltx——9 个 Soroban 合约、71 个测试、passkey + 社交恢复。STB Suite——3 个合约部署于测试网。**诉求：** 生态可见度。

---

## Slide 7 — Why Shenzhen / Why These 20 Days | 为什么是深圳 / 为什么是这 20 天

| EN | 中文 |
|---|---|
| muShenzhen Garage plan, Nov 29 – Dec 18, C2 Hub OCT-LOFT North. Maker Faire Shenzhen Dec 12–13 (Vanke Design Commune, Chaihuo/Seeed). | muShenzhen Garage 计划：11月29日–12月18日，OCT-LOFT 北区 C2 Hub。深圳制汇节 12月12–13日（万科设计公社，柴火/Seeed 主办）。 |
| **W1:** arrival + BioHealy kit assembly with local parts. **W2:** firmware + app hardening, live bioimpedance demo. **W3:** Maker Faire demo day + XING paper work + partner meetings. **Final:** hand-off docs + video. | **第1周：** 抵达 + 用本地器件组装 BioHealy。**第2周：** 固件与应用打磨，实时生物阻抗演示。**第3周：** 制汇节演示日 + XING 论文 + 伙伴会谈。**收尾：** 交接文档 + 视频。 |
| Show **today:** repos, prototype, ICCIA paper. Show **Dec 18:** field-tested Shenzhen build, bilingual docs, demo video. | **今天可展示：** 代码库、原型、ICCIA 论文。**12月18日交付：** 深圳实测版本、双语文档、演示视频。 |

---

## Slide 8 — What I Offer Partners | 我能为伙伴提供什么

| EN | 中文 |
|---|---|
| ✅ Dev kits validated in a real project + open-source documentation. | ✅ 在真实项目中验证的开发套件 + 开源文档。 |
| ✅ Visibility among international builders (muShanghai alumni network, IEEE/Springer). | ✅ 国际创客圈的曝光（muShanghai 校友网络、IEEE/Springer）。 |
| ✅ Health / IoT / agents use case, bilingual (ES/ZH) content. | ✅ 健康 / IoT / 智能体用例，中西双语内容。 |
| **Option A (minimal):** kits + technical review. **Option B (medium):** co-branded build + workshop. **Option C (ambitious):** industrial/research collaboration with agreement. | **方案 A（基础）：** 提供套件 + 技术评审。**方案 B（进阶）：** 联名开发 + 工作坊。**方案 C（深度）：** 产业/科研合作并签署协议。 |

---

## Slide 9 — Travel Budget & Ask | 行程预算与诉求

| Item (EN) | Cost | 中文 |
|---|---|---|
| Flight CDMX–SZX | **[COMPLETAR]** | 机票（墨西哥城–深圳） |
| Lodging, ~20 nights | **[COMPLETAR]** | 住宿，约 20 晚 |
| Visa + insurance | **[COMPLETAR]** | 签证 + 保险 |
| Tickets (Full Pass $179 / muShanghai Alumni $149 / Garage $449) | $179–449 | 门票（全通 $179 / muShanghai 校友 $149 / Garage $449） |
| **Total** | **USD [COMPLETAR]** | **合计** |

**Ask (EN):** intro to sponsors, hardware kits, or co-funding. **诉求（中文）：** 赞助方引荐、硬件套件，或联合出资。

---

## Slide 10 — Close | 结语

| EN | 中文 |
|---|---|
| Let's build the hardware-software-research bridge between Mexico and Shenzhen. | 让我们共建墨西哥与深圳之间的「软硬件 + 科研」之桥。 |
| GitHub: github.com/FernandoMay *(QR in visual deck)* · LinkedIn: linkedin.com/in/fernandomay · ORCID: 0009-0002-3953-5224 · Email: **fmay130@gmail.com** | GitHub / LinkedIn / ORCID 同左（视觉版含二维码） · 邮箱：**fmay130@gmail.com** |
| Final line: **"Four lines of work. One builder. Twenty days in Shenzhen."** | 结语：**「四条产线，一位创客，深圳二十天。」** |

---

### Integrity note (deck footer) | 诚信声明（页脚）

> All on-chain evidence is **Stellar Testnet**. No claims of Mainnet or medical-device approval. BioHealy is a research/wellness/biofeedback platform, not an approved medical device. Beihang University details pending documentation: **[COMPLETAR]**. Figures marked [COMPLETAR] are not yet verified.
>
> 所有链上证据均为 **Stellar 测试网**。未主张主网或医疗设备审批。BioHealy 为科研/健康/生物反馈平台，非获批医疗设备。北航经历待补充文件：**[待补全]**。标注 [待补全] 的数字尚未核实。
