# ◈ CryptoVision
<img width="1600" height="895" alt="image" src="https://github.com/user-attachments/assets/d1b08606-4be6-45e5-ad73-8c914d891270" />
<img width="1600" height="804" alt="image" src="https://github.com/user-attachments/assets/30eeedeb-e291-48e3-94b0-5ffa39bd77e6" />
<img width="228" height="73" alt="image" src="https://github.com/user-attachments/assets/ff8b31c7-fca0-41f8-9233-5a1712bc3cd9" />
<img width="1600" height="857" alt="image" src="https://github.com/user-attachments/assets/7b9a25c3-00f3-4fa2-b7e6-9b4ae60ec18e" />
<img width="1600" height="807" alt="image" src="https://github.com/user-attachments/assets/4d5b4795-8efd-45e4-8b0c-413143d4fa41" />
<img width="1600" height="807" alt="image" src="https://github.com/user-attachments/assets/70845de9-9d87-4762-b3e0-6baaad5a4802" />
<img width="1600" height="805" alt="image" src="https://github.com/user-attachments/assets/0359c18d-0ea1-43b8-9dc5-e53e229328e9" />

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
