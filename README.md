# 🚀 Sniper Cripto V4.0 - Autonomous Quantitative Intelligence

Sistema avançado de monitoramento e execução de trading quantitativo para o mercado de criptomoedas. Utiliza arquitetura multi-agentes de IA (LangGraph), Processamento de Linguagem Natural ultra-rápido (Groq/Llama 3.3), RAG (Retrieval-Augmented Generation) para leitura de notícias em tempo real e execução algorítmica via CCXT na Binance.

## 🛠️ Stack Tecnológica

| Categoria | Tecnologias e Frameworks |
| :--- | :--- |
| **Linguagem & Core** | ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) |
| **Inteligência Artificial** | ![LangChain](https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white) ![Groq](https://img.shields.io/badge/Groq-f55036?style=for-the-badge&logo=groq&logoColor=white) |
| **Mercado & Notícias (RAG)** | ![Binance](https://img.shields.io/badge/Binance-F3BA2F?style=for-the-badge&logo=binance&logoColor=black) ![CCXT](https://img.shields.io/badge/CCXT-4db33d?style=for-the-badge&logo=bitcoin&logoColor=white) ![RSS](https://img.shields.io/badge/RSS_Feed-FFA500?style=for-the-badge&logo=rss&logoColor=white) |
| **Interface & Bot** | ![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white) |
| **Análise de Dados** | ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) |

## 🧠 Arquitetura de Agentes (Human-in-the-Loop)
O sistema utiliza **LangGraph** para orquestrar um fluxo de decisão em que agentes especializados colaboram. O diferencial é a trava de segurança humana: a IA propõe com base em matemática fria e notícias globais, mas o gestor dispõe.

![Código dos Agentes](img/agentesIA.png)

## 📱 Fluxo de Operação e Tomada de Decisão

O ecossistema garante total transparência em cada etapa do trade. Abaixo, o fluxo completo desde o monitoramento até a liquidação:

| 1. Gatilho (Volatilidade) | 2. Dossiê IA | 3. Validação Humana | 4. Execução Binance |
| :---: | :---: | :---: | :---: |
| ![Gatilho](img/gatilho.png) | ![Dossiê](img/conselho1.png) | ![Escolha](img/conselho2_escolha.png) | ![Execução](img/execucao.png) |

> **Governança:** Na etapa 3, os botões interativos permitem que o usuário aprove ou recuse a operação baseando-se no parecer quantitativo (MACD, Bollinger, RSI) e fundamentalista (Notícias), definindo o valor exato do aporte no ato.

## 🖥️ Logs de Monitoramento 360º
O robô mantém vigilância constante (Dockerized com `PYTHONUNBUFFERED=1` para logs em tempo real) com varreduras proativas e blindadas anti-crash a cada 15 minutos em todos os ativos da carteira.

| Operação via VS Code Terminal | Monitoramento de Contêineres |
| :--- | :--- |
| ![Logs VS Code](img/log_vscode.png) | ![Docker Status](img/docker.png) |

---

## 📈 Roadmap de Evolução (Próximos Passos)

- [ ] **Comando de Consulta Rápida (`/carteira`):** Dashboard instantâneo para cálculo de PnL (Lucro/Prejuízo) em tempo real de todos os ativos da Binance via Telegram.
- [ ] **Integração Global (Master Dashboard V3 + V4):** Unificação dos dados de Renda Variável (B3) e Criptoativos em um único DRE automatizado no Google Sheets, consolidando o patrimônio total da família.
- [ ] **Relatórios Mensais em PDF:** Automação de balanço de performance enviado diretamente pelo bot.

---
**Desenvolvido por Bruno Felipe de Almeida** *Especialista em BI & Analytics (USP) | Engenheiro de Dados* [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bruno-felipe-de-almeida/)