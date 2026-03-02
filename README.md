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

```bash
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
