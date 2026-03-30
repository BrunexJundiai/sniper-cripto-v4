# ⚖️ Regras de Negócio - Sniper Cripto V4.1

Este documento formaliza as políticas de execução, travas de segurança e lógicas financeiras adotadas pelo robô para garantir a proteção do patrimônio.

## 1. Gatilhos de Operação (Swing Trade / Giro Rápido)
* **Sensibilidade de Disparo (3%):** O ecossistema monitoriza a carteira a cada 15 minutos. Se qualquer ativo registrar uma alta ou queda igual ou superior a **3.0%** em relação à última marcação de memória, o Conselho de Administração (IA) é acionado.
* **Alvos Dinâmicos:** O preço de referência de um ativo é atualizado (resetado) sempre que ele dispara o gatilho, permitindo rastrear ralis contínuos de alta ou facas caindo (quedas sucessivas).

## 2. Governança e Decisão Humana
* **Painel Autônomo:** O veredito da IA (Comprar, Vender ou Aguardar) possui caráter puramente consultivo. 
* **Regra de Disponibilidade de Botões:** * O botão **"✅ Comprar"** só é exibido se o `caixa_brl` for superior ao valor mínimo exigido pela exchange.
  * O botão **"💰 Vender"** é exibido sempre que o usuário possuir qualquer saldo do ativo (saldo > 0.00001), permitindo a realização de lucro imediato (Giro), mesmo que a IA sugira "Aguardar".

## 3. Cálculo de PnL (Profit and Loss) e Preço Médio
* **Origem dos Dados:** O robô varre o endpoint `fetch_my_trades` da Binance limitando-se aos últimos 500 trades por ativo.
* **Exclusão de Transferências:** Ativos comprados fora da Binance (ex: Mercado Pago ou P2P) e transferidos para a corretora não possuem histórico financeiro na API. Nesses casos, o robô atribui o Preço Médio como `0.0` e desativa o cálculo de PnL no dossiê.
* **Take Profit Consciente:** A IA é instruída a priorizar ordens de Venda sempre que o RSI estiver elevado (>70) **somado** a um `lucro_pct` positivo do usuário.

## 4. Relatórios Executivos (Master Dashboard)
* **Periodicidade:** A cada 30 minutos (independente de gatilhos de volatilidade).
* **Filtro Visual:** Moedas fiduciárias de base e Stablecoins (BRL, USDT, USDC) e tokens sem liquidez rastreável (ex: TRUMP/BRL) são ignorados na montagem do gráfico Treemap.
* **Degradê Institucional:** Os blocos do PDF são matematicamente ordenados do maior volume financeiro (`total_moeda`) para o menor, mapeados numa paleta de azuis (do escuro para o claro) para facilitar a leitura de exposição de risco.
* **Trava de API Telegram:** Devido ao limite de 1024 caracteres em legendas de mídia, o sistema envia o texto executivo (DRE) separadamente do anexo PDF.

## 5. Limites de Corretora
* **Ordem Mínima:** Operações com valor financeiro inferior a R$ 25,00 são bloqueadas antes de serem enviadas à API, prevenindo erros de *LOT_SIZE* e *MIN_NOTIONAL* da Binance.