# 🏗️ Arquitetura do Sistema (V4.1)

O ecossistema foi projetado de forma modular para garantir escalabilidade, resiliência contra falhas de API, gestão de patrimônio e segurança na execução financeira. A arquitetura divide-se em 5 camadas principais:

1. **Camada de Dados e RAG (`dados_mercado.py`):** - Utiliza a biblioteca Yahoo Finance para coletar dados OHLCV e converter cotações para BRL (Cotação Sintética).
   - Módulo **RAG (Retrieval-Augmented Generation)** integrado via API `rss2json`, extraindo notícias globais em tempo real para contornar firewalls institucionais.

2. **Cérebro de IA e Gestão de PnL (`agentes_ia.py`):** - Orquestrado via **LangGraph** utilizando um Grafo de Estado (StateGraph).
   - **Agente Quantitativo:** Visão 3D de mercado cruzando RSI, MACD, Bandas de Bollinger e o **Lucro/Prejuízo Real (PnL)** da carteira.
   - **Agente Fundamentalista:** Analisa o sentimento de mercado (pânico/euforia) baseado em notícias.
   - **Conselheiro Chefe:** Sintetiza os dados em um dossiê executivo (LLM Llama 3.3 via Groq) focado em proteção de caixa e realização de lucros (*Take Profit*).

3. **Orquestrador de Swing Trade (`main.py`):** - Gerencia o loop assíncrono de monitoramento proativo com **Gatilho de Giro Rápido (3%)**.
   - Arquitetura blindada (Try/Except interno) para garantir que anomalias em uma moeda não derrubem o ecossistema.
   - Painel de Controle via Telegram com botões interativos independentes do veredito da IA.

4. **Execução e Extrato (`corretora_ccxt.py`):** - Gateway de comunicação segura com a Binance via protocolo CCXT.
   - Realiza execução de ordens a mercado (Spot), leitura de saldos e **varredura na blockchain/extrato** para cálculo milimétrico do Preço Médio de compra.

5. **Master Dashboard (`integra_saldos.py`):** - Loop em background (30 minutos) focado em relatórios institucionais.
   - Processamento de DataViz utilizando `matplotlib` e `squarify` para renderizar gráficos Treemap em PDF na memória (Headless) com ordenação em degradê de volume financeiro.