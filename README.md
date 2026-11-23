<div align="center">

# SAGA

**Sistema de Acompanhamento e Gestão Acadêmica — plataforma web para alunos, professores e instituições**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?logo=firebase&logoColor=black)
![Google Gemini](https://img.shields.io/badge/Google_Gemini-8E75B2?logo=google&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-000000?logo=threedotjs&logoColor=white)
![GSAP](https://img.shields.io/badge/GSAP-88CE02?logo=greensock&logoColor=white)
[![Licença: MIT](https://img.shields.io/badge/licen%C3%A7a-MIT-blue.svg)](./LICENSE)

</div>

---

## 📖 Sobre

**SAGA** (Sistema de Acompanhamento e Gestão Acadêmica) é uma aplicação web que organiza a rotina escolar em dois ambientes distintos: a **área do aluno** e a **área do professor**. Para o aluno, reúne dashboard, atividades, notas, cronograma de estudos, comunicados, chat e recursos de apoio com IA; para o professor, oferece dashboard e gestão de atividades e comunicados.

O projeto é construído em **HTML, CSS e JavaScript puros** (sem framework de *build*): cada página é um arquivo `.html` que carrega um **Design System** compartilhado (`saga-components.js` gera a sidebar e o tema automaticamente). O back-end é o **Firebase** (Authentication + Realtime Database), e recursos de inteligência artificial usam a **API do Google Gemini** (modelos `gemini-2.0-flash` e `gemini-2.0-flash-exp`).

A experiência começa por uma **landing page institucional** com apresentação dos planos e termina no **login**, que autentica o usuário via Firebase e o redireciona para o painel correspondente ao seu perfil. A base visual é o **SAGA Design System**, documentado em `SAGA_DESIGN_GUIDE.md`, com temas claro/escuro, sidebar responsiva e componentes reutilizáveis (cards, KPI widgets, badges de status, toasts e modais). A landing page usa **Three.js**, **GSAP/ScrollTrigger** e **Lenis** para animações 3D e rolagem suave.

> Observações de fidelidade ao código atual: o menu do professor referencia a página `professoralunos.html`, que **não existe** neste repositório; e o perfil **Responsável** está marcado como *"em desenvolvimento"* no login. As chaves do Firebase e da API do Gemini estão **embutidas no código-fonte**.

## ✨ Funcionalidades

- **Landing page** (`index.html`) com partículas 3D (Three.js), animações por scroll (GSAP + ScrollTrigger) e rolagem suave (Lenis).
- Seção de planos: **Básico (R$ 39,99/mês)**, **Pro (R$ 99,99/mês)** e **King (R$ 139,99/mês)**, além de um **Plano para Instituições** com formulário "Peça uma Demonstração".
- **Autenticação** por e-mail e senha via Firebase, com seleção de perfil (Aluno, Responsável, Professor) e animação de transição após o login.
- **Redirecionamento por perfil**: e-mails de professor são encaminhados para `professor/`; os demais, para `aluno/`.
- **Área do aluno**:
  - Dashboard (`alunoinicio.html`) com KPIs de atividades (pendentes, hoje, na semana e concluídas) e marcação de conclusão persistida no Firebase.
  - Atividades (`alunoatvi.html`) com busca.
  - Notas (`alunodash.html`).
  - Cronograma de estudos (`alunocrono.html`) com criação e compartilhamento de eventos.
  - Comunicados (`alunocomu.html`) com busca.
  - Chat global (`alunochat.html`), integrado ao Gemini.
  - Nexus AI (`alunonexus.html`) — assistente conversacional integrado ao Gemini.
  - Exercícios (`alunoexercicios.html`) — gerador de quiz por tópico integrado ao Gemini.
  - Suporte (`alunosuporte.html`).
- **Área do professor**: dashboard (`professordash.html`), gestão de atividades (`professoratividades.html`) e comunicados (`professorcomunicados.html`).
- **SAGA Design System**: sidebar gerada automaticamente (com menus distintos para aluno e professor), cards, KPI widgets, badges semânticos, botões, toasts e modais.
- Sistema de **temas claro/escuro** com persistência em `localStorage` e troca automática de logo.
- **Camada de dados** com Firebase Realtime Database e dados simulados (`saga-data.js`) para demonstração e cálculo de estatísticas.
- Conjunto de utilitários de navegação/animação (`firebase-sidebar.js`, `sidebar-menu.js`, `modern-sidebar.js`, `responsive-sidebar.js`, `simple-menu.js`, `header-menu.js`, `custom-progress-bar.js`, `auto-cleanup.js`, `vinheta-animation.js`).

## 🛠️ Tecnologias

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript_ES6-F7DF1E?logo=javascript&logoColor=black)
![Firebase Auth](https://img.shields.io/badge/Firebase_Auth-FFCA28?logo=firebase&logoColor=black)
![Firebase Realtime Database](https://img.shields.io/badge/Realtime_Database-FFCA28?logo=firebase&logoColor=black)
![Google Gemini](https://img.shields.io/badge/Google_Gemini_API-8E75B2?logo=google&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-000000?logo=threedotjs&logoColor=white)
![GSAP](https://img.shields.io/badge/GSAP-88CE02?logo=greensock&logoColor=white)
![Lenis](https://img.shields.io/badge/Lenis-000000)
![Google Fonts](https://img.shields.io/badge/Inter-Font-4285F4?logo=googlefonts&logoColor=white)

## 📁 Estrutura do projeto

```
saga2.0/
├── index.html                     # Landing page institucional (Three.js + GSAP)
├── login.html                     # Login, seleção de perfil e entrada
├── saga-design-system.css         # Design System principal (variáveis e componentes)
├── saga-additional-styles.css     # Estilos complementares (modais, toasts, formulários)
├── saga-components.js             # Componentes: sidebar, tema, toasts, modais, auth
├── saga-data.js                   # Dados simulados e estatísticas
├── SAGA_DESIGN_GUIDE.md           # Guia de uso do Design System
├── firebase-sidebar.js            # Sidebar com integração Firebase
├── sidebar-menu.js                # Menu lateral
├── modern-sidebar.js              # Variante moderna da sidebar
├── responsive-sidebar.js          # Comportamento responsivo da sidebar
├── simple-menu.js                 # Menu simplificado
├── header-menu.js                 # Menu de cabeçalho
├── custom-progress-bar.js         # Barra de progresso customizada
├── auto-cleanup.js                # Limpeza automática de elementos
├── vinheta-animation.js           # Animação de transição (vinheta)
├── template-aluno.html            # Template base para páginas do aluno
├── universal-style.css            # Estilos globais
├── aluno/
│   ├── alunoinicio.html           # Dashboard do aluno
│   ├── alunodash.html             # Notas
│   ├── alunoatvi.html             # Atividades
│   ├── alunoexercicios.html       # Gerador de exercícios (Gemini)
│   ├── alunocrono.html            # Cronograma de estudos
│   ├── alunocomu.html             # Comunicados
│   ├── alunochat.html             # Chat global (Gemini)
│   ├── alunosuporte.html          # Suporte
│   └── alunonexus.html            # Nexus AI (Gemini)
├── professor/
│   ├── professordash.html         # Dashboard do professor
│   ├── professoratividades.html   # Gestão de atividades
│   └── professorcomunicados.html  # Comunicados
└── logo.png / logoinvertido.png / nexus.png / login.png
```

## 🚀 Como rodar localmente

Por ser um projeto estático, basta servi-lo a partir da raiz do repositório (é necessário um servidor HTTP, pois as páginas usam módulos ES e caminhos relativos):

```bash
# Opção 1: servir com npx
npx serve .

# Opção 2: servir com Python
python -m http.server 8000
```

Depois, acesse:

- Landing page: `http://localhost:8000/index.html`
- Login: `http://localhost:8000/login.html`

> É necessária conexão com a internet para carregar o Firebase, a API do Gemini, os scripts via CDN (Three.js, GSAP, Lenis) e as fontes do Google.

## 🔐 Variáveis de ambiente

> ⚠️ No código atual, a configuração do Firebase e a chave da API do Gemini estão **embutidas diretamente nos arquivos HTML/JS**. Recomenda-se externalizá-las (variáveis de ambiente ou configuração segura) antes de publicar o projeto.

Chaves de configuração utilizadas pela aplicação:

- `FIREBASE_API_KEY`
- `FIREBASE_AUTH_DOMAIN`
- `FIREBASE_DATABASE_URL`
- `FIREBASE_PROJECT_ID`
- `FIREBASE_STORAGE_BUCKET`
- `FIREBASE_MESSAGING_SENDER_ID`
- `FIREBASE_APP_ID`
- `GEMINI_API_KEY`

## 📄 Licença

Distribuído sob a **Licença MIT**. Veja [`LICENSE`](./LICENSE).
