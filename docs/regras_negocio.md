# ⚖️ Regras de Negócio e Estratégia

### 📊 Indicadores Quantitativos
- **RSI (Relative Strength Index):** Utilizado para identificar zonas de exaustão de preço (Sobrevenda < 30 / Sobrecompra > 70).
- **Regressão Linear:** Modelo preditivo de primeiro grau aplicado sobre os últimos 180 dias para identificar a inércia da tendência macro.

### 🚨 Gestão de Risco (Gatilhos)
- **Variação de 10%:** O robô monitora a volatilidade intraday. Caso um ativo mude 10% de preço em relação à última marcação, o Conselho de IA é convocado.
- **Human-in-the-Loop:** Nenhuma ordem é enviada à Binance sem a aprovação explícita e manual do gestor via Telegram.