🌐 **English** · [Português (Brasil)](README.pt-BR.md)

# Fellype Samuel dos Santos de Melo
### Software Engineer & Tech Lead — Software Architecture · Applied AI

<p align="left">
  <img src="https://img.shields.io/badge/Tech%20Lead-blue?style=flat-square" alt="Tech Lead" />
  <img src="https://img.shields.io/badge/Software%20Architecture-brightgreen?style=flat-square" alt="Software Architecture" />
  <img src="https://img.shields.io/badge/AI%20%26%20Deep%20Learning-orange?style=flat-square" alt="AI & Deep Learning" />
  <img src="https://img.shields.io/badge/GPU%20%26%20Inference%20Optimization-blueviolet?style=flat-square" alt="GPU & Inference Optimization" />
  <img src="https://img.shields.io/badge/First--Author%20Publication-red?style=flat-square" alt="First-Author Publication" />
  <img src="https://img.shields.io/badge/Open%20Source-black?style=flat-square" alt="Open Source" />
</p>

<p align="left">
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

📍 Rio de Janeiro, RJ, Brazil

---

### 🧠 About Me
Software Engineer and final-semester student of **Systems Analysis and Development (FAETERJ-Rio)**. I work at the intersection of **backend architecture** and **applied Artificial Intelligence** (Deep Learning, NLP, and Computer Vision). As a Tech Lead, I translate business requirements into decoupled architectures and drive technical integrations end to end.

> *"Great software starts by understanding problems before writing code."*

---

## 🤖 Flagship Project — OpenChatBot

**Local-first** engine for agents and characters with **persistent state and memory** — believable behavior applicable to companions, interactive fiction, and **game NPCs**. Runs 100% locally, with RAG and full privacy control, no cloud dependency.

At its core is the **Living Entity Framework v5**, a six-layer cognitive engine (master prompts, identity, social dynamics, emotional state, RAG-based context, and conversation history) built on a **Clean Architecture / SOLID** foundation.

*(Architecture and implementation details below are drawn from the project's own repository — see the link at the end of this section for the current source of truth.)*

```mermaid
flowchart TB
    UI["React + Vite SPA<br/>TypeScript · Tailwind"]
    API["FastAPI Backend<br/>Clean Architecture · SOLID"]
    LEF["Living Entity Framework v5<br/>Cognitive engine · 6 layers"]
    MEM[("SQLite<br/>relational data")]
    VEC[("ChromaDB<br/>vectors · RAG")]
    LLM["llama.cpp<br/>GGUF · GPU offload"]

    UI <-->|"HTTP / WS"| API
    API --> LEF
    LEF -->|context| VEC
    LEF -->|"history · identity"| MEM
    LEF -->|prompt| LLM
    LLM -->|tokens| API
```

**Demo — persistent memory across turns** *(interface walkthrough)*

![OpenChatBot recalling a fact stated turns earlier, via vector memory (RAG)](https://raw.githubusercontent.com/FellypeMelo/Open-ChatBot/main/docs/demo/openchatbot-memory.gif)

**Technical highlights**
- Local inference via **llama.cpp** with **GGUF** quantization and GPU offload.
- Hybrid memory: **SQLite** (relational) + **ChromaDB** (vector / RAG).
- Separation of domain, infrastructure, adapters, and presentation layers (Clean Architecture).
- Automated multi-process deployment (frontend build + AI services + Uvicorn).

**Stack** &nbsp; `TypeScript` `React` `Vite` `Python` `FastAPI` `ChromaDB` `llama.cpp`

📂 **[Repository & Documentation →](https://github.com/FellypeMelo/Open-ChatBot)**

---

## ⚡ TurboQuant — Inference Optimization *(llama.cpp fork)*

**2–4 bit KV-cache quantization** with **Walsh–Hadamard rotation** (outlier smoothing before quantizing) for **Intel Arc / Xe2** GPUs via the **SYCL** backend — the same `turbo3` path that powers OpenChatBot.

**As reported in the repository's own benchmarks** *(Intel Arc B580 · Qwen3-4B Q4_K_M · 64k context)*:
- 🔻 KV-cache reduced from **9.2 GB to 1.6–1.8 GB** — up to **7.5x less** memory than fp16
- ⚡ Prefill at **fp16 speed parity**
- 🐛 6 correctness bugs fixed during implementation

**Stack** &nbsp; `C/C++` `SYCL` `Intel oneAPI` `Quantization` `llama.cpp`

📂 **[Fork & technical deep-dive →](https://github.com/FellypeMelo/llama-cpp-turboquant-SYCL)**

---

## 🚀 Other Projects

| Project | What it solves | Stack | Access |
| :--- | :--- | :--- | :--- |
| 🔬 **OpenScientific-Workbench** | Agentic workbench for computational biology: sandboxed multi-agent pipelines and scientific database integration via MCP. | `Python` · `FastAPI` · `Neo4j` · `MCP` | [Repo](https://github.com/FellypeMelo/OpenScientific-Workbench) |
| 👁️ **LocalVision-Jules** | 100% local vision assistant (LLaVA models): image analysis with contextual history and an accessible GUI. | `Python` · `LM Studio` · `LLaVA` | [Repo](https://github.com/FellypeMelo/LocalVision-Jules) |
| 🧬 **Embryo Classification** | **ResNet-18** network (k-fold validation) integrated with a REST API to support an external master's research project. | `PyTorch` · `FastAPI` · `React` | FuzzyLab · private |
| 🦠 **_Trypanosoma cruzi_ Segmentation** | **YOLOv8-seg** fine-tuning to segment structures in scanning electron microscopy images. | `YOLOv8-seg` · `OpenCV` | FuzzyLab · private |
| 🎓 **Educa** | School management system (classes, grades, content) — full-stack capstone project (TCC), with requirements engineering and relational modeling. | `React` · `FastAPI` · `MySQL` | Private (capstone project) |

*Rows marked "private" refer to repositories not publicly available; descriptions above summarize my role, not independently verifiable claims about the private codebases themselves.*

---

### 📝 Research & Publication
**First author** — peer-reviewed academic journal:

> **MELO, F. S. S.** et al. *Arquitetura Algorítmica para Atenção Sustentável: o Modelo Be-Productive como Resposta à Sobrecarga Cognitiva no Capitalismo de Vigilância*. Revista Tópicos, 2026.
> 🔗 **DOI:** [10.70773/revistatopicos/781363235](https://doi.org/10.70773/revistatopicos/781363235)

---

### 🔭 Current Focus
- [ ] Decentralized local multi-agent orchestration at the core of OpenChatBot.
- [ ] Hands-on distributed systems design — Event-Driven Architecture, CQRS, Apache Kafka.
- [ ] Real-time computer vision deployment via WebSockets.

---

### 🛠️ Tech Stack

**Languages**
<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/PHP-777BB4?style=flat&logo=php&logoColor=white" alt="PHP" />
  <img src="https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black" alt="C" />
</p>

**Backend & Web**
<p>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black" alt="React" />
  <img src="https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white" alt="Vite" />
  <img src="https://img.shields.io/badge/Tailwind-06B6D4?style=flat&logo=tailwindcss&logoColor=white" alt="Tailwind" />
</p>

**AI & Data**
<p>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white" alt="OpenCV" />
  <img src="https://img.shields.io/badge/YOLOv8-111F68?style=flat" alt="YOLOv8" />
  <img src="https://img.shields.io/badge/ChromaDB-FF6F61?style=flat" alt="ChromaDB" />
  <img src="https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white" alt="SQLite" />
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white" alt="MySQL" />
  <img src="https://img.shields.io/badge/Neo4j-4581C3?style=flat&logo=neo4j&logoColor=white" alt="Neo4j" />
</p>

**Engineering** &nbsp; `Clean Architecture` · `SOLID` · `DDD` · `Design Patterns` · `TDD` · `XP`

---

### 🎓 Education & Certifications
- **Systems Analysis and Development** — *FAETERJ-Rio* (final semester)
- 🛡️ **Ethical Hacking & Network Defense** — Cisco Networking Academy
- 🧠 **AI Fundamentals & Artificial Intelligence** (NLP, Watson Studio) — Cisco & IBM SkillsBuild
- ☕ **Java Foundations** — Oracle Academy

---

### 📊 GitHub

<p align="center">
  <a href="https://github.com/FellypeMelo?tab=followers"><img src="https://img.shields.io/github/followers/FellypeMelo?style=for-the-badge&logo=github&logoColor=white&label=Followers&labelColor=0d1117&color=1f6feb" alt="GitHub followers" /></a>
  <a href="https://github.com/FellypeMelo/Open-ChatBot"><img src="https://img.shields.io/github/last-commit/FellypeMelo/Open-ChatBot?style=for-the-badge&logo=git&logoColor=white&label=Last%20commit&labelColor=0d1117&color=1f6feb" alt="Last commit on OpenChatBot" /></a>
  <a href="https://github.com/FellypeMelo?tab=repositories"><img src="https://img.shields.io/badge/Repositories-30%2B-1f6feb?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117" alt="Public repositories" /></a>
</p>

---

<p align="center">
  <a href="https://linkedin.com/in/fellype-samuel">LinkedIn</a> ·
  <a href="mailto:fellypesamuel1@hotmail.com">Email</a> ·
  <a href="https://orcid.org/0009-0000-3274-0343">ORCID</a> ·
  <a href="https://github.com/FellypeMelo">GitHub</a>
</p>

<p align="center"><i>Open to collaborating on software engineering, applied AI, and open-source projects.</i></p>
