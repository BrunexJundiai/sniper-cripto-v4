# 📖 Dicionário de Dados - Sniper Cripto V4.0

Este documento descreve as principais variáveis, métricas quantitativas avançadas e entidades de dados processadas pelo ecossistema.

---

## 1. Entidades de Mercado (Market Data)
Dados brutos coletados via Yahoo Finance, CCXT (Binance) e RSS Feeds.

| Variável | Descrição | Unidade/Tipo |
| :--- | :--- | :--- |
| `ticker` | Símbolo do ativo no mercado (ex: BTC, SOL, ETH). | String |
| `preco_atual` | Última cotação capturada convertida para moeda local. | Float (BRL) |
| `volatilidade_15m` | Variação percentual do preço em janelas de monitoramento. | Percentual (%) |
| `noticias` | Feed dinâmico com as 3 manchetes globais mais recentes do ativo. | String (RAG Context) |

---

## 2. Indicadores Quantitativos (Métricas de Análise)
Camada de inteligência técnica calculada em tempo real pelo módulo `dados_mercado.py`.

| Métrica | Definição Técnica | Objetivo |
| :--- | :--- | :--- |
| **RSI (14)** | Relative Strength Index sobre os últimos 14 períodos. | Identificar exaustão de tendência (Sobrevenda < 30 / Sobrecompra > 70). |
| **MACD (Linha/Sinal/Hist)** | Moving Average Convergence Divergence. | Medir o momentum e antecipar cruzamentos de reversão de tendência. |
| **Bandas de Bollinger (Sup/Inf)** | Média móvel +- 2 Desvios Padrões (Janela de 20). | Medir a volatilidade extrema e identificar zonas de suporte (piso) ou resistência (teto). |
| **Viés Preditivo (30d)** | Projeção linear do preço baseada em regressão polinomial de 1º grau. | Estimar a inércia da tendência macro do ativo. |

---

## 3. Entidades da Corretora (Wallet & Execution)
Informações extraídas diretamente da conta Spot via API da Binance.

| Campo | Descrição | Origem |
| :--- | :--- | :--- |
| `free_balance` | Saldo disponível em conta para execução imediata. | `balance['free']` |
| `caixa_brl` | Montante total em Reais disponível para novos aportes. | `balance['BRL']` |
| `precos_referencia` | Dicionário em memória RAM com o preço âncora de cada ativo. | Loop Orquestrador |

---

## 4. Contexto dos Agentes de IA (LangGraph State)
Estrutura de dados `EstadoConselho` que transita entre os nós da IA.

| Atributo | Descrição | Responsável |
| :--- | :--- | :--- |
| `parecer_quant` | Texto analítico cruzando RSI, MACD e Bollinger. | Agente Quantitativo |
| `parecer_fund` | Texto avaliando pânico/euforia baseado nas notícias RAG. | Agente Fundamentalista |
| `dossie_final` | Mensagem formatada em Markdown com o Veredito final. | Conselheiro Chefe |