# PulseBTC15 – 15-Minute BTC Pulse Trader on Polymarket

**PulseBTC15** is a production-grade autonomous trading bot engineered to capture Bitcoin micro-impulses and trends in **Polymarket**'s 15-minute prediction markets.

Built on **NautilusTrader** (open-source HFT-grade framework), it features advanced feature engineering, online self-learning models, full Grafana/Prometheus monitoring, and military-grade risk controls (Half-Kelly sizing, drawdown breakers, circuit breakers).

→ **MetaQuant Universe** – 15 Years of Trading Innovation  
From raw code to autonomous market intelligence.

🌐 https://metaquantuniverse.com  
📊 https://metaquantuniverse.com/polymarket

## 🔥 Why PulseBTC15?

- **15-minute timeframe**: Ideal balance between clean signals and low noise (vs. noisy 1s scalping or slow 4h swings)
- **Polymarket-native**: Leverages on-chain CLOB, EIP-712 signing, low-latency WebSocket + RPC execution
- **Self-adaptive learning**: Model evolves live (no frozen backtest that dies on day one)
- **Pro-grade visualization**: Ready-to-use Grafana dashboards (PnL, exposure, signal strength, latency, risk metrics)
- **Risk-first philosophy**: Half-Kelly / fractional sizing, max daily drawdown, trailing stops, volatility filters

This is battle-tested architecture refined over months—not a weekend script.

## ✨ Key Features

- Polymarket integration (WebSocket + REST + on-chain execution)
- 15-min OHLCV pipeline + order-flow features + sentiment proxies
- Lightweight feature store with real-time engineering
- Adaptive model (LightGBM / lightweight NN / ensemble) with online retraining
- Reliable execution: FOK/IOC orders + controlled slippage
- Military Risk Engine:
  - Half-Kelly position sizing
  - Circuit breakers (volatility spikes, disconnects, daily PnL caps)
  - Hard exposure & position limits
- Monitoring stack:
  - Prometheus metrics exporter
  - Grafana dashboards (included)
  - Optional Telegram / Discord / email alerts
- Structured JSONL logging with rotation
- Backtest + paper trading modes
- Simple one-click launcher (soon: .exe / Docker one-liner)

## Prerequisites

- Python 3.10+
- Polymarket API keys (wallet private key)
- (Recommended) Machine with ≥8 GB RAM for Grafana + Prometheus

## Quick Install (≈5 minutes)

# 1. Clone the repo
git clone https://github.com/metaquantAI/PulseBTC15.git
cd PulseBTC15

# 2. Create virtual environment
python -m venv .venv
source .venv/bin/activate          # Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Copy and configure .env
cp .env.example .env
# → Edit .env with your Polymarket keys + Telegram (optional)

# 5. (Optional but recommended) Start monitoring stack
docker-compose up -d               # launches Prometheus + Grafana

# 6. Run the bot – start in paper mode!
python src/main.py --mode paper
See INSTALL.md for Docker, systemd, VPS, or production deployment guides.
.env Configuration Example
env# Polymarket
POLYMARKET_PRIVATE_KEY=0x...
POLYMARKET_CHAIN_ID=137               # Polygon Mainnet
POLYMARKET_RPC_URL=https://polygon-rpc.com

# Trading parameters
SYMBOL=BTC-USD
TIMEFRAME=15m
POSITION_MAX_PCT=0.05                 # max 5% of capital per trade
DAILY_LOSS_CAP_PCT=-3.0
MAX_DRAWDOWN_PCT=-15.0

# Optional Telegram alerts
TELEGRAM_BOT_TOKEN=...
TELEGRAM_CHAT_ID=...
Monitoring – Grafana Dashboards
After docker-compose up, open: http://localhost:3000
Default login: admin / admin
Included dashboards:

PulseBTC15 Overview
PnL & Performance
Signal Quality Analysis
Execution Latency
Risk & Exposure Metrics

Risk Disclaimer
PulseBTC15 is NOT financial advice.
Trading involves substantial risk of loss — potentially your entire capital.
Use only risk capital you can afford to lose.
Always test extensively in paper/simulation mode for weeks before live deployment.
No guaranteed profits. Edges decay. Markets change.
2025–2026 Roadmap

 One-liner Docker full-stack deployment
 Windows .exe launcher (PyInstaller)
 External signals (funding rates, on-chain flows)
 Multi-asset support (ETH, SOL…)
 Experimental RL agent (PPO / SAC)
 Cloud templates (Render, Railway, AWS)

Contribute / Get in Touch
PRs welcome! Open an issue for bugs, ideas, or questions.
Part of MetaQuant Universe?
→ https://metaquantuniverse.com
→ https://metaquantuniverse.com/polymarket
Built with precision & persistence — 15 years in the trenches.
PulseBTC15 – Feel the pulse. Trade the edge.
You’re good to go!  
