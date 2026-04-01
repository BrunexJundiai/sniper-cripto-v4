# 🏗️ Arquitetura do Sistema (V4.1)

O ecossistema foi projetado de forma modular para garantir escalabilidade, resiliência contra falhas de API, gestão de patrimônio e segurança na execução financeira. A arquitetura divide-se em 6 camadas principais:

### 1. Camada de Dados e RAG (`dados_mercado.py`)
![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![RSS](https://img.shields.io/badge/RSS_Feed-FFA500?style=for-the-badge&logo=rss&logoColor=white) 
- Utiliza bibliotecas financeiras nativas para coletar dados OHLCV e converter cotações para BRL (Cotação Sintética).
- Módulo **RAG (Retrieval-Augmented Generation)** integrado via API `rss2json`, extraindo notícias globais em tempo real para contornar firewalls institucionais e municiar a IA com contexto atualizado.

### 2. Cérebro de IA e Gestão de PnL (`agentes_ia.py`)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white) ![Groq](https://img.shields.io/badge/Groq-f55036?style=for-the-badge&logo=groq&logoColor=white)
- Orquestrado via **LangGraph** utilizando um Grafo de Estado (StateGraph).
- **Agente Quantitativo:** Visão 3D de mercado cruzando RSI, MACD, Bandas de Bollinger e o **Lucro/Prejuízo Real (PnL)** da carteira.
- **Agente Fundamentalista:** Analisa o sentimento de mercado (pânico/euforia) baseado nas notícias capturadas pelo RAG.
- **Conselheiro Chefe:** Sintetiza os dados em um dossiê executivo utilizando o modelo **Llama 3.3 via Groq**, focado em proteção de caixa e realização de lucros (*Take Profit*).

### 3. Orquestrador de Swing Trade (`main.py`)
![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)
- Gerencia o loop assíncrono de monitoramento proativo com **Gatilho de Giro Rápido (3%)**.
- Arquitetura blindada (Try/Except interno) para garantir que anomalias ou interrupções em uma moeda não derrubem o ecossistema.
- Painel de Controle via API do Telegram com botões interativos (`CallbackQuery`), permitindo intervenção humana independente do veredito da IA.

### 4. Execução e Extrato (`corretora_ccxt.py`)
![Binance](https://img.shields.io/badge/Binance-F3BA2F?style=for-the-badge&logo=binance&logoColor=black) ![CCXT](https://img.shields.io/badge/CCXT-4db33d?style=for-the-badge&logo=bitcoin&logoColor=white)
- Gateway de comunicação segura com a Binance via protocolo CCXT, garantindo padronização de requisições.
- Realiza execução de ordens a mercado (Spot), leitura de saldos consolidados e **varredura na blockchain/extrato** histórico para cálculo milimétrico do Preço Médio de compra.

### 5. Master Dashboard (`integra_saldos.py`)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) ![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
- Loop executado em background (a cada 30 minutos) focado na geração de relatórios de nível institucional.
- Processamento intensivo de DataViz utilizando `pandas`, `matplotlib` e `squarify` para renderizar gráficos complexos (Treemap, Regressão Linear) diretamente em PDF na memória (Headless), otimizando o envio seguro dos documentos.

### 6. Infraestrutura e Deploy (Nuvem)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Oracle Cloud](https://img.shields.io/badge/Oracle_Cloud-F80000?style=for-the-badge&logo=oracle&logoColor=white) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
- Código 100% conteinerizado utilizando `docker-compose`, garantindo isolamento de dependências e previsibilidade de ambiente.
- Hospedado em servidor Linux (Ubuntu) na **Oracle Cloud Infrastructure (OCI)**.
- Operação *Always-On* (24/7), garantindo latência ultrabaixa nas requisições da exchange e zero dependência de hardware local.