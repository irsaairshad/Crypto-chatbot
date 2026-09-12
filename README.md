# ◈ CryptoVision

> **Next-Generation Cryptocurrency Market Intelligence & AI Terminal**

![CryptoVision Banner](https://img.shields.io/badge/CryptoVision-v2.0-6366f1?style=for-the-badge&logo=bitcoin&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![WebSocket](https://img.shields.io/badge/WebSockets-Binance%20Live-06b6d4?style=for-the-badge)
![TradingView](https://img.shields.io/badge/Charts-TradingView%20Lightweight-a855f7?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)

---

## 🌟 Overview

**CryptoVision** is an institutional-grade, real-time cryptocurrency intelligence terminal and AI assistant. It integrates high-frequency WebSocket data streams directly from Binance with real-time CoinGecko coin analytics and TradingView Lightweight Charts, offering a sleek, glassmorphic cyber-space trading experience.

---

## ✨ Key Features

- ⚡ **Real-Time WebSocket Streams**:
  - Live 24hr ticker market streams directly from Binance.
  - Sub-second candlestick (Kline) updates across multiple timeframes (`1m`, `5m`, `15m`, `1h`, `4h`, `1d`).
  - Aggregate live trade ticker tracking buyer/seller flow in real time.
- 📈 **Interactive TradingView Candlestick Charts**:
  - Embedded TradingView Lightweight Charts with dynamic viewport auto-resizing.
  - Responsive timeframe switching and currency pair search with instant live data hydration.
- 🤖 **CryptoVision AI Assistant**:
  - Context-aware crypto market chatbot powered by Google Gemini and live market feeds.
  - Answers queries on real-time prices, market caps, tokenomics, technical definitions, and fiat conversions.
  - Floating modal terminal with expandable workspace and streaming response animations.
- 🌐 **Live Market Directory & Marquee**:
  - Auto-scrolling ticker tape highlighting top unit-price cryptocurrency pairs.
  - Filterable market directory with 24h highs, lows, and volume metrics.
- 🎨 **Modern Cyber-Space UI**:
  - Deep space theme with Electric Violet, Neon Cyan, and Radiant Purple gradients.
  - Glassmorphic panels with subtle glowing borders and micro-interactions.
  - 100% responsive design optimized for mobile, tablet, and widescreen displays.

---

## 🏗️ Architecture & Tech Stack

```
crypto-chatbot-main/
├── backend/
│   ├── main.py               # FastAPI application & route endpoints
│   ├── schemas/
│   │   └── chat.py           # Pydantic models for chat requests/responses
│   └── services/
│       ├── chatbot.py        # AI Assistant engine & Gemini API integration
│       ├── coingecko.py      # CoinGecko market & circulating supply APIs
│       └── currency.py       # Fiat currency conversion utilities
├── frontend/
│   └── index.html            # Complete Single-Page Application (HTML5 / Vanilla CSS / JS)
├── requirements.txt          # Python project dependencies
└── README.md                 # Project documentation
```

### Tech Stack
- **Frontend**: HTML5, Vanilla CSS3 (Glassmorphism & Custom Design Tokens), Vanilla JavaScript (ES6+), TradingView Lightweight Charts.
- **Backend**: Python 3.10+, FastAPI, Uvicorn, HTTPX, Pydantic.
- **Data Providers**: Binance WebSockets & REST API, CoinGecko REST API, Gemini LLM API.

---

## 🚀 Quick Start Guide

### Prerequisites
- Python 3.10 or higher installed.
- (Optional) Google Gemini API Key for AI Assistant capabilities.

### 1. Clone & Navigate to Project
```bash
git clone https://github.com/your-username/crypto-chatbot-main.git
cd crypto-chatbot-main
```

### 2. Set Up Virtual Environment (Recommended)
```bash
# Windows (PowerShell)
python -m venv venv
.\venv\Scripts\Activate.ps1

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables
Create a `.env` file in the project root:
```env
GEMINI_API_KEY=your_gemini_api_key_here
GEMINI_MODEL=gemini-2.5-flash
```
*(Note: If no Gemini API key is provided, the live market charts and ticker data will still function normally, while the assistant will inform users when the key is missing.)*

### 5. Launch Application
```bash
uvicorn backend.main:app --reload --port 8000
```

Open your browser and navigate to:
👉 **[http://localhost:8000](http://localhost:8000)**

---

## 📡 API Reference

### `GET /`
Serves the single-page application terminal frontend.

### `GET /health`
Returns backend health status.
```json
{
  "status": "healthy"
}
```

### `GET /api/price/{coin_id}?currency=usd`
Fetches verified live price from CoinGecko.
- **Parameters**: `coin_id` (e.g. `bitcoin`, `ethereum`), `currency` (default: `usd`).

### `POST /api/chat`
Interacts with the CryptoVision AI Assistant.
- **Request Body**:
```json
{
  "message": "What is the current Bitcoin price and 24h trend?",
  "history": [
    {"role": "user", "content": "Hi"},
    {"role": "assistant", "content": "Hello! How can I help you analyze the markets today?"}
  ]
}
```
- **Response**:
```json
{
  "reply": "Bitcoin (BTC) is currently trading at $... with a 24h volume of $..."
}
```

---

## 🛡️ License

This project is open source and available under the [MIT License](LICENSE).
