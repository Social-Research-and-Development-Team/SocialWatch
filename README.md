# 🎯 SocialWatch

<div align="center">

![Social Digital Commerce](https://www.socialsa.com/wp-content/uploads/2024/11/Logo-Colorida-2.webp)

**Dashboard inteligente para monitoramento e análise de testes automatizados**

[![Netlify Status](https://api.netlify.com/api/v1/badges/your-badge-id/deploy-status)](https://app.netlify.com/sites/your-site)
[![GitHub Actions](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-2088FF?logo=github-actions&logoColor=white)](https://github.com/features/actions)
[![Supabase](https://img.shields.io/badge/Database-Supabase-3ECF8E?logo=supabase&logoColor=white)](https://supabase.com)
[![Cypress](https://img.shields.io/badge/Testing-Cypress-17202C?logo=cypress&logoColor=white)](https://www.cypress.io)

[Demo ao Vivo](https://dash-report-cy.netlify.app/)

</div>

---

## 📋 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades](#-funcionalidades)
- [Tecnologias](#-tecnologias)
- [Como Executar os Testes](#-como-executar-os-testes)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Equipe](#-equipe)

---

## 🎯 Sobre o Projeto

**SocialWatch** é um dashboard moderno e responsivo desenvolvido para monitorar, analisar e visualizar resultados de testes automatizados. O projeto oferece uma interface intuitiva para acompanhar métricas de qualidade, histórico de execuções e performance dos testes em tempo real.

### 🎨 Principais Características

- **Dashboard em Tempo Real**: Visualização instantânea de métricas e estatísticas
- **Histórico Completo**: Acompanhamento de todas as execuções de testes
- **Gráficos Interativos**: Visualização de dados com Chart.js
- **Notificações Automáticas**: Integração com Microsoft Teams
- **Métricas de Performance**: Análise de PageSpeed Insights
- **Auto-refresh**: Atualização automática a cada 30 segundos
- **Filtros Avançados**: Busca por data, status e período
- **Responsivo**: Interface adaptável para desktop e mobile


---

## ✨ Funcionalidades

### 📊 Dashboard Principal

- **Cards de Estatísticas**: Total de testes aprovados, falhados, duração média e taxa de sucesso
- **Gráficos Dinâmicos**: Visualização de status e histórico de execuções (24h, 7 dias, 30 dias)
- **Tabela de Execuções**: Listagem paginada com filtros por data e status
- **Detalhes Completos**: Modal com informações detalhadas de cada execução

### 🔍 Recursos Avançados

- **Visão Geral**: Informações gerais (ID, data, branch, ambiente, autor, commit)
- **Lista de Testes**: Detalhamento de todos os testes executados
- **Logs Completos**: Acesso aos logs de execução
- **Artefatos**: Screenshots e vídeos de falhas

### 📢 Integrações

- **Microsoft Teams**: Notificações automáticas com resumo dos testes
- **GitHub Actions**: Integração completa com pipeline de CI/CD
- **PageSpeed Insights**: Métricas de performance das aplicações

---

## 🛠 Tecnologias

### Frontend
- **HTML5, CSS3, JavaScript** - Interface moderna e responsiva
- **Chart.js** - Gráficos interativos e dinâmicos
- **Font Awesome** - Biblioteca de ícones

### Backend & Infraestrutura
- **Netlify Functions** - Serverless functions para API
- **Supabase** - Banco de dados PostgreSQL em nuvem
- **Node.js** - Runtime JavaScript

### Testes & Automação
- **Cypress** - Framework de testes E2E
- **GitHub Actions** - Pipeline de CI/CD automatizado
- **Netlify** - Deploy contínuo e hospedagem

---

## 🚀 Como Executar os Testes

### Pré-requisitos

- Node.js 20.x ou superior
- npm 9.x ou superior

### 1. Instalação

Clone o repositório e instale as dependências:

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/SocialWatch.git
cd SocialWatch

# Instale as dependências
npm install
```

### 2. Executar Testes Localmente

#### Modo Interativo (Recomendado para desenvolvimento)

```bash
npx cypress open
```

Isso abrirá a interface do Cypress onde você pode:
- Selecionar e executar testes individualmente
- Ver os testes rodando em tempo real
- Debugar testes com facilidade

#### Modo Headless (Execução completa)

```bash
npx cypress run
```

Executa todos os testes em modo headless (sem interface gráfica), ideal para CI/CD.

#### Executar testes específicos

```bash
# Executar um arquivo específico
npx cypress run --spec "cypress/e2e/seu-teste.cy.js"

# Executar em um navegador específico
npx cypress run --browser chrome
```

### 3. Executar via GitHub Actions

Os testes são executados automaticamente:

- **A cada push** nas branches `main` ou `develop`
- **A cada pull request** para `main`
- **Agendamento automático**: 4x ao dia (8h, 12h, 16h, 20h - horário de Brasília)

#### Executar manualmente:

1. Vá em **Actions** no GitHub
2. Selecione o workflow **Cypress E2E and Deploy**
3. Clique em **Run workflow**
4. Escolha o ambiente (dev/staging/prod)
5. Clique em **Run workflow**

### 4. Visualizar Resultados

Após a execução dos testes, os resultados são automaticamente:

1. **Salvos no banco de dados** (Supabase)
2. **Exibidos no dashboard** (acesse a URL do site)
3. **Enviados para o Teams** (se configurado)

Acesse o dashboard em: `https://seu-site.netlify.app`

---

## 📁 Estrutura do Projeto

```
SocialWatch/
├── .github/
│   └── workflows/
│       └── pipeline.yml         # Configuração do GitHub Actions
├── cypress/
│   ├── e2e/                     # Testes automatizados
│   ├── fixtures/                # Dados de teste
│   └── support/                 # Comandos customizados
├── netlify/
│   └── functions/               # API serverless
├── app.js                       # Lógica do dashboard
├── style.css                    # Estilos da interface
├── index.html                   # Página principal
├── cypress.config.js            # Configuração do Cypress
├── package.json                 # Dependências do projeto
└── README.md                    # Este arquivo
```

---

## 📊 Como Funciona

1. **Testes são executados** via Cypress (localmente ou GitHub Actions)
2. **Resultados são coletados** e enviados para a API
3. **Dados são salvos** no banco de dados Supabase
4. **Dashboard exibe** as informações em tempo real
5. **Notificações são enviadas** para o Teams (opcional)

---

## 🎯 Casos de Uso

- **Monitoramento de Qualidade**: Acompanhe a saúde dos seus testes
- **Análise de Tendências**: Identifique padrões de falhas ao longo do tempo
- **Relatórios Executivos**: Visualize métricas de forma clara e objetiva
- **Notificações em Tempo Real**: Seja alertado imediatamente sobre falhas
- **Histórico Completo**: Acesse logs e artefatos de execuções passadas

---

## 👥 Equipe

Desenvolvido com ❤️ pela equipe **Social Digital Commerce**

- **Website:** [socialsa.com](https://www.socialsa.com)
- **GitHub:** [Social-Research-and-Development-Team](https://github.com/Social-Research-and-Development-Team)

