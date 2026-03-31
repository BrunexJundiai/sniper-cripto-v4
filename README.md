# 🚀 Sniper Cripto V4.1 - Autonomous Quantitative Intelligence & PnL

Sistema avançado de monitoramento e execução de trading quantitativo para o mercado de criptomoedas, desenhado para arquiteturas de *Family Office*. Utiliza orquestração multi-agentes de IA (LangGraph), Processamento de Linguagem Natural ultra-rápido (Groq/Llama 3.3), RAG para leitura de notícias em tempo real e execução algorítmica via CCXT na Binance, com gestão de risco e PnL (Lucro/Prejuízo) automatizados.

## 🛠️ Stack Tecnológica

| Categoria | Tecnologias e Frameworks |
| :--- | :--- |
| **Linguagem & Core** | ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) |
| **Inteligência Artificial** | ![LangChain](https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white) ![Groq](https://img.shields.io/badge/Groq-f55036?style=for-the-badge&logo=groq&logoColor=white) |
| **Mercado & Notícias (RAG)** | ![Binance](https://img.shields.io/badge/Binance-F3BA2F?style=for-the-badge&logo=binance&logoColor=black) ![CCXT](https://img.shields.io/badge/CCXT-4db33d?style=for-the-badge&logo=bitcoin&logoColor=white) ![RSS](https://img.shields.io/badge/RSS_Feed-FFA500?style=for-the-badge&logo=rss&logoColor=white) |
| **Interface & DataViz** | ![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white) ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) |

## 🧠 Arquitetura de Agentes e Consciência de Bolso (PnL)
O sistema utiliza **LangGraph** para orquestrar um fluxo de decisão com uma inteligência patrimonial única. Os agentes consultam a blockchain/exchange em tempo real para descobrir o **Preço Médio Exato** do usuário. A IA propõe estratégias não apenas baseadas em matemática fria, mas no **Lucro/Prejuízo real da carteira**, recomendando ações de *Take Profit* (Realização de Lucros) em momentos estratégicos.

![Código dos Agentes](img/agentesIA.png)

## 📱 Fluxo de Swing Trade e Tomada de Decisão (Giro Rápido)

O ecossistema é otimizado para capturar volatilidade de curto prazo **(Gatilhos de 3%)**, garantindo total autonomia. A IA aconselha com base no RSI, MACD e Notícias, mas o gestor humano possui um painel de controle absoluto para realizar lucros ou aportar a qualquer momento.

| 1. Dossiê Executivo (PnL) | 2. Painel Autônomo de Giro |
| :---: | :---: |
| ![Dossiê](img/conselho1.png) | ![Escolha](img/conselho2_escolha.png) |

> **Governança Ativa:** Os botões interativos permitem que o usuário ignore ou acate o "Veredito" da IA, decidindo raspar os lucros de uma operação (Vender) ou fechar a análise imediatamente.

## 📊 Master Dashboard Institucional e Deep Dive (Automático)
O robô mantém vigilância constante em duas frentes simultâneas:
1. **Loop Proativo (15 min):** Varredura caçando oportunidades sensíveis de *Swing Trade* (3%).
2. **Boletim Executivo (30 min):** O robô gera um **Relatório PDF Multi-page** autônomo, enviado via Telegram, contendo o Treemap de alocação, DRE Analítico ordenado por lucro real e o Deep Dive técnico das Top moedas.

### 1. Visão Global e DRE Analítico
Consolidação da alocação global em degradê de volume financeiro e status de posições com formatação condicional baseada no PnL Real.

| Mapa de Alocação (Treemap) | DRE Dinâmico (Ordenado por Lucro) |
| :---: | :---: |
| ![Treemap](img/relatorio_cripto2.png) | ![DRE](img/DRE_cripto.png) |

### 2. Deep Dive Técnico (Top Performers)
Geração de lâminas detalhadas para os ativos com melhor performance na carteira, destacando Ação de Preço, cruzamento de PM, MACD, RSI e **Regressão Linear Preditiva (30 dias)** em evidência.

| Ação de Preço e Regressão Linear | Indicadores Técnicos (MACD / RSI) |
| :---: | :---: |
| ![Preço e Regressão](img/top_performance_1.png) | ![Indicadores](img/top_performance_2.png) |

## 🖥️ Monitoramento 360º (Docker)
Infraestrutura conteinerizada (`PYTHONUNBUFFERED=1`) com blindagem anti-crash.

| Operação via Terminal (VS Code) | Status dos Contêineres |
| :--- | :--- |
| ![Logs VS Code](img/log_vscode.png) | ![Docker Status](img/docker.png) |

---

## 📈 Roadmap de Evolução (Concluído)

- [x] **Comando de Consulta Rápida:** Dashboard instantâneo para cálculo de PnL (Lucro/Prejuízo) em tempo real de todos os ativos da Binance via Telegram.
- [x] **Integração Global (Master Dashboard V4.1):** Unificação dos dados com a criação de gráficos automáticos Multi-page em PDF.
- [x] **DRE Dinâmico e Viés Preditivo:** Implementação de regressão linear para 30 dias com cone de projeção e ordenação de ativos por maior lucro líquido em Reais.

---
**Desenvolvido por Bruno Felipe de Almeida** *Especialista em BI & Analytics (USP) | Engenheiro de Dados* [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bruno-felipe-de-almeida/)