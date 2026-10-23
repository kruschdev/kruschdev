<div align="center">

  <img src="assets/banner.svg" alt="Kevin Ruschman — @kruschdev" width="100%" />

  <br/><br/>

  [![Website](https://img.shields.io/badge/Website-krusch.dev-00e5ff?style=for-the-badge&logo=googlechrome&logoColor=060913)](https://krusch.dev)
  [![Tech Stack](https://img.shields.io/badge/2026_Stack-Architecture_Blueprint-7c4dff?style=for-the-badge&logo=buffer&logoColor=white)](https://krusch.dev/articles/the-sovereign-ai-tech-stack.html)
  [![MCP](https://img.shields.io/badge/KruschContext_MCP-v1.8.1-ff4081?style=for-the-badge&logo=anthropic&logoColor=white)](https://github.com/kruschdev/krusch-context-mcp)
  [![KruschGit](https://img.shields.io/badge/KruschGit-v1.2.2-00b4d8?style=for-the-badge&logo=git&logoColor=white)](https://github.com/kruschdev/krusch-git)
  [![KruschFS](https://img.shields.io/badge/KruschFS_MCP-v0.3.1-00e676?style=for-the-badge&logo=linux&logoColor=black)](https://github.com/kruschdev/krusch-fs-mcp)
  [![PostgreSQL](https://img.shields.io/badge/PostgreSQL_16-pgvector_HNSW-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://krusch.dev/articles/postgres-as-operating-plane-for-ai.html)
  [![LinkedIn](https://img.shields.io/badge/LinkedIn-Kevin_Ruschman-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kevin-saylor-ruschman-1080493a3/)
  [![X](https://img.shields.io/badge/X-@Kev96790724-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/Kev96790724)

  <br/>

  ### Multi-Family Bare-Metal GPUs · 3-Tier MCP Substrates · `@krusch/toolkit` · PostgreSQL 16 State Planes
</div>

---

### 💡 Architectural Premise

> **Language models are stateless, interchangeable compute samplers—routing, working memory, codebase navigation, and filesystem mutations belong to a deterministic systems stack.**

Instead of layering heavyweight prompt frameworks over a single metered cloud API and flat sliding-window RAG, my engineering stack inverts the model:
- **Multi-Family GPU Isolation:** 5 local bare-metal GPUs (`57GB+` VRAM over `10GbE`) + an on-demand **96GB Blackwell G4** burst tier run orthogonal model families (`Qwen3`, `Gemma 4`, `Hermes 3`, `GPT-OSS`, `Gemini 4 Argon`) so no model family ever grades its own homework.
- **Relational State & 7 Focused MCP Servers:** Working memory, Git Commit DAGs, AST caller/callee graphs, and 8-node OS page trees live in **PostgreSQL 16 + `pgvector` HNSW** and zero-Docker **SQLite WAL**.
- **Zero-Bloat Shared Runtime (`@krusch/toolkit` & `krusch_toolkit`):** Every Node.js 22 ESM and Python 3.12 repository imports unified LLM/vision clients, logprob routers, cross-family Referee gates, and context pruners from one monorepo toolkit.
- **Closed-Loop Self-Distillation:** A 24/7 autonomous SRE daemon (**Jean SRE**) continuously sweeps 86 software targets, verifies fixes in hermetic test sandboxes, and distills test-gated Golden Remediations back into local weights via QLoRA.

---

### 🏗️ The 2026 Sovereign AI Tech Stack Overview

```text
┌─────────────────────────────────────────────────────────────────────────────────────┐
│ LAYER 5 · SOVEREIGN DOMAIN ENGINES & EXECUTION SURFACES                             │
│           KruschNexus · KruschLaw (0.00% FSR) · KruschBiz · Companion · G-Krusch    │
├─────────────────────────────────────────────────────────────────────────────────────┤
│ LAYER 4 · AUTONOMOUS SRE, VERIFICATION & DUAL-TRACK QLoRA SELF-DISTILLATION         │
│           Jean SRE (86 Targets) · Spec-First Referee Gate · 9,377 SFT Trajectory DB │
├─────────────────────────────────────────────────────────────────────────────────────┤
│ LAYER 3 · ZERO-BLOAT RUNTIME & SHARED MONOREPO TOOLKITS                             │
│           @krusch/toolkit (Node 22 ESM · node:sqlite · node --test · oxlint)        │
│           krusch_toolkit  (Python 3.12 · FastAPI · SQLAlchemy 2.0 · PyArrow)        │
├─────────────────────────────────────────────────────────────────────────────────────┤
│ LAYER 2 · 7-SERVER MODEL CONTEXT PROTOCOL (MCP) & RELATIONAL STATE SUBSTRATE        │
│           PostgreSQL 16 + pgvector HNSW · SQLite WAL · Polygres Cloud Bridge        │
│           Tier 1: krusch-context-mcp │ Tier 2A: krusch-git │ Tier 2B: krusch-fs-mcp │
│           Tier 3: krusch-harness 2PC │ Domain: Gateway · Frontend · G-Krusch        │
├─────────────────────────────────────────────────────────────────────────────────────┤
│ LAYER 1 · COMPUTE, MULTI-FAMILY 5-GPU POOL & MICROSECOND CASCADE ROUTING            │
│           Stage 0 (<15µs CPU) ──► Stage 1 (<25µs / <50ms Centroids · 80.72% Acc)    │
│           ──► Local 5-GPU Pool (57GB+ VRAM · 10GbE) ──► 96GB Blackwell G4 (120B)    │
│           ──► Frontier Escalation & 3-Viewport Chrome UI Audit (Gemini 4 Argon)     │
└─────────────────────────────────────────────────────────────────────────────────────┘
```

---

### ⚡ Layer 1: Compute, Multi-Family GPU Pool & Cascade Routing

All local inference models are pinned 100% in VRAM (`keep_alive: -1`, `q8_0` quantized KV caches, zero CPU spill) across an 8-node Linux fleet interconnected via a dedicated `10GbE` fabric and encrypted Tailscale mesh:

| Compute Tier / Node Role | Hardware Profile | Pinned Models & Throughput | Role in the Stack |
| :--- | :--- | :--- | :--- |
| **Stage 0 & Stage 1 Routers**<br>[`krusch-pre-router`](https://github.com/kruschdev/krusch-pre-router) · [`krusch-cascade-router`](https://github.com/kruschdev/krusch-cascade-router) | In-Process CPU + Local Embedding Centroids | `<15µs` syntactic gate (`$0.00`)<br>`<25µs` / `<50ms` centroid cascade | Eliminates the 500ms LLM routing tax; benchmarked at **80.72% accuracy (`$0.21/1K`)** on RouteWorks RouterArena with speculative parallel hedging. |
| **Node-02 · Heavy Compute Host**<br>*(10GbE Compute Plane)* | Dual Xeon 40T · 64GB ECC<br>**Dual RTX 2080 Ti (22.5GB NVLink)** | `qwen3-coder-30b-moe:latest`<br>(`16K` ctx · `q8_0` KV · **124.2 tok/s**) | Primary local code synthesis, multi-file AST refactoring, and **Jean SRE** autonomous persona reasoning. |
| **Node-01 · State & Referee Host**<br>*(10GbE Production Plane)* | Dual Xeon 40T · 80GB RAM<br>**Dual RTX 3060 (24.5GB VRAM)**<br>+ Dedicated NVMe DB Array | `gemma4:e4b` (`16K` ctx · native tools/thinking/vision/audio)<br>`hermes3:latest` (`16K` ctx · `q8_0` KV) | **Cross-Family Referee Pool** (auditing Qwen outputs), SRE tool execution, statutory/contract prose, and primary **PostgreSQL 16 + `pgvector`** host. |
| **Node-03 · Orchestrator Host**<br>*(Central Control Plane)* | i7-5820K · 32GB RAM<br>**RTX 2080 Ti (11.2GB VRAM)** + 5 Edge Nodes | `bge-large:latest` (1,024-dim)<br>`qwen2.5-coder:7b` (**74.6 tok/s**)<br>`faster-whisper` (16kHz ASR) | Fleet-wide 1,024-dim semantic embeddings, sub-second tag/intent classification, local IDE coding, and real-time voice transcription. |
| **Tier L2.5 · Cloud Burst**<br>*(On-Demand SSH Tunnel)* | 48 vCPU · 176GB RAM<br>**RTX PRO 6000 Blackwell (96GB)** | `gpt-oss:120b`<br>(`131K` ctx · **~117.7 tok/s** · 4-bit MXFP4) | Ephemeral high-VRAM burst tier for `120B` architectural synthesis and **Dual-Track QLoRA Teacher/Student fine-tuning**. |
| **Tier L3 · Frontier & Vision**<br>*(Managed API & `gemini-api` CLI)* | Frontier Cloud Escalation | `gemini-4-argon` (`65,536` max output · `thinkingLevel` · `CONTINUATION`) | L0 architectural planning, Golden Remediation synthesis, and **3-viewport (`375/768/1440px`) headless Chrome visual UI auditing**. |

---

### 🛠️ Layer 2: The 7-Server Model Context Protocol (MCP) & State Substrate

Standardized across **Antigravity**, **Claude Code**, **Cursor**, and **Windsurf**. Instead of bloating agent context with dozens of overlapping tools, each MCP server exposes a disciplined verb contract (`~350–450` tokens) with explicit behavioral annotations (`readOnlyHint`, `destructiveHint`, `idempotentHint`, `openWorldHint`):

<div align="center">
  <img src="assets/agent_architecture.svg" alt="3-Tier Sovereign Agent MCP Ecosystem" width="100%" />
</div>

<br/>

| Tier / Domain | MCP Server & Package | Verb Contract | Storage Engine & Architectural Role |
| :--- | :--- | :--- | :--- |
| **Tier 1**<br>Working Memory | [**`krusch-context-mcp`**](https://github.com/kruschdev/krusch-context-mcp) `v1.8.1` | 5 Verbs:<br>`retrieve`, `remember`, `revise`, `nudge`, `health` | `node:sqlite` WAL + PostgreSQL 16. Enforces Turn-1 Zero-Trust Hydration, closed 5-category taxonomy, temporal lineage superseding, and `INV-12` span-grounded SHA-256 drift detection. |
| **Tier 2A**<br>Code & Git DAG | [**`krusch-git`**](https://github.com/kruschdev/krusch-git) `v1.2.2` | 7 Verbs:<br>`search_symbols`, `dependency_graph`, `file_symbols`, `semantic_search`, `read_tree`, `read_blob`, `list_repos` | PostgreSQL 16 + `pgvector` HNSW. Zero-dependency brace-matched AST symbol chunker, recursive SQL CTE caller/callee blast-radius checks, and Hybrid BM25 + 1,024-dim RRF with temporal decay. |
| **Tier 2B**<br>OS & Fleet Memory | [**`krusch-fs-mcp`**](https://github.com/kruschdev/krusch-fs-mcp) `v0.3.1` | 6 Verbs:<br>`search`, `locate`, `page_tree`, `read_page`, `remember_on_page`, `sync` | SQLite WAL / Postgres + **KruschNexus Library Mode**. Indexes PDFs, DOCX, `/etc/systemd`, and `/etc/fstab` across 8 SSH nodes into SHA-256 drift-verified page trees with `.env` secret value redaction. |
| **Tier 3**<br>2PC Execution | [**`krusch` (Harness)**](https://github.com/kruschdev/krusch) `v0.1.0` | 7 Verbs:<br>`run`, `task_status`, `diff`, `apply_diff`, `explain`, `reject`, `abort` | PostgreSQL 16 finite state machine + Bubblewrap sandboxes. Stages patches in `staged_diffs`, runs isolated container tests, and commits to disk via `<32ms` two-phase commit (2PC) apply journals. |
| **Domain RAG**<br>Law & Contracts | **`krusch-gateway-mcp`** | 5 Verbs (`<450` tok):<br>`ask_law`, `ask_biz`, `check_compliance`, `ingest`, `purge` | Unified stdio router across **KruschLaw** (`0.00%` FSR statutory DAGs), **KruschBiz** (confirmed-edge contract graphs), **KruschBizLaw** ("The Join"), and **KruschNexus**. |
| **Web Design**<br>UI Primitives | **`krusch-frontend-mcp`** | `get_canonical_template`, `list_canonical_templates`, `query_design_rules`, `css_to_tailwind` | Serves bit-for-bit canonical HTML/SVG components (`article-shell`, `footer-deadbolt`, `cyber-grid`) and responsive layout rules. |
| **Workspace Hub**<br>Drive, Docs & Mail | **`g-krusch`** | 12 Verbs:<br>`search_drive_rag`, `write_drive_file`, `get_agent_steering`, etc. | SQLite FTS5 + 1,024-dim Drive RAG, AES-256-GCM vault, and server-side OpenXML/HTML/CSV conversion for native Google Docs (`.gdoc`), Sheets (`.gsheet`), and Slides (`.slides` with speaker notes). |
| **Hybrid Bridge**<br>Cloud Substrate | [**`@krusch/polygres-connector`**](https://github.com/kruschdev/krusch-polygres-connector) | `getSymbolContext`, `auditRefactor`, `sync` | Bridges local SQLite/PostgreSQL with Polygres Cloud (`pgContext` + `pgGraph`) with 40-char SHA pinning and fail-closed air-gap enforcement. |

---

### 🧰 Layer 3: Zero-Bloat Runtime & Shared Monorepo Toolkits (`@krusch/toolkit` & `krusch_toolkit`)

We avoid heavyweight framework dependencies by standardizing every service across 27+ core repositories on **Node.js 22+ ESM**, **Python 3.12**, **PostgreSQL 16**, and a pair of zero-bloat shared monorepo libraries:

- **JavaScript / Web Stack:** Node.js 22 ESM (`"type": "module"`), built-in `node:sqlite` (`DatabaseSync` with WAL + automatic `PRAGMA quick_check` corruption self-healing), native `node --test`, `oxlint`, Express, React + Vite + Tailwind CSS, and Cloudflare Pages/Workers.
- **Python / Data & ML Stack:** Python 3.12, FastAPI, SQLAlchemy 2.0, Pydantic v2, PyArrow, Poppler TSV layout extraction, `faster-whisper`, and `pytest`.

| Shared Module | Exported Primitives | What It Replaces / Provides |
| :--- | :--- | :--- |
| **`@krusch/toolkit/llm`** & **`/vision`** | `chat`, `chatJson`, `callGeminiMedia`, `callGeminiMediaJson` | Unified client for local Ollama pools, xAI, and `gemini-4-argon` (`thinkingLevel`, `65,536` `maxOutputTokens`, and multi-hop `CONTINUATION` stitching). |
| **`@krusch/toolkit/browser`** | `scrapeHtml`, `captureResponsiveBreakpoints`, `auditPageWithArgon` | Stealth Puppeteer capturing `375/768/1440px` viewports + console/network telemetry routed to Gemini 4 Argon with deterministic offline CI fallback. |
| **`@krusch/toolkit/decide`** | `decide`, `decideBatch`, `calibrateChoiceLogprobs`, `createSystem1Decider` | Single-token logprob System-1 decision router with temperature calibration, LRU cache, and zero-network CI fallback. |
| **`@krusch/toolkit` (Spec & Referee)** | `createSpecAuditRunner`, `runRefereeAuditPass`, `evaluateRefereeConsensus`, `checkConvergence` | Enforces the **Dual-Zero-Finding Convergence Gate** across orthogonal model families (`Qwen3` generator vs. `Gemma 4` / `Hermes 3` referees). |
| **`@krusch/toolkit` (Context & Drift)** | `createContextPruner`, `MemoryInvalidationEngine`, `ArtifactVerificationGraph` | 3-stage context pruning (`pre-retrieval`, `post-retrieval`, `pre-synthesis`), temporal fact superseding, and SHA-256 artifact-anchored drift invalidation. |
| **`@krusch/toolkit` (Resilience & KV)** | `createTrajectoryGuard`, `evaluateFutileReasoning`, `createKvCacheManager`, `createGvaAllocator` | Loop/goal-drift circuit breakers, prompt-injection sanitization, and Grouped Value Attention (GVA) / KV cache sizing across multi-GPU pools. |
| **`krusch_toolkit` (Python)** | `ai` (`chat`, `chat_json`), `db` (SQLAlchemy), `config`, `log`, `auth`, `decide` | Python 3.12 parity suite for LLM structured extraction, database pooling, rotating JSON logs, and logprob routing. |

---

### 🔄 Layer 4: Autonomous SRE, Verification & Dual-Track QLoRA Self-Distillation

1. **Spec-First & Disjoint Parallel Subagent Fan-Out (`INV-606`):** Multi-module builds freeze exports, schemas, and JSON contracts (`{ ok, tool, summary, data }`) in `spec.md`, fan out parallel subagents owning 1–2 disjoint files with local `node --check` / `npx oxlint` verification, and wire shared choke points exclusively in the parent orchestrator before running the **Dual-Zero-Finding Convergence Gate**.
2. **Jean SRE 24/7 Fleet & Codebase Sweeps:** Our autonomous SRE daemon continuously audits all **86 software targets** and 21+ infrastructure checks—building AST symbol indexes, running cross-family Referee audits, verifying candidate fixes inside hermetic container test suites (`node --test` and `pytest`), and normalizing passing diffs into `$WORKSPACE_ROOT`-portable SFT training rows.
3. **Dual-Track QLoRA Distillation on 96GB Blackwell G4:**
   - **120B Teacher Track (`gpt-oss-120b`):** Uses native Blackwell `Mxfp4Config(dequantize=False)` to keep 128 MoE experts frozen in hardware-native 4-bit MXFP4 (`~63GB` VRAM) while training BF16 attention LoRA adapters (`r=16, alpha=32`) on **1,168 elitist teacher rows** (`2x` oversampled Gemini 4 Argon Golden Remediations + rejection-sampled 120B traces with `>=3` `file:line` citations).
   - **30B Student Track (`qwen3-coder-30b-moe`):** Oversamples Argon Golden Remediations `3x` alongside **9,377 test-verified Student SFT rows** to continuously upgrade our local `124.2 tok/s` coding workhorse.

---

### 🚀 Layer 5: Sovereign Domain Engines & Applications Built on the Stack

| System | Domain | How It Leverages the Stack |
| :--- | :--- | :--- |
| [**Krusch Companion**](https://github.com/kruschdev/krusch-companion) `v1.2` | Voice-First Personal AI & Priority Engine | Local `faster-whisper` ASR, Dual-Axis Priority Board (4 Lanes × 6 Pillars), 20-tool `<holodata>` proxy with Confirm-Before-Act gates, Opt-In Headless Chrome + Gemini 4 Argon UI Auditor, and SQLite WAL fact superseding. |
| [**KruschNexus**](https://github.com/kruschdev/krusch-nexus) `v0.3.1` | Layout-True Document Ingestion Spine | 7-parser-family Poppler TSV bounding-box ingestion (`100%` held-out citation accuracy, `96.2%` span precision) preserving physical `pdf_page`, `printed_page`, `bbox`, and `char_start..end` coordinates. |
| [**KruschLaw**](https://github.com/kruschdev/krusch-law) & **Authority Packs** | Air-Gapped Legal RAG & Statutory DAGs | Enforces a **0.00% False Support Rate** via two-pass proposition entailment, versioned statutory preemption DAGs (`resolve_controlling_law` with `as_of_date`), 16 certified Authority Packs, and cryptographic purge. |
| **KruschBiz** & **KruschBizLaw** | Contract Graphs & Statutory Compliance | Confirmed-edge commercial contract precedence graph (MSA/SOW/Amendment overrides), unexecuted draft isolation, and **"The Join"** (auditing contract slots directly against statutory floors/ceilings). |

---

### 📊 Verified Systems & Performance Benchmarks

<div align="center">
  <img src="assets/metrics.svg" alt="Systems & Performance Benchmarks" width="100%" />
</div>

<br/>

<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=kruschdev&theme=tokyonight&background=070b16&ring=00e5ff&fire=7c4dff&currStreakLabel=00e5ff&sideNums=ffffff&currStreakNum=00e5ff&sideLabels=94a3b8&border=1f293d&stroke=00e5ff" alt="GitHub Streak Stats" height="175" />
</div>

---

### 📖 Selected Architecture Papers ([All 19 on krusch.dev →](https://krusch.dev/articles/))

- ⚡ [**The 2026 Sovereign AI Tech Stack: Multi-Family GPUs, 3-Tier MCP Substrates, `@krusch/toolkit`, and Closed-Loop Distillation**](https://krusch.dev/articles/the-sovereign-ai-tech-stack.html) — *End-to-end blueprint of our 5 bare-metal GPUs + 96GB Blackwell G4 burst tier, 7 MCP servers, zero-bloat Node 22 / Python 3.12 runtime, and dual-track QLoRA self-distillation.*
- ⚡ [**Multi-Tier Cascade Routing: Slashing Enterprise Inference Budgets by 60–80%**](https://krusch.dev/articles/multi-tier-cascade-routing.html) — *How `krusch-pre-router` (`<15µs` CPU gate) and `krusch-cascade-router` achieve 80.72% accuracy at `$0.21/1K` on RouteWorks RouterArena.*
- 🧠 [**Beyond Flat Vector RAG: What Makes `krusch-context-mcp` Special**](https://krusch.dev/articles/what-makes-krusch-context-mcp-special.html) — *The 5-verb working memory contract (`~350` tokens), closed write taxonomy, and `INV-12` span-grounded SHA-256 drift detection.*
- 🌳 [**`krusch-git`: Git DAG Indexing, Relational AST Symbols, and Hybrid Recency Search**](https://krusch.dev/articles/krusch-git-architecture.html) — *Zero-dependency AST symbol extraction, recursive multi-hop caller/callee CTEs, and Hybrid RRF in PostgreSQL 16 + `pgvector`.*
- 🗂️ [**`krusch-fs-mcp`: OS Filesystem Page Memory, SHA-256 Drift Detection & Multi-Node Fleet Indexing**](https://krusch.dev/articles/krusch-fs-architecture.html) — *Turning PDFs, DOCX, and `/etc/systemd` across an 8-node SSH fleet into layout-true page trees with secret-redacted `.env` indexing.*
- 🛡️ [**The Krusch Coding Harness: Why Autonomous Code Agents Require a Transaction Manager, Not a Prompt**](https://krusch.dev/articles/krusch-coding-harness.html) — *Pre-commit SHA-256 diff staging in PostgreSQL, Bubblewrap sandboxes, and `<32ms` two-phase commit (2PC) apply journals.*

---

<div align="center">
  <sub>Engineered by <strong>Kevin Ruschman (@kruschdev)</strong> · <a href="https://krusch.dev">krusch.dev</a></sub>
</div>
