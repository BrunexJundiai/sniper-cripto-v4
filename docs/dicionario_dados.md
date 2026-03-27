# 📖 Dicionário de Dados - Sniper Cripto V4.0

Este documento descreve as principais variáveis, métricas e entidades de dados processadas pelo ecossistema, desde a coleta via APIs até a geração do Dossiê de IA.

---

## 1. Entidades de Mercado (Market Data)
Dados brutos coletados via Yahoo Finance e CCXT (Binance).

| Variável | Descrição | Unidade/Tipo |
| :--- | :--- | :--- |
| `ticker` | Símbolo do ativo no mercado (ex: BTC, SOL, ETH). | String |
| `preco_atual` | Última cotação capturada convertida para moeda local. | Float (BRL) |
| `volatilidade_15m` | Variação percentual do preço em janelas de 15 minutos. | Percentual (%) |
| `fechamento_ajustado` | Preço de fechamento histórico utilizado para cálculos estatísticos. | Float (BRL) |

---

## 2. Indicadores Quantitativos (Métricas de Análise)
Camada de inteligência calculada pelo módulo `dados_mercado.py`.

| Métrica | Definição Técnica | Objetivo |
| :--- | :--- | :--- |
| **RSI (14)** | Relative Strength Index calculado sobre os últimos 14 períodos. | Identificar exaustão de tendência (Sobrevenda/Sobrecompra). |
| **Slope (Regressão)** | Coeficiente angular da reta de melhor ajuste (Mínimos Quadrados). | Medir a velocidade e direção da tendência macro. |
| **Viés Preditivo (30d)** | Projeção linear do preço para os próximos 30 dias baseada em regressão. | Estimar o valor intrínseco de curto prazo do ativo. |
| **Variação Gátilho** | Delta entre o preço atual e o preço de referência da última varredura. | Disparar o alerta proativo (Default: 10%). |

---

## 3. Entidades da Corretora (Wallet & Execution)
Informações extraídas diretamente da conta Spot via API da Binance.

| Campo | Descrição | Origem |
| :--- | :--- | :--- |
| `free_balance` | Saldo disponível em conta para execução imediata (Livre). | `balance['free']` |
| `used_balance` | Saldo alocado em ordens abertas ou em garantia (Travado). | `balance['used']` |
| `caixa_brl` | Montante total em Reais disponível para novos aportes. | `balance['BRL']` |
| `exec_price` | Preço real de execução da ordem na exchange. | Binance Order API |

---

## 4. Contexto dos Agentes de IA
Estrutura de dados que compõe o StateGraph do LangGraph.

| Atributo | Descrição | Responsável |
| :--- | :--- | :--- |
| `parecer_quant` | Texto analítico focado em indicadores e estatística. | Agente Quantitativo |
| `parecer_fund` | Texto analítico focado em notícias e cenário macro. | Agente Fundamentalista |
| `veredito_final` | Recomendação conclusiva (Comprar, Vender ou Aguardar). | Conselheiro Chefe |
| `dossie_final` | Mensagem formatada em Markdown para envio via Telegram. | IA Orquestradora |

---