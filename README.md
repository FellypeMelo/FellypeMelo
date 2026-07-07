# Fellype Samuel dos Santos de Melo
### Software Engineer & Tech Lead

<p align="left">
  <img src="https://img.shields.io/badge/Role-Tech%20Lead-blue?style=flat-square" alt="Tech Lead" />
  <img src="https://img.shields.io/badge/Focus-Software%20Architecture-brightgreen?style=flat-square" alt="Software Architecture" />
  <img src="https://img.shields.io/badge/Specialty-AI%20%26%20Deep%20Learning-orange?style=flat-square" alt="AI & Deep Learning" />
  <img src="https://img.shields.io/badge/Academic-First%20Author%20Publication-red?style=flat-square" alt="First Author Publication" />
</p>

<p align="left">
  <a href="https://linkedin.com/in/fellype-samuel" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="mailto:fellypesamuel1@hotmail.com">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
  <a href="https://github.com/FellypeMelo">
    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  </a>
</p>

📍 **Rio de Janeiro, RJ, Brasil** | ✉️ **fellypesamuel1@hotmail.com**

---

### 🧠 Sobre Mim
Sou Software Engineer e estudante do último período de **Análise e Desenvolvimento de Sistemas (FAETERJ-Rio)**. Atuo na intersecção entre arquitetura de backend escalável e Inteligência Artificial aplicada (Deep Learning & NLP). Como Tech Lead, modelo requisitos de negócio em arquiteturas sustentáveis e lidero integrações técnicas de ponta a ponta.

> *"Great software starts by understanding problems before writing code."*

---

### 🚀 Projetos em Destaque

#### 🤖 **OpenChatBot**
*   **Problema:** Dificuldade na orquestração de múltiplos agentes conversacionais locais com memória persistente e controle rígido de privacidade.
*   **Arquitetura:** Desacoplamento estrutural baseado em Clean Architecture e Domain-Driven Design (DDD), separando regras de domínio de adaptadores externos de LLM.
```
┌─────────────────────────────────────────────────────────┐
│                       React UI                          │
└────────────────────┬──────────────▲─────────────────────┘
                     │ HTTP / WS    │ State updates
┌────────────────────▼──────────────┴─────────────────────┐
│                  FastAPI Backend REST                   │
│  ┌───────────────────────────────────────────────────┐  │
│  │              Clean Architecture Core              │  │
│  │   ┌─────────────┐   ┌─────────────┐   ┌─────────┐ │  │
│  │   │ Controllers │──►│ Use Cases   │──►│ Domain  │ │  │
│  │   └─────────────┘   └─────────────┘   └─────────┘ │  │
│  └───────────────────────────────────────────────────┘  │
└────────────────────┬──────────────▲─────────────────────┘
                     │ Repository   │ Memory / Context
┌────────────────────▼──────────────┴─────────────────────┐
│            Local LLM & Persistence (SQLite)             │
└─────────────────────────────────────────────────────────┘
```
*   **Stack:** `React` `Vite` `FastAPI` `Python` `TDD`
*   **Resultado:** Plataforma modular altamente personalizável para execução e teste de agentes locais privados.
*   **Links:** [Código do Repositório](https://github.com/FellypeMelo/OpenChatBot) | [Documentação do Sistema](https://github.com/FellypeMelo/OpenChatBot#readme)

#### 🎓 **Educa — Gestão Escolar**
*   **Problema:** Regras de negócio complexas e acopladas para gerenciamento de turmas, alunos e notas em instituições de ensino de médio porte.
*   **Arquitetura:** Liderança técnica na diagramação e modelagem relacional de banco de dados, mapeamento de requisitos e estrutura MVC desacoplada.
```
┌─────────────┐       ┌─────────────┐       ┌─────────────┐
│  React UI   ├──────►│ FastAPI API ├──────►│ Relational  │
│  (Frontend) │◄──────┤  (Backend)  │◄──────┤ DB (MySQL)  │
└─────────────┘       └─────────────┘       └─────────────┘
```
*   **Stack:** `React` `Vite` `FastAPI` `Python` `MySQL`
*   **Resultado:** TCC concluído com sucesso com arquitetura robusta e documentação técnica abrangente.
*   **Links:** [Código do Repositório](https://github.com/FellypeMelo/Educa) | [Documentação Arquitetural](https://github.com/FellypeMelo/Educa#readme)

#### 🔬 **Segmentação de Trypanosoma cruzi**
*   **Problema:** Lentidão na identificação manual de estruturas biológicas complexas do parasita em imagens de microscopia de varredura.
*   **Arquitetura:** Pipeline de visão computacional otimizado para inferência automatizada por meio de segmentação de instâncias.
```
┌───────────────────┐      ┌──────────────────┐      ┌───────────────────┐
│ Imagens Eletrônicas├─────►│  YOLOv8-seg Core ├─────►│ Estruturas        │
│ de Microscopia    │      │  (Fine-Tuning)   │      │ Segmentadas (PNG) │
└───────────────────┘      └──────────────────┘      └───────────────────┘
```
*   **Stack:** `YOLOv8-seg` `Python` `OpenCV`
*   **Resultado:** Aceleração do tempo de análise de imagens científicas no Laboratório Fuzzy.
*   **Links:** [Repositório da Pesquisa](https://github.com/FellypeMelo/Trypanosoma-segmentation)

#### 🔬 **Classificação Automática de Embriões**
*   **Problema:** Inconsistências de classificação morfológica humana no desenvolvimento inicial de embriões.
*   **Arquitetura:** Pipeline de classificação de Deep Learning integrado à interface web, treinado no FuzzyLab em parceria com pesquisa externa de mestrado.
```
┌─────────────┐      ┌─────────────┐      ┌─────────────┐      ┌─────────────┐
│ Imagens do  ├─────►│ ResNet-18   ├─────►│ FastAPI API ├─────►│  React UI   │
│ Embrião     │      │ (PyTorch)   │      │ (Endpoints) │      │ (Visual)    │
└─────────────┘      └─────────────┘      └─────────────┘      └─────────────┘
```
*   **Stack:** `PyTorch` `ResNet-18` `FastAPI` `Python` `React`
*   **Resultado:** Integração bem-sucedida de modelos com validação cruzada k-fold para suporte à tomada de decisões médicas.
*   **Links:** [Repositório da Integração](https://github.com/FellypeMelo/Embryo-classification)

---

### 📝 Pesquisa & Publicações Científicas
*   **Primeiro Autor:**
    > **MELO, F. S. S.** et al. *Arquitetura Algorítmica para Atenção Sustentável: o Modelo Be-Productive como Resposta à Sobrecarga Cognitiva no Capitalismo de Vigilância*. Revista Tópicos, 2026.
    > 🔗 **DOI:** [10.70773/revistatopicos/781363235](https://doi.org/10.70773/revistatopicos/781363235)

---

### 🌐 Open Source & Contribuições
*   **Foco:** Criação de pacotes modulares de IA que priorizam execução local e privacidade.
*   **Iniciativa Principal:** Manutenção do **OpenChatBot** para simplificar conexões de LLMs locais à comunidade.
*   **Objetivos:** Contribuir com melhorias em wrappers de APIs e bibliotecas de arquitetura limpa em Python.

---

### 🚀 Atualmente & Roadmap de Estudos
*   [ ] Refatoração de orquestração multiagentes locais descentralizados.
*   [ ] Design de **Sistemas Distribuídos** (Event-Driven Architecture, CQRS, Apache Kafka).
*   [ ] Otimização de deploys de visão computacional em tempo real usando WebSockets.

---

### 🛠️ Competências Técnicas & Práticas

| Categoria | Tecnologias / Metodologias |
| :--- | :--- |
| **Linguagens** | Python, JavaScript (ES6+), Java, PHP, C |
| **Backend & Web** | FastAPI, APIs RESTful, React, Vite, HTML5, CSS3, WordPress, Elementor |
| **Inteligência Artificial** | PyTorch, Deep Learning, CNNs, Transformers, Processamento de Linguagem Natural (NLP), YOLOv8, Watson Studio |
| **Práticas de Engenharia** | Clean Architecture, SOLID, Domain-Driven Design (DDD), Design Patterns, Clean Code, TDD, XP |
| **Banco de Dados & Ferramentas** | Modelagem de Dados, SQL, MySQL, Git, GitHub |

---

### 🎓 Formação & Certificações
*   **Análise e Desenvolvimento de Sistemas** — *FAETERJ-Rio* (Último Período)
*   🛡️ **Ethical Hacker & Network Defense** — *Cisco Networking Academy*
*   🧠 **AI Fundamentals & Artificial Intelligence** — *Cisco & IBM SkillsBuild* (NLP, Watson Studio)
*   ☕ **Java Foundations** — *Oracle Academy*

---

### 📊 Estatísticas do GitHub

<p align="center">
  <img height="180" src="https://github-readme-stats.vercel.app/api?username=FellypeMelo&show_icons=true&theme=tokyonight&include_all_commits=true&locale=pt-br" alt="Estatísticas do GitHub de Fellype" />
  <img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=FellypeMelo&theme=tokyonight&layout=compact&custom_title=Tecnologias%20Mais%20Usadas&langs_count=9" alt="Tecnologias mais usadas pelo Fellype" />
</p>

<p align="center">
  <img height="180" src="https://github-readme-streak-stats.herokuapp.com/?user=FellypeMelo&theme=tokyonight" alt="Estatísticas de Streak do Fellype" />
</p>

---

### 📞 Contato & Conexões

| Canal | Link / Identificador |
| :--- | :--- |
| **💼 Profissional** | [LinkedIn](https://linkedin.com/in/fellype-samuel) \| [GitHub](https://github.com/FellypeMelo) \| [Email](mailto:fellypesamuel1@hotmail.com) |
| **🎓 Acadêmico** | [ORCID](https://orcid.org/0009-0000-3274-0343) |

<br>

> 📬 *Estou sempre aberto a colaborar em projetos de engenharia de software, pesquisa aplicada, inteligência artificial e iniciativas open source. Vamos construir algo incrível juntos!*
