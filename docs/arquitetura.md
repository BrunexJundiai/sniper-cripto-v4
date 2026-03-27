# 🏗️ Arquitetura do Sistema

O ecossistema foi projetado de forma modular para garantir escalabilidade, resiliência contra falhas de API e segurança na execução financeira:

1. **Camada de Dados e RAG (`dados_mercado.py`):** - Utiliza a biblioteca Yahoo Finance para coletar dados OHLCV e converter cotações de USD para BRL (Cotação Sintética).
   - Módulo **RAG (Retrieval-Augmented Generation)** integrado via API `rss2json`, extraindo notícias globais em tempo real do portal CoinTelegraph para contornar firewalls institucionais.
2. **Cérebro de IA (`agentes_ia.py`):** - Orquestrado via **LangGraph**. Utiliza um Grafo de Estado (StateGraph) cíclico.
   - **Agente Quantitativo:** Visão 3D de mercado processando RSI, MACD e Bandas de Bollinger.
   - **Agente Fundamentalista:** Analisa o sentimento de mercado baseado nas notícias quentes (RAG).
   - **Conselheiro Chefe:** Sintetiza os dados em um dossiê executivo (LLM Llama 3.3 via Groq).
3. **Orquestrador (`main.py`):** - Gerencia o loop assíncrono de monitoramento proativo.
   - Possui arquitetura blindada (Try/Except interno) para garantir que anomalias em uma única moeda (ex: *delisting* ou poeira de carteira) não derrubem o ecossistema.
   - Interface de comando via Telegram com botões interativos.
4. **Execução (`corretora_ccxt.py`):** - Gateway de comunicação segura com a API da Binance utilizando o protocolo CCXT, garantindo execução de ordens a mercado (Spot) com leitura de saldo em tempo real.