---
name: nse-market-analysis
description: NSE/BSE Indian stock market analysis with technical indicators, sector rotation tracking, and swing trade signal detection. Use when the user asks about Indian stocks, NIFTY, Bank NIFTY, specific NSE symbols, market trends, or trading setups.
---

# NSE Market Analysis

Analyse Indian stock market data from NSE/BSE with technical indicators, sector rotation tracking, and swing trade signal detection.

## When to Use This Skill

- User asks about NIFTY, Bank NIFTY, or any NSE-listed stock
- User wants market analysis, stock comparison, or sector performance
- User asks for swing trade setups, support/resistance levels, or technical signals
- User mentions Indian market, NSE, BSE, Sensex, or specific symbols like RELIANCE, TCS, INFY
- User asks "what should I buy" or "what's trending in the market"

## Data Sources

Use these free data sources in priority order:

1. **Yahoo Finance API** (via yfinance): `pip install yfinance` — most reliable for Indian stocks. Use `.NS` suffix for NSE (e.g., `RELIANCE.NS`, `^NSEI` for NIFTY 50).
2. **Google Finance**: Quick price checks via web search for `[SYMBOL] NSE price today`.
3. **NSE India website**: For FII/DII data, bulk deals, and delivery percentage. Scrape `nseindia.com` with proper headers.
4. **MoneyControl**: For news, earnings, and fundamental data.

## Analysis Framework

### Quick Price Check
When user asks "what's NIFTY at" or "check [SYMBOL]":
```
Fetch current price, day change (%), 52-week high/low.
Format: SYMBOL: ₹PRICE (±CHANGE%) | 52W: ₹LOW–₹HIGH | Vol: XM
```

### Technical Analysis
When user asks for analysis on a specific stock:

1. **Trend**: 20 EMA vs 50 EMA vs 200 EMA — bullish/bearish/sideways
2. **RSI (14)**: Overbought (>70), oversold (<30), neutral
3. **MACD**: Signal line crossover, histogram direction
4. **Volume**: Compare today vs 20-day average — accumulation or distribution
5. **Support/Resistance**: From recent swing highs/lows (last 3 months)
6. **Delivery %**: >50% suggests institutional interest (from NSE bhavcopy)

### Sector Rotation
When user asks about sector performance or "what sectors are hot":

Track these NIFTY sectoral indices:
- NIFTY IT, NIFTY Bank, NIFTY Pharma, NIFTY Auto, NIFTY Metal
- NIFTY Realty, NIFTY Energy, NIFTY FMCG, NIFTY Media, NIFTY PSU Bank

Compare 1-week and 1-month returns. Sectors rotating IN (improving relative strength) are buying opportunities. Sectors rotating OUT are sells.

### Swing Trade Signals
When user asks for trade setups or "what looks good to buy":

Scan NIFTY 50 stocks for:
1. **Pullback to 20 EMA** in an uptrend (price above 200 EMA, RSI 40-60, touching 20 EMA)
2. **Breakout above resistance** with volume spike (>1.5x 20-day avg)
3. **Bullish divergence** — price making lower lows, RSI making higher lows
4. **Delivery % > 60%** with price up — smart money accumulating

Output format:
```
SIGNAL: [BUY/WATCH] SYMBOL
Entry: ₹PRICE | SL: ₹PRICE (RISK%) | Target: ₹PRICE (REWARD%)
R:R Ratio: X:1
Reason: [1-line technical justification]
```

### Portfolio Review
When user provides holdings:

1. Calculate portfolio weight per stock
2. Flag concentration risk (>20% in one stock)
3. Show sector allocation pie
4. Calculate overall portfolio beta vs NIFTY
5. Suggest rebalancing if any position is >2 standard deviations from target weight

## Important Notes

- Always mention that this is analysis, not financial advice
- IST timezone for all market references (market hours: 9:15 AM – 3:30 PM IST)
- NSE symbols don't have exchange prefix — use RELIANCE not NSE:RELIANCE
- For yfinance, append .NS for NSE and .BO for BSE
- F&O data: check lot sizes at nseindia.com before discussing options
- Never recommend specific buy/sell actions as advice — present data and let the user decide

## Example Prompts and Expected Behaviour

| User says | What to do |
|-----------|-----------|
| "Check NIFTY" | Quick price + day change + trend direction |
| "Analyse RELIANCE" | Full technical analysis (trend, RSI, MACD, S/R, volume) |
| "What sectors are hot?" | Sector rotation table, top 3 IN and bottom 3 OUT |
| "Find me a swing trade" | Scan NIFTY 50 for signals, present top 3 setups |
| "Review my portfolio: 50 RELIANCE, 100 TCS, 200 INFY" | Weight analysis, sector allocation, risk flags |
