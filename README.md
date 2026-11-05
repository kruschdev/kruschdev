<div align="center">

  <img src="assets/banner.svg" alt="Kevin Ruschman — @kruschdev" width="100%" />

  <br/><br/>

  [![Website](https://img.shields.io/badge/Website-krusch.dev-00e5ff?style=for-the-badge&logo=googlechrome&logoColor=060913)](https://krusch.dev)
  [![Resume](https://img.shields.io/badge/Resume-PDF_%26_Web-7c4dff?style=for-the-badge&logo=readthedocs&logoColor=white)](https://krusch.dev/resume)
  [![Hugging Face](https://img.shields.io/badge/Hugging_Face-@krush420-ffcc00?style=for-the-badge&logo=huggingface&logoColor=060913)](https://huggingface.co/krush420)
  [![LinkedIn](https://img.shields.io/badge/LinkedIn-Kevin_Ruschman-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kevin-saylor-ruschman-1080493a3/)
  [![X](https://img.shields.io/badge/X-@Kev96790724-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/Kev96790724)

</div>

<br/>

I architect **deterministic AI infrastructure, relational working-memory substrates, transactional coding harnesses, and bare-metal multi-GPU inference pipelines**. Instead of wrapping fragile prompts around metered cloud APIs, I treat language models as stateless compute samplers governed by **PostgreSQL ACID state**, **sandboxed verification**, and **empirical benchmarks**.

---

### ⚡ Core Engineering Strengths

- **Stateful Agent Substrates & Long-Horizon Memory:** Designing bounded Model Context Protocol (MCP) engines backed by `PostgreSQL 16 + pgvector HNSW`, zero-Docker `node:sqlite` WAL, and Porter `FTS5`—proven across **10M-token** horizons where flat sliding-window RAG collapses.
- **Transactional Safety & Cross-Family Verification:** Building fail-closed execution harnesses with Bubblewrap sandboxes, `<32ms` two-phase commit (`2PC`) diff journals, 2-hop AST call-graph blast-radius gates, and **3-Family Referee Consensus** (`Qwen3` + `Gemini` + `DeepSeek` / local `Gemma 4` & `Hermes 3` with zero shortcut contagion).
- **Cost-Disciplined Bare-Metal LLMOps & Post-Training:** Operating an 8-node `10GbE` Linux GPU cluster (`57GB+` pinned local VRAM, zero CPU spill) with on-demand **96GB Blackwell** burst compute, `<15µs` cascade routing (**60–80% cost cut**), and test-gated **120B / 31B / 30B / 8B QLoRA + DPO self-distillation**.
- **Zero-Hallucination Evidentiary Retrieval:** Engineering layout-true Poppler TSV document spines (`100%` held-out citation accuracy) and two-pass proposition entailment pipelines enforcing a **0.00% False Support Rate** on statutory and contract corpora.
- **Real-World Operational Ownership:** Pairing high-velocity `Node.js 22 ESM`, `TypeScript`, and `Python 3.12` systems engineering across 35+ CI-verified repos with prior hands-on leadership in commercial NEC electrical diagnostics and brick-and-mortar P&L operations—shipping systems that fail closed and hold up in production.

---

### 📊 Verified Systems Benchmarks

<div align="center">
  <img src="assets/metrics.svg" alt="Systems & Performance Benchmarks" width="100%" />
</div>

---

### 🚀 Flagship Open-Source Systems

```bash
# Run the full 7-pillar, 39-tool MCP ecosystem locally in one command (Node.js 22+ SQLite WAL or PostgreSQL 16)
npx krusch-stack init --ide all --defer-tools && npx krusch-stack doctor
```

| System | Focus | Verified Engineering Impact |
| :--- | :--- | :--- |
| [**`krusch-stack`**](https://github.com/kruschdev/krusch-stack) `v1.1.0` & [**`grounded-harness`**](https://github.com/kruschdev/grounded-harness) `v0.2.0` | Unified Stack & Grounded Harness | 1-command installer (`npx` / Docker) bundling **39 annotated MCP tools** across 7 pillars + **Turn-0 Grounded Harness** (`INV-GH-01..10`) & **`2PC` Action Harness** (`68/68` tests); **`adyen/DABstep`:** **`90.0%` (`-74.5%` cost, `2.54x` faster)** on `Gemini 4 Argon` & **`2x` accuracy (`40.0%` @ `$0.00`)** on `Gemma 4 31B`; **UC Berkeley BFCL v3 Live (`2,251` Qs):** **`59.9%` → `66.3%`** at **`-80.7%` schema tokens** ([**Benchmarks ↗**](https://github.com/kruschdev/krusch-stack/blob/main/BENCHMARKS.md)). |
| [**`@krusch/toolkit`** & **`krusch_toolkit`**](https://github.com/kruschdev/toolkit) `v1.8.1` | Certified Code Substrate | **39 dual-runtime JS/TS & Python Lego bricks** (`64` `.d.ts` subpaths, `141/141` Node & `201/201` `pytest` suites, incl. atomic `Idempotency-Key` locks, immutable SHA-256/SQLite `audit-log`, zero-`node:*` `rbac`/IDOR guards, & HMAC keyset `pagination`) + **7 zero-LLM blueprints** & **16 `<1ms` Slop-Breaker detectors** (`krusch-lego`); enforces **`104/104` (`100%`) zero-boilerplate workspace compliance** ([**Architecture Paper ↗**](https://krusch.dev/articles/lego-system-for-code)). |
| [**`krusch-context-mcp`**](https://github.com/kruschdev/krusch-context-mcp) `v2.0.0` | Agent Working Memory | 5-verb hierarchical memory & SHA-256 drift gate. **#1 Overall on Official DolphinBench (`600` tasks, `27` runs / `16,200` `gpt-5.6-sol` traces, `97.83%` `Oracle@27`, `83.17%` `$0.00` `Oracle@17`):** **`91.17%` (`547/600`) @ `$24.54`** with `Gemini 4 Argon (Low)` (`94.00%` `Oracle@2`, `+20.50 pp` above `#1` `GPT 5.6 Luna + Mem0` `70.67%` @ `$96.21`, [**Return on Memory Paper ↗**](https://krusch.dev/articles/return-on-memory-dolphinbench)), **`81.50%` (`489/600`, `1.57x` faster) @ `$1.35`** on model-matched `GPT 5.6 Luna + Grounded` (`71.1x` cheaper than `Mem0`), & **`57.33%` (`344/600`) `#1` Open-Weights [`krush420/gemma4-31b-sre-lora`](https://huggingface.co/krush420/gemma4-31b-sre-lora) + Grounded @ `$0.00`** (`56.67%` Stock + Grounded, `43.00%` local `30B` + Grounded, [**Local AI Study ↗**](https://krusch.dev/articles/what-dolphinbench-taught-me-about-local-ai)); plus all **2,000 Official ICLR 2026 BEAM (`100K`–`10M` tok)** probes. |
| [**`krusch-cascade-router`**](https://github.com/kruschdev/krusch-cascade-router) | Inference Routing | **#1 on Martian RouterBench (`36,497` Qs)** (`0.7488` `0-shot` & `0.7695` `5-shot` ID `AIQ`, `-72.6%` cost @ `98%` `GPT-4`, & `#1` OOD beating `ZeroRouter`), **#1 on ACL 2026 LLMRouterBench** ([`0.4269` Pareto, `-83.95%` cost](https://huggingface.co/datasets/krush420/sovereign-g4-benchmarks) across `12,566` Qs & unseen OOD `ARC-AGI`/`HLE`), & **`0.7263` on RouterArena** (PR #169 open · `74.44%` @ `$0.38/1K`, `91.43%` rob., beating `Azure-Model-Router` `70.37` & `GPT-5` `64.32` @ `26.4x` lower cost); live SSE abort cuts `120B` TTFT **`-48.0%`** & routes `Polyglot` **`1,442x` faster** ([**Live Arena ↗**](https://huggingface.co/spaces/krush420/sovereign-router-arena)). |
| [**`Jean SRE`**](https://github.com/kruschdev/Jean-SRE-by-kruschdev) & [**`@krush420`**](https://huggingface.co/krush420) | Autonomous SRE & QLoRA | 24/7 daemon sweeping 104 repos in hermetic sandboxes + Rule-of-3 scouting; published [**18,131 Zero-Leak SFT + DPO rows**](https://huggingface.co/datasets/krush420/sovereign-code-audit-sft) (`7` splits) to train [**31B Dense (`#1` Open-Weights `57.33%`)**](https://huggingface.co/krush420/gemma4-31b-sre-lora), [**120B Teacher**](https://huggingface.co/krush420/gpt-oss-120b-sre-lora), [**30B Student (`43.00%`)**](https://huggingface.co/krush420/qwen3-coder-30b-sre-lora), & [**8B Edge**](https://huggingface.co/krush420/llama3-hermes3-8b-sre-lora) QLoRA + DPO adapters (`25%` → **`100%`** brick adoption; `4/4` DolphinBench lifts incl. **`+3.17 pp`** on `31B` & **`15.7x`** on `8B`). |
| [**`krusch-git`**](https://github.com/kruschdev/krusch-git) · [**`krusch-fs-mcp`**](https://github.com/kruschdev/krusch-fs-mcp) · [**`krusch-coding-harness`**](https://github.com/kruschdev/krusch-coding-harness) | Code, Security & `2PC` | **ACL 2025 CoIR (`2.39M` docs / `162,216` Qs):** **`56.40%` `#1` 10-task `NDCG@10`** (`> Voyage-Code-002` `56.26%`); **RepoBench-R (`47,998` Qs):** beats `CodeBERT` & `UniXcoder`; **AgentDojo (`1,046` eps):** **`0.00%` ASR (`0/949` attacks)**; **Aider Polyglot (`225`):** **`19.6%` → `51.6%` `Pass@2`**; **BIRD-SQL (`500`):** **`26.0%` → `40.2%` EX (`1.55x`)**. |
| [**`krusch-law`**](https://github.com/kruschdev/krusch-law) & [**`krusch-nexus`**](https://github.com/kruschdev/krusch-nexus) | Evidentiary RAG | **`0.00%` False Support Rate** statutory DAGs & citation spines; **LegalBench-RAG (`6,889` Qs / `714` docs):** **`26.74%` Macro F1 (`k=1`) & `25.81%` F1 / `44.72%` Recall (`k=2`)** (`33.95%` `MAUD` R@2 > OpenAI `3-large` + Cohere R@64 `28.28%`). |

---

### 🧰 Technical Stack

- **Languages & Runtimes:** `JavaScript / TypeScript` (`Node.js 22+ ESM`, `React`, `Vite`, `Express`, `Cloudflare Workers`, `oxlint`) · `Python 3.12` (`FastAPI`, `SQLAlchemy 2.0`, `Pydantic v2`, `PyTorch`, `asyncio`) · `SQL`
- **State, Graph & Search:** `PostgreSQL 16` (`pgvector` HNSW, `tsvector` GIN, Hybrid RRF) · `node:sqlite` WAL + external-content Porter `FTS5` · `snowflake-arctic-embed2` (`8,192`-ctx, `1,024`-dim, asymmetric `query:` calibration)
- **Infrastructure & LLMOps:** Multi-Node Bare-Metal Linux (`10GbE`, `Tailscale`, `systemd`, `Docker`, `Bubblewrap`) · `Ollama` / `vLLM` (`q8_0` KV) · `96GB RTX PRO 6000 Blackwell` MXFP4 QLoRA · `GitHub Actions CI`

---

### 📖 Selected Architecture Writing ([All 26 Papers on krusch.dev →](https://krusch.dev/articles/))

- [**Return on Memory: Why Test-Time Reasoning Unlocks Zero-Distillation Agentic Retrieval on Official DolphinBench (`91.17%`, `#1` Overall)**](https://krusch.dev/articles/return-on-memory-dolphinbench) — Holding `13,539` episodic sessions byte-for-byte constant inside frozen `0o444` SQLite checkpoints (`$0.00` Raw-RAG + 4-Way RRF) across `27` full `600`-task Official `gpt-5.6-sol` runs (`16,200` traces across `6` model families), model-matched `GPT 5.6 Luna (High) + Grounded` reaches **`81.50%` (`489/600` @ `$1.35`, `1.57x` faster)** (`+10.83 pp` above `#1` `Luna + Mem0` `70.67%` @ `$96.21`, **`71.1x` lower cost**), `Gemini 4 Argon (Low)` hits **`91.17%` (`547/600` @ `$24.54`, `97.83%` `Oracle@27`, `4.19x` `4+`-fact lift)**, and [`krush420/gemma4-31b-sre-lora`](https://huggingface.co/krush420/gemma4-31b-sre-lora) (`Google Gemma 4 31B` Wave-6 QLoRA+DPO + Grounded) hits **`57.33%` (`344/600` @ `$0.00`, `56.67%` Stock + Grounded, `83.17%` `$0.00` `Oracle@17`)**—beating `8` commercial cloud stacks up to `$1,830.57`.
- [**What 5,535 DolphinBench Runs Taught Me About Local AI Memory**](https://krusch.dev/articles/what-dolphinbench-taught-me-about-local-ai) — Controlled multi-family study across `600` workspace tasks + `15` counterfactuals (`13,539` sessions / `1.50M` tokens, `0o444` frozen SQLite WAL): general-domain `Gemma 4 31B` (`57.33%` Wave-6 + Grounded / `56.67%` Stock + Grounded / `54.17%` Stock @ `$0.00`) outperforms matched-scale `Qwen2.5-Coder-32B` (`35.33%`) by **`+22.00 pp`**, Wave-4 QLoRA+DPO + Grounded lifts local `30B` to `43.00%` (`42.67%` Std.) & `8B Q4_0` `15.7x`, and `krusch-stack`'s `2PC` Action Harness cuts duplicate MCP calls **`-95.2%` (`42 → 2`)** across all `600` local `30B` tasks (`10 → 0` on the diagnostic slice, `50.33%` `Oracle@2`).
- [**Why Coding Agents Need Certified Lego Bricks, Not Prompted Boilerplate: Inside a 39-Brick, Self-Evolving Code Substrate**](https://krusch.dev/articles/lego-system-for-code) — Eliminating LLM-regenerated HTTP `413` TCP `RST` races, DNS-rebinding SSRF, FTS5 injection, idempotency races, mutable audit logs, IDOR leaks, and YAML alias bombs across `104/104` (`100%`) homelab repositories using [`@krusch/toolkit` `v1.8.1` & `krusch_toolkit` `v1.6`](https://github.com/kruschdev/toolkit) (`16` `<1ms` Slop-Breaker detectors), pre-commit MCP diff guards, Rule-of-3 scouting, and 2-stage QLoRA + DPO calibration (`25%` → `100%`).
- [**The 15 Production Agentic Systems: Reference Architecture, State-Machine Invariants & Benchmark Proofs**](https://krusch.dev/articles/fifteen-production-agent-systems) — Three architectural teardowns covering `100+` async orchestration, typed Pydantic v2 swarms, `72h` Slack HMAC HITL leases, `100`-trajectory Golden DAG CI gates, `$0.50` cost kill-switches, and `5%` shadow diffing.
- [**How an Open-Weights Sovereign Stack Stacks Up Across 333,000+ Benchmark Queries (Including Where Cloud Still Wins)**](https://krusch.dev/articles/how-krusch-stack-stacks-up) — Empirical cross-stack comparison against wrapper and commercial cloud stacks across 13 external benchmarks (`49` Hugging Face audit logs [`48` raw JSON + `1` live PR #169 receipt bundle] & `90/90` SHA-256 gates), with honest gaps and reproduction commands.
- [**The 2026 Sovereign AI Tech Stack**](https://krusch.dev/articles/the-sovereign-ai-tech-stack) — Multi-family GPUs, 3-Tier MCP substrates, zero-bloat runtimes, and closed-loop QLoRA distillation.
- [**Multi-Tier Cascade Routing Architecture**](https://krusch.dev/articles/multi-tier-cascade-routing) — `#1` on Martian `RouterBench` (`0-shot`/`5-shot` ID & OOD), `#1` on ACL 2026 `LLMRouterBench` (`-83.95%` cost), `RouterArena` (`0.7263` across `8,400` live queries, `74.44%` @ `$0.38/1K`, `91.43%` rob., PR #169 open), live SSE logprob aborts (`-48.0%` TTFT), and `1,442x` faster agentic `Polyglot` routing.
- [**Beyond Flat Vector RAG: What Makes `krusch-context-mcp` Special**](https://krusch.dev/articles/what-makes-krusch-context-mcp-special) — 5-verb hierarchical working memory, temporal lineage, and SHA-256 span-drift checks across `100K`–`10M` tokens.
- [**The Krusch Coding Harness**](https://krusch.dev/articles/krusch-coding-harness) — Why autonomous code agents require a PostgreSQL `2PC` transaction manager rather than a prompt.

---

<div align="center">
  <sub>Engineered by <strong>Kevin Ruschman (@kruschdev)</strong> · Los Angeles, CA · <a href="https://krusch.dev">krusch.dev</a></sub>
</div>
