# 🏗️ Arquitetura do Sistema

O ecossistema foi projetado de forma modular para garantir escalabilidade e segurança:

1. **Camada de Dados (`dados_mercado.py`):** Utiliza a biblioteca Yahoo Finance para coletar dados OHLCV e converter cotações em USD para BRL (Cotação Sintética).
2. **Cérebro de IA (`agentes_ia.py`):** Orquestrado via **LangGraph**. Utiliza um Grafo de Estado onde Agentes Quantitativos e Fundamentalistas processam dados via LLM Llama 3.3 (Groq).
3. **Orquestrador (`main.py`):** Gerencia o loop assíncrono de monitoramento proativo e a interface de comando via Telegram.
4. **Execução (`corretora_ccxt.py`):** Gateway de comunicação segura com a API da Binance utilizando o protocolo CCXT.