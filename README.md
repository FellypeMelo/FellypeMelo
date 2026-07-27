🌐 **English** · [Português (Brasil)](README.pt-BR.md)

# Fellype Melo
### Software Engineer — Backend Architecture · Applied AI · GPU Systems

<p align="left">
  <img src="https://img.shields.io/badge/Software%20Architecture-brightgreen?style=flat-square" alt="Software Architecture" />
  <img src="https://img.shields.io/badge/Applied%20AI-orange?style=flat-square" alt="Applied AI" />
  <img src="https://img.shields.io/badge/GPU%20%26%20Inference-blueviolet?style=flat-square" alt="GPU and Inference" />
  <img src="https://img.shields.io/badge/First--Author%20Publication-red?style=flat-square" alt="First-Author Publication" />
</p>

<p align="left">
  <a href="https://fellypemelo.github.io/curriculum-vitae/" target="_blank">
    <img src="https://img.shields.io/badge/Full%20CV-1f6feb?style=for-the-badge&logoColor=white" alt="Full CV" />
  </a>
  <a href="https://linkedin.com/in/fellype-samuel" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="mailto:fellypesamuel1@hotmail.com">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
  <a href="https://orcid.org/0009-0000-3274-0343" target="_blank">
    <img src="https://img.shields.io/badge/ORCID-A6CE39?style=for-the-badge&logo=orcid&logoColor=white" alt="ORCID" />
  </a>
</p>

📍 Rio de Janeiro, Brazil

Software engineer finishing Systems Analysis and Development at FAETERJ-Rio. I work where backend architecture meets applied AI, and I gravitate toward the problems that sit close to the machine: sandboxed execution of untrusted code, quantized inference on Intel Arc GPUs, tamper-evident data trails, real-time DSP.

Most of what follows is open source. Clone it, read the tests, run the benchmarks — the numbers below all trace back to a file in the repository they describe.

---

## 🗂️ Selected work

### 🔬 [OpenScientific-Workbench](https://github.com/FellypeMelo/OpenScientific-Workbench) — public

An agentic platform for computational biology that does the thing everyone hand-waves about: it actually **executes LLM-generated code**. That code runs inside a real `bwrap` kernel sandbox with no network namespace and a read-only root, because the alternative is trusting a language model with a shell.

Work is planned as a DAG and scheduled with reward-based pruning, then passed through an **actor–critic review loop** — a second agent audits the numeric claims in the output and sends the task back for a re-plan when they don't hold. RAG runs over Qdrant, the knowledge graph over Neo4j, and long jobs dispatch to Slurm over SSH with credentials issued ephemerally from Vault.

`Python 3.12` `FastAPI` `Next.js` `PostgreSQL` `Neo4j` `Qdrant` `Redis/RQ` `bubblewrap`
CI gates `pytest --cov-fail-under=80` and runs a real sandbox-escape smoke test.

### 🏥 bio-saas — *private*

Five healthcare-compliance products sharing one hardened core. The interesting part is the **audit trail**: an HMAC-keyed hash chain with a sequence anchor table, designed so that an attacker holding a full database dump still cannot rewrite history without detection. Append-only immutability is enforced at three separate database layers rather than trusted to application code.

Multi-tenancy is Postgres row-level security, and the tests prove it by connecting as a **genuine non-superuser role** — RLS that is only ever tested as superuser is RLS that has never been tested.

`TypeScript` `Fastify` `PostgreSQL` `pnpm monorepo`
Integration tests run against real Postgres and real S3 in CI, not mocks.

### ⚡ [llama-cpp-turboquant-SYCL](https://github.com/FellypeMelo/llama-cpp-turboquant-SYCL) — public fork

2/3/4-bit **rotated KV-cache quantization** on Intel Arc. Rotating each key/value vector with a Walsh–Hadamard transform smooths outliers before quantizing, so a tiny codebook reconstructs it near-losslessly. Result: the KV cache for a 4B model at 64k context drops from 9.2 GB to 1.6–1.8 GB, with prefill still at fp16 parity, measured on an Arc B580.

**Credit where it belongs:** TurboQuant was invented by [TheTom](https://github.com/TheTom) and [Gabe Ortiz](https://github.com/signalnine) for Metal and CUDA. I ported it to Intel's SYCL backend — the rotation kernels, the fix that made flash-attention work with a turbo cache at all, an asymmetric-precision dispatcher that keeps K precise while V goes low-bit, and the golden-parity and end-to-end gates. Personal fork, not merged upstream.

`C/C++17` `SYCL / Intel oneAPI` `CMake`

### 🔇 [SilenceArc](https://github.com/FellypeMelo/SilenceArc) — public

Real-time noise suppression on Intel Arc, with **no OpenVINO and no ONNX Runtime in the GPU path**. DeepFilterNet3's full 133-tensor forward pass is hand-wired onto raw oneDNN primitive descriptors over a single in-order SYCL queue, USM zero-copy, one sync per frame — which is what it takes to keep custom DSP interleaved with the network in the hot path.

Measured **2.4–3.9 ms per frame** (p99 4.3–4.9 ms) against a hard 10 ms budget, over 10,000 frames on an Arc B580.

`C++20` `SYCL` `oneDNN` `oneMKL` `Dear ImGui` `vendored Rust CPU fallback`

### 📱 tino — *private*

A local-first finance tracker that captures transactions from **Android bank and Pix push notifications** through a native `NotificationListenerService`, then parses them with a data-driven Chain of Responsibility so a new bank is a rule, not a code change.

Everything downstream runs on-device over an SQLCipher-encrypted database: FNV-1a content hashing for idempotent dedupe, statistical subscription detection, and unusual-spend nudges. No transaction data leaves the phone.

`Flutter` `Dart` `Drift` `SQLCipher` `Kotlin (platform channel)`

### 🤖 [Open-ChatBot](https://github.com/FellypeMelo/Open-ChatBot) — public

A local-first engine for stateful conversational characters — companions, interactive fiction, game NPCs. **Token-budgeted prompt assembly** decides what survives into a finite context window; persona and session state use optimistic concurrency so two in-flight turns cannot silently clobber each other; and the vector memory store is quantized and crash-safe, with consolidation.

Runs entirely offline against a local `llama.cpp` server. Includes dedicated anti-poison and cross-chat-scoping regression suites, because a memory system that can be poisoned is worse than no memory at all.

`Python` `FastAPI` `SQLAlchemy` `React 19` `Vite` `llama.cpp`

---

## 🚀 More work

| Project | | The interesting part |
| :--- | :--- | :--- |
| **[StoryForge](https://github.com/FellypeMelo/StoryForge)** | public | Offline-first Tauri/Rust novel-writing IDE. `sqlite-vec` semantic search that survives a live embedding-dimension change, a six-provider LLM router behind a circuit breaker, and E2E tests against a real `llama.cpp` server that caught model drift a mock had been hiding. |
| **embryo_trainer** | private | IVF embryo classification. Diagnosed a group-wise data-leakage bug in cross-validation — reported accuracy fell from a leaked 94–97% to an honest **91.37% holdout** once folds were grouped by embryo instead of by frame. Finding that bug was worth more than the score it cost. |
| **[Arc-Forge](https://github.com/FellypeMelo/Arc-Forge)** | public fork | Intel Arc optimization layer over Stable Diffusion WebUI Forge. My own contribution is the hardware-validation sprint: proving the OpenVINO UNet path end to end on a real Arc B580, where INT8 works and FP16 turns out VRAM-bound. |
| **fecho** | private | Cash-book for Brazilian micro-entrepreneurs. Every daily close posts as a Decimal-exact, Strategy-dispatched **double-entry ledger** inside one atomic transaction, with a per-account trial-balance invariant checked on commit. |

*Private entries describe architecture, algorithms and testing strategy only — no schemas, credentials, tenant or patient data, or commercial terms.*

---

## 📝 Publication

**First author**, peer-reviewed:

> **MELO, F. S. S.** et al. *Arquitetura Algorítmica para Atenção Sustentável: o Modelo Be-Productive como Resposta à Sobrecarga Cognitiva no Capitalismo de Vigilância*. Revista Tópicos, 2026.
> DOI: [10.70773/revistatopicos/781363235](https://doi.org/10.70773/revistatopicos/781363235) · Reference implementation: [Be-Productive-TCC](https://github.com/FellypeMelo/Be-Productive-TCC)

---

## 🔭 Current focus

- Agentic orchestration for scientific computing — DAG scheduling, sandboxed execution, numeric-correctness review loops.
- Low-level GPU work on Intel Arc / SYCL — KV-cache quantization and real-time DSP inference.
- Compliance-grade backend architecture for regulated domains — tenant isolation and tamper-evident audit trails.

---

## 🛠️ Stack

**Languages** &nbsp; `Python` · `TypeScript` · `Rust` · `C++` · `Dart` · `Go` · `Java` · `C`
**Backend & data** &nbsp; `FastAPI` · `Fastify` · `PostgreSQL` · `Redis` · `Neo4j` · `Qdrant` · `SQLite` · `Docker`
**AI & GPU** &nbsp; `PyTorch` · `ONNX Runtime` · `YOLO` · `llama.cpp` · `SYCL / Intel oneAPI` · `oneDNN`
**Frontend** &nbsp; `React` · `Next.js` · `Vite` · `Tailwind` · `Flutter` · `Tauri`
**Practice** &nbsp; `Clean Architecture` · `DDD` · `SOLID` · `TDD` · `Design Patterns`

**Education** — Systems Analysis and Development, FAETERJ-Rio (final semester). Certifications: Ethical Hacking & Network Defense (Cisco), AI Fundamentals & NLP (Cisco / IBM SkillsBuild), Java Foundations (Oracle Academy).

---

<p align="center">
  <a href="https://github.com/FellypeMelo?tab=followers"><img src="https://img.shields.io/github/followers/FellypeMelo?style=for-the-badge&logo=github&logoColor=white&label=Followers&labelColor=0d1117&color=1f6feb" alt="GitHub followers" /></a>
  <a href="https://github.com/FellypeMelo/Open-ChatBot"><img src="https://img.shields.io/github/last-commit/FellypeMelo/Open-ChatBot?style=for-the-badge&logo=git&logoColor=white&label=Last%20commit&labelColor=0d1117&color=1f6feb" alt="Last commit on Open-ChatBot" /></a>
  <a href="https://fellypemelo.github.io/curriculum-vitae/"><img src="https://img.shields.io/badge/Full%20technical%20CV-1f6feb?style=for-the-badge&logo=readthedocs&logoColor=white&labelColor=0d1117" alt="Full technical CV" /></a>
</p>

<p align="center"><i>Open to collaborating on software engineering, applied AI, and open-source projects.</i></p>
