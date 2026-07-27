[English](README.md) · 🌐 **Português (Brasil)**

# Fellype Melo
### Engenheiro de Software — Arquitetura Backend · IA Aplicada · Sistemas em GPU

<p align="left">
  <img src="https://img.shields.io/badge/Arquitetura%20de%20Software-brightgreen?style=flat-square" alt="Arquitetura de Software" />
  <img src="https://img.shields.io/badge/IA%20Aplicada-orange?style=flat-square" alt="IA Aplicada" />
  <img src="https://img.shields.io/badge/GPU%20%26%20Infer%C3%AAncia-blueviolet?style=flat-square" alt="GPU e Inferência" />
  <img src="https://img.shields.io/badge/Publica%C3%A7%C3%A3o%20como%201%C2%BA%20autor-red?style=flat-square" alt="Publicação como primeiro autor" />
</p>

<p align="left">
  <a href="https://fellypemelo.github.io/curriculum-vitae/" target="_blank">
    <img src="https://img.shields.io/badge/Curr%C3%ADculo%20completo-1f6feb?style=for-the-badge&logoColor=white" alt="Currículo completo" />
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

Engenheiro de software no Rio de Janeiro, concluindo Análise e Desenvolvimento de Sistemas na FAETERJ-Rio. Trabalho no encontro entre arquitetura backend e IA aplicada, e gosto dos problemas que ficam perto da máquina: execução em sandbox, inferência quantizada em GPUs Intel Arc, trilhas de auditoria à prova de adulteração, DSP em tempo real.

---

## Trabalhos selecionados

| Projeto | O que tem de interessante |
| :--- | :--- |
| **[OpenScientific-Workbench](https://github.com/FellypeMelo/OpenScientific-Workbench)** | Plataforma de agentes de pesquisa que executa código de bioinformática gerado por LLM dentro de um sandbox de kernel `bwrap` real, atrás de um escalonador de DAG com laço ator-crítico que refaz o trabalho quando a revisão numérica o rejeita. `Python` `FastAPI` `Neo4j` `Qdrant` |
| **bio-saas** &nbsp;·&nbsp; *privado* | Cinco aplicações de conformidade em saúde sobre um núcleo endurecido: uma cadeia de hash de auditoria com HMAC que continua evidenciando adulteração mesmo contra um atacante com o dump do banco, além de RLS no Postgres testado a partir de um papel não-superusuário de verdade. `TypeScript` `PostgreSQL` |
| **tino** &nbsp;·&nbsp; *privado* | Captura notificações de banco e Pix por um `NotificationListenerService` nativo do Android, interpreta com uma Chain of Responsibility orientada a dados, e roda detecção de assinaturas e anomalias no próprio dispositivo sobre um banco SQLCipher. `Flutter` `Dart` |
| **[llama-cpp-turboquant-SYCL](https://github.com/FellypeMelo/llama-cpp-turboquant-SYCL)** | Port do esquema TurboQuant de cache KV para o backend SYCL da Intel, validado em Arc B580 física. **O esquema não é meu** — foi criado por [TheTom](https://github.com/TheTom) e [Gabe Ortiz](https://github.com/signalnine); eu escrevi os kernels SYCL, o despacho de atenção com precisão assimétrica e o harness de paridade/CI. Fork pessoal, não integrado ao upstream. `C++` `SYCL` |
| **[SilenceArc](https://github.com/FellypeMelo/SilenceArc)** | O forward pass de 133 tensores do DeepFilterNet3 montado à mão sobre primitivas oneDNN puras em uma única fila SYCL — sem OpenVINO nem ONNX Runtime no caminho da GPU. Medido em 2,4–3,9 ms por frame contra um orçamento de 10 ms. `C++20` `oneDNN` `oneMKL` |
| **[Open-ChatBot](https://github.com/FellypeMelo/Open-ChatBot)** | Motor local de personagens com LLM: montagem de prompt com orçamento de tokens, estado de persona com concorrência otimista e memória vetorial quantizada resistente a falhas. `Python` `FastAPI` `React` `llama.cpp` |

As entradas privadas descrevem apenas arquitetura, algoritmos e estratégia de testes — sem schemas, credenciais, dados de inquilinos ou termos comerciais.

Mais projetos, com os detalhamentos técnicos completos: **[fellypemelo.github.io/curriculum-vitae](https://fellypemelo.github.io/curriculum-vitae/)**

---

## Publicação

**Primeiro autor**, revisado por pares — MELO, F. S. S. et al. *Arquitetura Algorítmica para Atenção Sustentável: o Modelo Be-Productive como Resposta à Sobrecarga Cognitiva no Capitalismo de Vigilância*. Revista Tópicos, 2026. DOI: [10.70773/revistatopicos/781363235](https://doi.org/10.70773/revistatopicos/781363235)

---

## Stack

**Linguagens** &nbsp; `Python` · `TypeScript` · `Rust` · `C++` · `Dart` · `Go` · `Java`
**Backend e dados** &nbsp; `FastAPI` · `PostgreSQL` · `Redis` · `Neo4j` · `SQLite` · `Docker`
**IA e GPU** &nbsp; `PyTorch` · `ONNX Runtime` · `llama.cpp` · `SYCL / Intel oneAPI` · `oneDNN`
**Frontend** &nbsp; `React` · `Vite` · `Tailwind` · `Flutter` · `Tauri`
**Prática** &nbsp; `Clean Architecture` · `DDD` · `SOLID` · `TDD`

**Formação** — Análise e Desenvolvimento de Sistemas, FAETERJ-Rio (último semestre). Certificações em ethical hacking (Cisco), IA aplicada (IBM SkillsBuild) e Java (Oracle Academy).

---

<p align="center">
  <a href="https://github.com/FellypeMelo?tab=followers"><img src="https://img.shields.io/github/followers/FellypeMelo?style=for-the-badge&logo=github&logoColor=white&label=Seguidores&labelColor=0d1117&color=1f6feb" alt="Seguidores no GitHub" /></a>
  <a href="https://github.com/FellypeMelo/Open-ChatBot"><img src="https://img.shields.io/github/last-commit/FellypeMelo/Open-ChatBot?style=for-the-badge&logo=git&logoColor=white&label=%C3%9Altimo%20commit&labelColor=0d1117&color=1f6feb" alt="Último commit no Open-ChatBot" /></a>
</p>

<p align="center"><i>Aberto a colaborações em engenharia de software, IA aplicada e projetos open source.</i></p>
