# 📖 Dicionário de Dados - Sniper Cripto V4.1

Este documento descreve as principais variáveis, métricas quantitativas avançadas e entidades de dados com foco em rentabilidade processadas pelo ecossistema.

## 1. Entidades de Mercado (Market Data)
| Variável | Descrição | Unidade/Tipo |
| :--- | :--- | :--- |
| `ticker` | Símbolo do ativo no mercado (ex: BTC, SOL, ETH). | String |
| `preco_atual` | Última cotação capturada convertida para moeda local. | Float (BRL) |
| `volatilidade_15m` | Variação percentual do preço em janelas curtas de monitoramento. | Percentual (%) |
| `noticias` | Feed dinâmico com as manchetes globais mais recentes do ativo (RAG). | String |

## 2. Indicadores Quantitativos e PnL
| Métrica | Definição Técnica | Objetivo |
| :--- | :--- | :--- |
| **RSI (14)** | Relative Strength Index sobre os últimos 14 períodos. | Identificar Sobrevenda (< 30) ou Sobrecompra (> 70). |
| **MACD** | Moving Average Convergence Divergence. | Antecipar cruzamentos de reversão de tendência. |
| **Bollinger** | Média móvel +- 2 Desvios Padrões (Janela de 20). | Identificar zonas de suporte (piso) ou resistência (teto). |
| **Preço Médio (PM)** | Total Gasto (BRL) / Quantidade Comprada na corretora. | Calcular a base de custo real do investidor. |
| **Lucro/Prejuízo** | Variação % entre o `preco_atual` e o `preco_medio`. | Ditar a urgência de realização de lucro (*Take Profit*). |

## 3. Entidades da Corretora (Wallet & Execution)
| Campo | Descrição | Origem |
| :--- | :--- | :--- |
| `free_balance` | Saldo em criptomoeda disponível para venda imediata. | `balance['free']` |
| `caixa_brl` | Montante líquido total em Reais. | `balance['BRL']` |
| `precos_referencia` | Dicionário em RAM com o preço âncora para disparo de gatilhos. | Loop Orquestrador |

## 4. Contexto dos Agentes de IA (LangGraph State)
| Atributo | Descrição | Responsável |
| :--- | :--- | :--- |
| `parecer_quant` | Análise cruzando RSI, MACD, Bollinger e o Lucro da Carteira. | Agente Quantitativo |
| `parecer_fund` | Texto avaliando pânico/euforia baseado nas notícias RAG. | Agente Fundamentalista |
| `dossie_final` | Mensagem em Markdown com Veredito de Compra/Venda/Aguardar. | Conselheiro Chefe |