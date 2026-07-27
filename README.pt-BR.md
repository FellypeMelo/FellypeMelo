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

📍 Rio de Janeiro, Brasil

Engenheiro de software concluindo Análise e Desenvolvimento de Sistemas na FAETERJ-Rio. Trabalho no encontro entre arquitetura backend e IA aplicada, e puxo para os problemas que ficam perto da máquina: execução de código não confiável em sandbox, inferência quantizada em GPUs Intel Arc, trilhas de dados à prova de adulteração, DSP em tempo real.

Quase tudo abaixo é open source. Clone, leia os testes, rode os benchmarks — todo número aqui remete a um arquivo do repositório que ele descreve.

---

## 🗂️ Trabalhos selecionados

### 🔬 [OpenScientific-Workbench](https://github.com/FellypeMelo/OpenScientific-Workbench) — público

Plataforma de agentes para biologia computacional que faz o que todo mundo trata por alto: **executa de fato o código gerado pelo LLM**. Esse código roda dentro de um sandbox de kernel `bwrap` real, sem namespace de rede e com raiz somente-leitura — porque a alternativa é confiar um shell a um modelo de linguagem.

O trabalho é planejado como DAG e escalonado com poda por recompensa, e então passa por um **laço ator–crítico**: um segundo agente audita as afirmações numéricas da saída e devolve a tarefa para replanejamento quando elas não se sustentam. O RAG roda sobre Qdrant, o grafo de conhecimento sobre Neo4j, e jobs longos são despachados para Slurm via SSH com credenciais efêmeras emitidas pelo Vault.

`Python 3.12` `FastAPI` `Next.js` `PostgreSQL` `Neo4j` `Qdrant` `Redis/RQ` `bubblewrap`
A CI exige `pytest --cov-fail-under=80` e roda um smoke test real de escape de sandbox.

### 🏥 bio-saas — *privado*

Cinco produtos de conformidade em saúde compartilhando um núcleo endurecido. O ponto interessante é a **trilha de auditoria**: uma cadeia de hash com HMAC e tabela âncora de sequência, desenhada para que um atacante de posse do dump completo do banco ainda não consiga reescrever o histórico sem ser detectado. A imutabilidade append-only é imposta em três camadas distintas do banco, não confiada ao código de aplicação.

A multitenancy é row-level security do Postgres, e os testes provam isso conectando como **papel não-superusuário de verdade** — RLS testado só como superusuário é RLS que nunca foi testado.

`TypeScript` `Fastify` `PostgreSQL` `monorepo pnpm`
Testes de integração rodam contra Postgres e S3 reais na CI, não mocks.

### ⚡ [llama-cpp-turboquant-SYCL](https://github.com/FellypeMelo/llama-cpp-turboquant-SYCL) — fork público

**Quantização rotacionada de cache KV** em 2/3/4 bits na Intel Arc. Rotacionar cada vetor de chave/valor com uma transformada de Walsh–Hadamard suaviza outliers antes de quantizar, então um codebook minúsculo o reconstrói quase sem perda. Resultado: o cache KV de um modelo de 4B em contexto de 64k cai de 9,2 GB para 1,6–1,8 GB, com o prefill ainda em paridade com fp16, medido em uma Arc B580.

**Crédito a quem é devido:** o TurboQuant foi inventado por [TheTom](https://github.com/TheTom) e [Gabe Ortiz](https://github.com/signalnine) para Metal e CUDA. Eu portei para o backend SYCL da Intel — os kernels de rotação, a correção que tornou o flash-attention utilizável com cache turbo, um despachante de precisão assimétrica que mantém K preciso enquanto V vai para baixa precisão, e os gates de paridade golden e ponta a ponta. Fork pessoal, não integrado ao upstream.

`C/C++17` `SYCL / Intel oneAPI` `CMake`

### 🔇 [SilenceArc](https://github.com/FellypeMelo/SilenceArc) — público

Supressão de ruído em tempo real na Intel Arc, **sem OpenVINO e sem ONNX Runtime no caminho da GPU**. O forward pass completo de 133 tensores do DeepFilterNet3 é montado à mão sobre descritores de primitivas oneDNN puras, em uma única fila SYCL em ordem, USM zero-copy, um sync por frame — que é o necessário para manter DSP customizado entrelaçado com a rede no hot path.

Medido em **2,4–3,9 ms por frame** (p99 4,3–4,9 ms) contra um orçamento rígido de 10 ms, ao longo de 10.000 frames em uma Arc B580.

`C++20` `SYCL` `oneDNN` `oneMKL` `Dear ImGui` `fallback Rust em CPU vendorizado`

### 📱 tino — *privado*

Rastreador financeiro local-first que captura transações de **notificações push de banco e Pix no Android** por um `NotificationListenerService` nativo, e as interpreta com uma Chain of Responsibility orientada a dados — de modo que um banco novo é uma regra, não uma mudança de código.

Tudo a jusante roda no próprio dispositivo sobre um banco cifrado com SQLCipher: hash de conteúdo FNV-1a para deduplicação idempotente, detecção estatística de assinaturas e alertas de gasto atípico. Nenhum dado de transação sai do aparelho.

`Flutter` `Dart` `Drift` `SQLCipher` `Kotlin (platform channel)`

### 🤖 [Open-ChatBot](https://github.com/FellypeMelo/Open-ChatBot) — público

Motor local-first para personagens conversacionais com estado — companions, ficção interativa, NPCs de jogos. A **montagem de prompt com orçamento de tokens** decide o que sobrevive em uma janela de contexto finita; o estado de persona e sessão usa concorrência otimista para que dois turnos em voo não se sobrescrevam em silêncio; e o armazenamento de memória vetorial é quantizado, resistente a falhas e com consolidação.

Roda inteiramente offline contra um servidor `llama.cpp` local. Inclui suítes dedicadas de regressão contra envenenamento de memória e vazamento entre conversas — porque um sistema de memória que pode ser envenenado é pior que memória nenhuma.

`Python` `FastAPI` `SQLAlchemy` `React 19` `Vite` `llama.cpp`

---

## 🚀 Mais trabalhos

| Projeto | | O que tem de interessante |
| :--- | :--- | :--- |
| **[StoryForge](https://github.com/FellypeMelo/StoryForge)** | público | IDE de escrita de romances em Tauri/Rust, offline-first. Busca semântica com `sqlite-vec` que sobrevive a mudança de dimensão de embedding em produção, roteador de seis provedores de LLM atrás de um circuit breaker, e testes E2E contra um servidor `llama.cpp` real que pegaram uma deriva do modelo que um mock vinha escondendo. |
| **embryo_trainer** | privado | Classificação de embriões para FIV. Diagnostiquei um vazamento de dados por grupo na validação cruzada — a acurácia reportada caiu de 94–97% vazados para **91,37% honestos em holdout** depois que os folds passaram a ser agrupados por embrião em vez de por frame. Achar esse bug valeu mais que a pontuação que ele custou. |
| **[Arc-Forge](https://github.com/FellypeMelo/Arc-Forge)** | fork público | Camada de otimização Intel Arc sobre o Stable Diffusion WebUI Forge. Minha contribuição própria é o sprint de validação em hardware: provar o caminho UNet do OpenVINO ponta a ponta em uma Arc B580 real, onde INT8 funciona e FP16 se revela limitado por VRAM. |
| **fecho** | privado | Livro-caixa para MEIs. Cada fechamento diário é postado como um **razão de partidas dobradas** exato em Decimal, despachado por Strategy, dentro de uma única transação atômica, com invariante de balancete por conta verificada no commit. |

*As entradas privadas descrevem apenas arquitetura, algoritmos e estratégia de testes — sem schemas, credenciais, dados de inquilinos ou de pacientes, nem termos comerciais.*

---

## 📝 Publicação

**Primeiro autor**, revisado por pares:

> **MELO, F. S. S.** et al. *Arquitetura Algorítmica para Atenção Sustentável: o Modelo Be-Productive como Resposta à Sobrecarga Cognitiva no Capitalismo de Vigilância*. Revista Tópicos, 2026.
> DOI: [10.70773/revistatopicos/781363235](https://doi.org/10.70773/revistatopicos/781363235) · Implementação de referência: [Be-Productive-TCC](https://github.com/FellypeMelo/Be-Productive-TCC)

---

## 🔭 Foco atual

- Orquestração agêntica para computação científica — escalonamento por DAG, execução em sandbox, laços de revisão de correção numérica.
- Trabalho de baixo nível em GPU Intel Arc / SYCL — quantização de cache KV e inferência de DSP em tempo real.
- Arquitetura backend de nível de conformidade para domínios regulados — isolamento de inquilinos e trilhas de auditoria à prova de adulteração.

---

## 🛠️ Stack

**Linguagens** &nbsp; `Python` · `TypeScript` · `Rust` · `C++` · `Dart` · `Go` · `Java` · `C`
**Backend e dados** &nbsp; `FastAPI` · `Fastify` · `PostgreSQL` · `Redis` · `Neo4j` · `Qdrant` · `SQLite` · `Docker`
**IA e GPU** &nbsp; `PyTorch` · `ONNX Runtime` · `YOLO` · `llama.cpp` · `SYCL / Intel oneAPI` · `oneDNN`
**Frontend** &nbsp; `React` · `Next.js` · `Vite` · `Tailwind` · `Flutter` · `Tauri`
**Prática** &nbsp; `Clean Architecture` · `DDD` · `SOLID` · `TDD` · `Design Patterns`

**Formação** — Análise e Desenvolvimento de Sistemas, FAETERJ-Rio (último semestre). Certificações: Ethical Hacking & Network Defense (Cisco), AI Fundamentals & NLP (Cisco / IBM SkillsBuild), Java Foundations (Oracle Academy).

---

<p align="center">
  <a href="https://github.com/FellypeMelo?tab=followers"><img src="https://img.shields.io/github/followers/FellypeMelo?style=for-the-badge&logo=github&logoColor=white&label=Seguidores&labelColor=0d1117&color=1f6feb" alt="Seguidores no GitHub" /></a>
  <a href="https://github.com/FellypeMelo/Open-ChatBot"><img src="https://img.shields.io/github/last-commit/FellypeMelo/Open-ChatBot?style=for-the-badge&logo=git&logoColor=white&label=%C3%9Altimo%20commit&labelColor=0d1117&color=1f6feb" alt="Último commit no Open-ChatBot" /></a>
  <a href="https://fellypemelo.github.io/curriculum-vitae/"><img src="https://img.shields.io/badge/Curr%C3%ADculo%20t%C3%A9cnico%20completo-1f6feb?style=for-the-badge&logo=readthedocs&logoColor=white&labelColor=0d1117" alt="Currículo técnico completo" /></a>
</p>

<p align="center"><i>Aberto a colaborações em engenharia de software, IA aplicada e projetos open source.</i></p>
