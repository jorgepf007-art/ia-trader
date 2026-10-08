# IA Trader v0.5 — Backtest Histórico

Versão seguinte do laboratório v0.4. Aplicação estática HTML/CSS/JavaScript, sem dependências de servidor.

## Executar
1. Extraia o ZIP.
2. Abra `index.html` em um navegador moderno com internet.
3. Selecione mercado, timeframe, quantidade de candles e custo estimado.
4. Clique em **CARREGAR HISTÓRICO E EXECUTAR**.

A aplicação solicita candles históricos à API WebSocket pública da Deriv (app_id público). A disponibilidade depende da rede, do navegador e da API. Nenhuma chave ou conta de trading é necessária; nenhuma ordem é enviada.

## Estratégia experimental
- Sinal no fechamento do candle `i`: EMA(9)/EMA(21) + RSI(14).
- Compra: EMA9 > EMA21 e RSI >= 55.
- Venda: EMA9 < EMA21 e RSI <= 45.
- Entrada simulada na abertura de `i+1`; saída no fechamento de `i+1`.
- O histórico é separado cronologicamente em 70% desenvolvimento e 30% teste.
- Resultado líquido desconta um custo configurável em pips por operação.

## Limitações
O custo informado é uma estimativa constante, não spread histórico. Não são modelados slippage, swaps, latência, liquidez, restrições de execução nem regras de corretora. Os candles mais recentes podem estar incompletos. Não há calibração de probabilidades nem envio de ordens. Backtest não garante desempenho futuro e não constitui recomendação financeira.


## GitHub Pages
Em Settings → Pages, selecione Deploy from a branch, branch `main`, pasta `/ (root)`.
