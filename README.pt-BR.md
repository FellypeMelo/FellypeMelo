🌐 [English](README.md) · **Português (Brasil)**

# Fellype Samuel dos Santos de Melo
### Software Engineer & Tech Lead — Arquitetura de Software · IA Aplicada

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

📍 Rio de Janeiro, RJ, Brasil

---

### 🧠 Sobre Mim
Software Engineer e estudante do último período de **Análise e Desenvolvimento de Sistemas (FAETERJ-Rio)**. Atuo na intersecção entre **arquitetura de backend** e **Inteligência Artificial aplicada** (Deep Learning, NLP e Visão Computacional). Como Tech Lead, modelo requisitos de negócio em arquiteturas desacopladas e conduzo integrações técnicas de ponta a ponta.

> *"Great software starts by understanding problems before writing code."*

---

## 🤖 Projeto Principal — OpenChatBot

Motor **local-first** para agentes e personagens com **estado e memória persistente** — comportamento crível aplicável a companions, ficção interativa e **NPCs de jogos**. Execução 100% local, com RAG e controle total de privacidade, sem dependência de nuvem.

O núcleo é o **Living Entity Framework v5**, um motor cognitivo de seis camadas (master prompts, identidade, dinâmica social, estado emocional, contexto via RAG e histórico de conversa) sobre uma base **Clean Architecture / SOLID**.

*(Os detalhes de arquitetura e implementação abaixo são extraídos do próprio repositório do projeto — veja o link ao final desta seção para a fonte de verdade atual.)*

```mermaid
flowchart TB
    UI["React + Vite SPA<br/>TypeScript · Tailwind"]
    API["FastAPI Backend<br/>Clean Architecture · SOLID"]
    LEF["Living Entity Framework v5<br/>Motor cognitivo · 6 camadas"]
    MEM[("SQLite<br/>dados relacionais")]
    VEC[("ChromaDB<br/>vetores · RAG")]
    LLM["llama.cpp<br/>GGUF · GPU offload"]

    UI <-->|"HTTP / WS"| API
    API --> LEF
    LEF -->|contexto| VEC
    LEF -->|"histórico · identidade"| MEM
    LEF -->|prompt| LLM
    LLM -->|tokens| API
```

**Demo — memória persistente entre turnos** *(demonstração da interface)*

![OpenChatBot recuperando um fato dito turnos antes, via memória vetorial (RAG)](https://raw.githubusercontent.com/FellypeMelo/Open-ChatBot/main/docs/demo/openchatbot-memory.gif)

**Destaques técnicos**
- Inferência local via **llama.cpp** com quantização **GGUF** e offload de GPU.
- Memória híbrida: **SQLite** (relacional) + **ChromaDB** (vetorial / RAG).
- Separação de domínio, infraestrutura, adaptadores e apresentação (Clean Architecture).
- Deploy multiprocesso automatizado (build do frontend + serviços de IA + Uvicorn).

**Stack** &nbsp; `TypeScript` `React` `Vite` `Python` `FastAPI` `ChromaDB` `llama.cpp`

📂 **[Repositório & Documentação →](https://github.com/FellypeMelo/Open-ChatBot)**

---

## ⚡ TurboQuant — Otimização de Inferência *(fork do llama.cpp)*

Quantização de **KV-cache de 2–4 bits** com rotação **Walsh–Hadamard** (suavização de outliers antes de quantizar) para GPUs **Intel Arc / Xe2** via backend **SYCL** — o mesmo `turbo3` que alimenta o OpenChatBot.

**Benchmarks do repositório** *(Intel Arc B580 · Qwen3-4B Q4_K_M · contexto 64k):*
- 🔻 KV-cache de **9,2 GB → 1,6–1,8 GB** — até **7,5× menos** memória que fp16
- ⚡ Prefill em **paridade de velocidade com fp16**
- 🐛 6 bugs de correção resolvidos durante a implementação

**Stack** &nbsp; `C/C++` `SYCL` `Intel oneAPI` `Quantização` `llama.cpp`

📂 **[Fork & deep-dive técnico →](https://github.com/FellypeMelo/llama-cpp-turboquant-SYCL)**

---

## 🚀 Outros Projetos

| Projeto | O que resolve | Stack | Acesso |
| :--- | :--- | :--- | :--- |
| 🔬 **OpenScientific-Workbench** | Workbench agêntico para biologia computacional: pipelines multiagente em sandbox e integração de bases científicas via MCP. | `Python` · `FastAPI` · `Neo4j` · `MCP` | [Repo](https://github.com/FellypeMelo/OpenScientific-Workbench) |
| 👁️ **LocalVision-Jules** | Assistente de visão 100% local (modelos LLaVA): análise de imagem com histórico contextual e GUI acessível. | `Python` · `LM Studio` · `LLaVA` | [Repo](https://github.com/FellypeMelo/LocalVision-Jules) |
| 🧬 **Classificação de Embriões** | Rede **ResNet-18** (validação k-fold) integrada a API REST para apoiar uma **pesquisa de mestrado externa**. | `PyTorch` · `FastAPI` · `React` | FuzzyLab · privado |
| 🦠 **Segmentação de _Trypanosoma cruzi_** | Fine-tuning de **YOLOv8-seg** para segmentar estruturas em microscopia eletrônica de varredura. | `YOLOv8-seg` · `OpenCV` | FuzzyLab · privado |
| 🎓 **Educa** | Sistema de gestão escolar (turmas, notas, conteúdos) — TCC full stack, com engenharia de requisitos e modelagem relacional. | `React` · `FastAPI` · `MySQL` | Privado (TCC) |

*As linhas marcadas "privado" referem-se a repositórios não disponíveis publicamente; as descrições acima resumem meu papel no projeto, não são afirmações verificáveis de forma independente sobre os códigos-fonte privados em si.*

---

### 📝 Pesquisa & Publicação
**Primeiro autor** — periódico acadêmico revisado:

> **MELO, F. S. S.** et al. *Arquitetura Algorítmica para Atenção Sustentável: o Modelo Be-Productive como Resposta à Sobrecarga Cognitiva no Capitalismo de Vigilância*. Revista Tópicos, 2026.
> 🔗 **DOI:** [10.70773/revistatopicos/781363235](https://doi.org/10.70773/revistatopicos/781363235)

---

### 🔭 Foco Atual
- [ ] Orquestração de **multiagentes locais descentralizados** no núcleo do OpenChatBot.
- [ ] Design prático de **Sistemas Distribuídos** — Event-Driven Architecture, CQRS, Apache Kafka.
- [ ] Deploy de **visão computacional em tempo real** via WebSockets.

---

### 🛠️ Stack

**Linguagens**
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

**IA & Dados**
<p>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white" alt="OpenCV" />
  <img src="https://img.shields.io/badge/YOLOv8-111F68?style=flat" alt="YOLOv8" />
  <img src="https://img.shields.io/badge/ChromaDB-FF6F61?style=flat" alt="ChromaDB" />
  <img src="https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white" alt="SQLite" />
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white" alt="MySQL" />
  <img src="https://img.shields.io/badge/Neo4j-4581C3?style=flat&logo=neo4j&logoColor=white" alt="Neo4j" />
</p>

**Engenharia** &nbsp; `Clean Architecture` · `SOLID` · `DDD` · `Design Patterns` · `TDD` · `XP`

---

### 🎓 Formação & Certificações
- **Análise e Desenvolvimento de Sistemas** — *FAETERJ-Rio* (último período)
- 🛡️ **Ethical Hacking & Network Defense** — Cisco Networking Academy
- 🧠 **AI Fundamentals & Artificial Intelligence** (NLP, Watson Studio) — Cisco & IBM SkillsBuild
- ☕ **Java Foundations** — Oracle Academy

---

### 📊 GitHub

<p align="center">
  <a href="https://github.com/FellypeMelo?tab=followers"><img src="https://img.shields.io/github/followers/FellypeMelo?style=for-the-badge&logo=github&logoColor=white&label=Seguidores&labelColor=0d1117&color=1f6feb" alt="Seguidores no GitHub" /></a>
  <a href="https://github.com/FellypeMelo/Open-ChatBot"><img src="https://img.shields.io/github/last-commit/FellypeMelo/Open-ChatBot?style=for-the-badge&logo=git&logoColor=white&label=%C3%9Altimo%20commit&labelColor=0d1117&color=1f6feb" alt="Último commit no OpenChatBot" /></a>
  <a href="https://github.com/FellypeMelo?tab=repositories"><img src="https://img.shields.io/badge/Reposit%C3%B3rios-30%2B-1f6feb?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117" alt="Repositórios públicos" /></a>
</p>

---

<p align="center">
  <a href="https://linkedin.com/in/fellype-samuel">LinkedIn</a> ·
  <a href="mailto:fellypesamuel1@hotmail.com">Email</a> ·
  <a href="https://orcid.org/0009-0000-3274-0343">ORCID</a> ·
  <a href="https://github.com/FellypeMelo">GitHub</a>
</p>

<p align="center"><i>Aberto a colaborar em engenharia de software, IA aplicada e projetos open source.</i></p>
