# Trading Dashboard

A single-file, self-contained trading dashboard built on [TradingView](https://www.tradingview.com/)'s
free embeddable widgets. Live charts, buy/sell technicals, watchlists, news, and
an economic calendar — for market analysis and monitoring.

> This dashboard is for **analysis and monitoring**. TradingView embed widgets
> don't place orders — execution happens through your broker/exchange. Each
> symbol has a "Trade on TradingView" deep link. Not financial advice.

## Run it

It's just one HTML file — no build step. Either:

- Open `index.html` in a browser, **or**
- Serve it (widgets load best over http):
  ```bash
  # any static server, e.g.
  npx serve .
  ```

## Features

- **My portfolio (PnL)** — track what you actually own (IDX stocks, crypto, US
  stocks); live mark-to-market in IDR, unrealized + daily PnL, close-position
  flow with a realized-PnL log. Stored in `localStorage` only — nothing leaves
  your browser. Shared with the finance dashboard on the same origin.
- **Today's briefing** — plain-language takeaways: market mood, the healthiest
  setup right now, what to avoid, portfolio health, and a rule of the day.
- **Opportunity radar** — every symbol in the basket scored 0–100 and ranked;
  click a row to open its full analysis.
- **Ticker tape** — live prices across crypto, US stocks, forex, indices, gold, oil.
- **Symbol switcher** — search box (`EXCHANGE:TICKER`, e.g. `NASDAQ:TSLA`) plus
  quick-pick chips grouped by Crypto / Stocks / Forex / Indonesia. The chart,
  technicals, symbol info, and news all follow the selected symbol.
- **Advanced chart** — real-time candles with EMA + RSI, drawing tools, indicators.
- **Technicals** — a buy/sell gauge across multiple timeframes.
- **Watchlist** — tabbed market overview (Crypto, US Stocks, Forex, Indonesia).
- **News** — headlines for the selected symbol.
- **Economic calendar** — upcoming events (US, EU, ID, JP, GB, CN).
- **Dark / light theme**, remembered across reloads (along with your last symbol).

## Customizing

Everything is configured in plain JS objects near the top of the `<script>` in
`index.html`:

- `GROUPS` — the quick-pick chips.
- `TICKER_SYMBOLS` — the scrolling ticker tape.
- `MARKET_TABS` — the watchlist tabs and their symbols.
- Default symbol/theme — `SYMBOL` / `THEME` (also persisted to `localStorage`).

Symbol format is `EXCHANGE:TICKER` — e.g. `BINANCE:BTCUSDT`, `NASDAQ:AAPL`,
`FX_IDC:USDIDR`, `IDX:BBCA`.
