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

Software engineer in Rio de Janeiro, finishing Systems Analysis and Development at FAETERJ-Rio. I work where backend architecture meets applied AI, and I like the problems that sit close to the machine: sandboxed execution, quantized inference on Intel Arc GPUs, tamper-evident data trails, real-time DSP.

---

## Selected work

| Project | What makes it interesting |
| :--- | :--- |
| **[OpenScientific-Workbench](https://github.com/FellypeMelo/OpenScientific-Workbench)** | Research-agent platform that runs LLM-generated bioinformatics code inside a real `bwrap` kernel sandbox, behind a DAG scheduler with an actor-critic loop that re-runs work when numeric review rejects it. `Python` `FastAPI` `Neo4j` `Qdrant` |
| **bio-saas** &nbsp;·&nbsp; *private* | Five healthcare-compliance apps over one hardened core: an HMAC-keyed audit hash-chain that stays tamper-evident against an attacker holding a database dump, plus Postgres RLS tested from a genuine non-superuser role. `TypeScript` `PostgreSQL` |
| **tino** &nbsp;·&nbsp; *private* | Captures bank and Pix push notifications through a native Android `NotificationListenerService`, parses them with a data-driven Chain-of-Responsibility, and runs subscription and anomaly detection on-device over an SQLCipher database. `Flutter` `Dart` |
| **[llama-cpp-turboquant-SYCL](https://github.com/FellypeMelo/llama-cpp-turboquant-SYCL)** | Port of the TurboQuant KV-cache scheme to Intel's SYCL backend, validated on physical Arc B580. **The scheme is not mine** — it was created by [TheTom](https://github.com/TheTom) and [Gabe Ortiz](https://github.com/signalnine); I wrote the SYCL kernels, the asymmetric-precision attention dispatch, and the parity/CI harness. Personal fork, not merged upstream. `C++` `SYCL` |
| **[SilenceArc](https://github.com/FellypeMelo/SilenceArc)** | DeepFilterNet3's 133-tensor forward pass hand-wired onto raw oneDNN primitives over one SYCL queue — no OpenVINO or ONNX Runtime in the GPU path. Measured 2.4–3.9 ms per frame against a 10 ms budget. `C++20` `oneDNN` `oneMKL` |
| **[Open-ChatBot](https://github.com/FellypeMelo/Open-ChatBot)** | Local-first LLM character engine: token-budgeted prompt assembly, optimistic-concurrency persona state, and a crash-safe quantized vector memory. `Python` `FastAPI` `React` `llama.cpp` |

Private entries describe architecture, algorithms and testing strategy only — no schemas, credentials, tenant data or commercial terms.

More, with the full technical write-ups: **[fellypemelo.github.io/curriculum-vitae](https://fellypemelo.github.io/curriculum-vitae/)**

---

## Publication

**First author**, peer-reviewed — MELO, F. S. S. et al. *Arquitetura Algorítmica para Atenção Sustentável: o Modelo Be-Productive como Resposta à Sobrecarga Cognitiva no Capitalismo de Vigilância*. Revista Tópicos, 2026. DOI: [10.70773/revistatopicos/781363235](https://doi.org/10.70773/revistatopicos/781363235)

---

## Stack

**Languages** &nbsp; `Python` · `TypeScript` · `Rust` · `C++` · `Dart` · `Go` · `Java`
**Backend & data** &nbsp; `FastAPI` · `PostgreSQL` · `Redis` · `Neo4j` · `SQLite` · `Docker`
**AI & GPU** &nbsp; `PyTorch` · `ONNX Runtime` · `llama.cpp` · `SYCL / Intel oneAPI` · `oneDNN`
**Frontend** &nbsp; `React` · `Vite` · `Tailwind` · `Flutter` · `Tauri`
**Practice** &nbsp; `Clean Architecture` · `DDD` · `SOLID` · `TDD`

**Education** — Systems Analysis and Development, FAETERJ-Rio (final semester). Certifications in ethical hacking (Cisco), applied AI (IBM SkillsBuild), and Java (Oracle Academy).

---

<p align="center">
  <a href="https://github.com/FellypeMelo?tab=followers"><img src="https://img.shields.io/github/followers/FellypeMelo?style=for-the-badge&logo=github&logoColor=white&label=Followers&labelColor=0d1117&color=1f6feb" alt="GitHub followers" /></a>
  <a href="https://github.com/FellypeMelo/Open-ChatBot"><img src="https://img.shields.io/github/last-commit/FellypeMelo/Open-ChatBot?style=for-the-badge&logo=git&logoColor=white&label=Last%20commit&labelColor=0d1117&color=1f6feb" alt="Last commit on Open-ChatBot" /></a>
</p>

<p align="center"><i>Open to collaborating on software engineering, applied AI, and open-source projects.</i></p>
