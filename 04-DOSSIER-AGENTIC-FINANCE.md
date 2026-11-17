# Agentic Payment & Trust Infrastructure on Stellar
### SentinelX402 + voltx + STB Suite

**Dossier — Shenzhen 2026/2027 collaboration campaign**
**Author:** Fernando May Fuentes — B.Eng. Telematics Engineering, UPIITA-IPN (Mexico City)
ORCID 0009-0002-3953-5224 · GitHub: https://github.com/FernandoMay · LinkedIn: https://linkedin.com/in/fernandomay
**Status: all systems Testnet-only. No Mainnet claims.** Technical-debt items are
listed openly in Section 6.

---

## 摘要 (Chinese Executive Summary)

本项目展示了在 Stellar/Soroban 上构建"智能体支付与信任基础设施"的完整开源工作成果。
SentinelX402 是一套欺诈检测 API：基于 x402 v2 协议（stellar:testnet、
Coinbase facilitator、手续费赞助）实现真实链上"按请求付费"，
内置 16+ 欺诈模式库与 0–100 启发式评分；Next.js 16 + Prisma 实现，
配备能自主付费购买分析的智能体 demo，每笔支付都持久化真实 txHash。
STB Suite 为三个已部署的 Soroban 合约（¿SÍ O NEL?、TÓMBOLA、BANDERA ROJA），
全部有测试网部署证据与浏览器可查，配套 Flutter/Web 前端直连钱包，无任何 mock。
voltx 即时支付套件包含 9 个 Soroban 合约、71 个测试，
采用 passkey 账户抽象与社会恢复机制。
另有 NIKO SUN（RWA 光伏）、breadline-protocol（跨境微托管）、
proofdrop、reap-bounded-runtime（自治智能体的可编程经济权限层）。
SDF 学术研究资助（6 万美元/12 个月）与 SCF Build Award 均在申报草案阶段。
现寻求联合研究、中拉支付通道试点及 InnoX/XbotPark 孵化合作。

---

## 1. Thesis

Autonomous AI agents are starting to transact: paying for APIs, data, and
services in real time. The x402 protocol (HTTP-native pay-per-request) shows
the model works. But two things are missing from the current stack:

1. **Fraud screening must be native to the payment flow.** When an agent pays
   autonomously, a human cannot review each transaction. Fraud scoring and
   spend authorization must happen *inside* the request path — not as a
   bolted-on compliance report.
2. **Economic boundedness must be enforced at the contract layer.** Agents
   need programmable spending limits, escrow semantics with veto, and
   recoverable wallets — enforced on-chain, not promised by a prompt.

**Thesis:** the agentic economy needs payments, fraud detection, and trust
boundaries designed as one substrate. Stellar/Soroban is a strong settlement
layer for it: fast, cheap, and explicitly oriented to payments and inclusion.

## 2. The Stack

```
┌──────────────────────────────────────────────────────────────┐
│                    AGENT / USER APPLICATIONS                  │
├──────────────────────────────────────────────────────────────┤
│ TRUST LAYER                                                   │
│   SentinelX402 — fraud-scoring API (16+ patterns, 0–100 score)│
│   reap-bounded-runtime — programmable economic authority      │
│   for autonomous agents (spend caps, bounded execution)       │
├──────────────────────────────────────────────────────────────┤
│ PAYMENT LAYER (Stellar / Soroban, Testnet)                    │
│   x402 v2 pay-per-request · Coinbase facilitator · sponsored  │
│   fees · real txHash persisted per payment                    │
│   STB Suite: escrow/prediction/raffle/poll contracts          │
├──────────────────────────────────────────────────────────────┤
│ WALLET LAYER                                                  │
│   voltx — passkey account abstraction + social recovery +     │
│   instant payouts (9 Soroban contracts, 71 tests)             │
├──────────────────────────────────────────────────────────────┤
│ RWA / CROSS-BORDER EXPERIMENTS                                │
│   niko-sun-stellar (solar RWA) · breadline-protocol           │
│   (cross-border micro-escrow) · proofdrop                     │
└──────────────────────────────────────────────────────────────┘
```

**Component summary:**

| Component | What it is | Verified state |
|---|---|---|
| **SentinelX402** | Fraud-detection API with real x402 payments (protocol x402 v2 on stellar:testnet, Coinbase facilitator, sponsored fees); 16+ fraud patterns; heuristic scoring 0–100; Next.js 16 + Prisma; autonomous-agent demo that pays for its own analysis; persists real `txHash` per payment | Working demo (Testnet) |
| **STB Suite** | 3 Soroban contracts on Stellar Testnet with deploy evidence and explorers — **v2 (current, deployed 2026-11-17 after security hardening):** ¿SÍ O NEL? `CCOMYNE2QAOGYH62RVVEQXGQXD2S3RDQ2BCOL6WNCPCVR2Q4OQB6CNP7` · TÓMBOLA `CAQS6NWM7FYJZSJJ2CNSG2OMIHZEA7FF3QMNZP4K7PGENM2XUOD7SWLX` · BANDERA ROJA `CDZ3AMYKNNJ6MJJV4F5MROHZ3QDRZMINEZK5D6KCUFXNGQ5JVJQSAPTN`. v1 contracts are historical. TÓMBOLA v2 uses a real on-chain **Stellar VRF Oracle (drand quicknet)** — no mock provider. Flutter/Web frontend connected to wallet, **no mocks** | Deployed + evidence |
| **voltx** | Instant payouts; 9 Soroban contracts; 71 tests; passkey account abstraction + social recovery | Tested (Testnet) |
| **reap-bounded-runtime** | Programmable economic-authority layer for autonomous agents | [COMPLETAR: current completion level] |
| **niko-sun-stellar** | Solar RWA concept/prototype | SCF Build Award draft stage |
| **breadline-protocol** | Cross-border micro-escrow | [COMPLETAR: status] |
| **proofdrop** | [COMPLETAR: one-line description] | [COMPLETAR: status] |

## 3. Evidence

- STB Suite contract IDs are re-checkable on Stellar explorers (listed above);
  E2E matrices record 12/12, 13/13, 11/11 on-chain flows with real txHashes and
  ledger numbers; frontend signs via wallet integration with human-readable
  transaction errors.
- voltx: 71 passing tests across 9 contracts (passkey AA + social recovery).
- SentinelX402: every paid analysis run stores its real on-chain `txHash`.
- Supporting documents in the workspace: `submission/SDF-ACADEMIC-GRANT.md`,
  `INFORME-FINAL.md`, `apps/PRODUCT-AUDIT.md` (audit-dated findings, kept public
  by design: "evidence over claims").

## 4. Why It Matters for China

- **Cross-border commerce:** China–LATAM trade runs on payment rails that are
  expensive and slow for small tickets. On-chain micro/settlement layers with
  escrow semantics (breadline-protocol, STB Suite) are a research path that
  complements, not replaces, domestic rails.
- **Agent-to-agent payments:** Chinese AI stack is moving toward autonomous
  agents in commerce and IoT. x402-style pay-per-request + fraud scoring +
  spend bounds (SentinelX402 + reap-bounded-runtime) is directly aligned with
  the direction x402/Coinbase is pushing globally.
- **RWA:** tokenized real-world assets (niko-sun-stellar: solar) intersect with
  China's RWA pilots in Hong Kong/Shenzhen [COMPLETAR: cite specific program if
  used in outreach].
- Wallet UX: passkey account abstraction + social recovery (voltx) addresses
  the same onboarding friction Chinese super-apps solved for consumers — the
  agentic version needs it even more.

## 5. The Ask

| Partner type | Concrete proposal |
|---|---|
| **Co-research (universities / labs)** | Joint study on agent-payment safety: labeled agent-fraud dataset (extending the 16-pattern corpus), Soroban bounded-payment experiments; publishable jointly |
| **Payment gateways (China ↔ LATAM)** | Sandbox pilot: cross-border micro-escrow flows (breadline-protocol pattern) measured against existing remittance rails [COMPLETAR: named pilot companies] |
| **Incubators: InnoX / XbotPark** | Incubation for the agentic-payments stack as a venture (open-core: contracts open, product layer commercial) [COMPLETAR: program dates/contacts] |
| **Stellar ecosystem** | SDF Academic Research Grant (USD 60k / 12 months) — draft ready; SCF Build Award (NIKO SUN) — draft stage; seeking reviewers/sponsors for submission |

## 6. Honest Status (read before partnering)

- **Testnet only.** Nothing here runs on Mainnet; no Mainnet claims are made
  anywhere in this dossier.
- **Known technical debt — status as of 2026-11-17:**
  1. **CLOSED:** the previously reported unauthenticated `initialize` was
     eliminated on 2026-11-17 — all three contracts were redeployed with
     immutable `__constructor` state (Soroban SDK 29.0.1); `initialize` no
     longer exists as an invocable function (verified).
  2. **CLOSED:** TÓMBOLA verifiable randomness — the v2 contract binds a real
     on-chain Stellar VRF Oracle (drand quicknet); the mock path is inactive.
  3. **OPEN:** TS bindings for the v2 WASM must be regenerated and web/Flutter
     E2E re-run against the v2 contract IDs; the public `stb-suite` hub still
     lists v1 identifiers until that is done.
  4. **OPEN:** no external security audit on any contract; all evidence is
     Testnet-only.
- External wallet integration (Freighter/WalletConnect on mobile) is partially
  blocked pending a Stellar WalletConnect v2 client in the Dart ecosystem;
  internal SEP-0005 wallet path works.
- Products are pre-release: admin positive flows need a completed privileged
  test run; external QA items documented in `apps/PRODUCT-AUDIT.md`.

We list these items deliberately: partners should trust the evidence *because*
the limitations are published.

## 7. Roadmap 2027

| Quarter | Milestone |
|---|---|
| Q1 2027 | Regenerate v2 TS bindings + full E2E; update public `stb-suite` hub; submit SDF Academic Research Grant; launch agent-fraud dataset collection (P2) |
| Q2 2027 | Bounded-payment runtime on Soroban (P3): economic authority limits + escrow-with-veto; first benchmarks |
| Q3 2027 | Passkey usability study with non-banked users in Mexico (P4, with MIRAI as study vehicle); cross-border pilot discussion with [COMPLETAR] |
| Q4 2027 | Peer-reviewed outputs (2 papers target); open reference implementation v1; reassess Mainnet readiness — only after independent audit |

---

## Internal notes (ES)

- El issue del initializer ya está CERRADO (redeploy 2026-11-17 con
  `__constructor`); el bloqueador actual es actualizar el hub público
  `stb-suite` (aún lista contract IDs v1) y regenerar bindings/E2E contra v2
  ANTES de cualquier reunión seria con partners.
- TÓMBOLA v2 ya usa Stellar VRF Oracle real (drand quicknet); mantener la
  afirmación coherente en todo material público (nada de "mock").
- [COMPLETAR: contactos concretos en InnoX / XbotPark / pasarelas de pago] —
  buscar intros vía muShenzhen/Garage.
- SDF grant: completar checklist de pre-envío (CV, proof Springer, resumen ES,
  carta de afiliación si aplica) — ver `submission/SDF-ACADEMIC-GRANT.md`.
- Actualizar estado de reap-bounded-runtime / breadline / proofdrop para quitar
  los [COMPLETAR] antes de enviar.
- Presupuesto de viaje total USD [COMPLETAR] — actualizar al cerrar vuelo,
  hospedaje, visa y seguro.
