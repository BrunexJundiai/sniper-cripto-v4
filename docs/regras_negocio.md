# ⚖️ Regras de Negócio e Estratégia

### 📊 Estratégia Quantitativa Avançada
O ecossistema utiliza uma abordagem de "Visão 3D" para evitar armadilhas de mercado (como comprar uma faca caindo):
- **Bandas de Bollinger:** Mapeia se o preço atual está esmagado no piso (oportunidade de suporte) ou rompendo o teto (risco de correção).
- **RSI (Relative Strength Index):** Confirma a exaustão. Apenas zonas extremas (< 30 ou > 70) são consideradas gatilhos fortes de assimetria.
- **MACD:** Atua como o juiz final da tendência. Mesmo com RSI baixo, uma compra pode ser vetada pelo Agente Quantitativo se o histograma do MACD estiver fortemente negativo e sem sinais de cruzamento de reversão.

### 📰 Análise Fundamentalista em Tempo Real (RAG)
- O sistema não opera "cego". Antes de emitir qualquer dossiê, o bot consome via feed RSS as manchetes mais recentes do portal *CoinTelegraph*.
- O LLM (Llama 3.3) interpreta o impacto semântico destas notícias para bloquear compras impulsivas em dias de pânico institucional (ex: processos da SEC) ou validar teses de alta.

### 🚨 Gestão de Risco e Governança
- **Gatilho de Volatilidade (10%):** O robô patrulha todos os ativos da carteira na Binance. Caso qualquer moeda sofra uma variação de módulo >= 10% em relação à sua última marcação de preço, o Conselho de IA é automaticamente convocado.
- **Isolamento de Erros:** O loop proativo é blindado. Caso uma moeda antiga (poeira) sofra delisting ou falhe na coleta de dados, o sistema ignora o erro, emite um log e continua a varredura da carteira normalmente.
- **Human-in-the-Loop:** Nenhuma ordem de compra ou venda é submetida à corretora sem a aprovação explícita, manual e com definição de valor pelo gestor através do Telegram.