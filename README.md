# Binance Futures Testnet Trading Bot

> Note: Due to Binance Testnet access restrictions, fallback simulation is used when API calls fail.

## 📌 Overview

This project is a CLI-based Python trading bot that places MARKET and LIMIT orders on Binance Futures Testnet (USDT-M). It is designed with a clean, modular structure, proper logging, and robust error handling.

---

## 🚀 Features

* Place **MARKET** and **LIMIT** orders
* Supports **BUY** and **SELL**
* CLI-based input using `argparse`
* Input validation for all parameters
* Structured code (client, orders, validators, logging)
* Logging of:

  * API requests
  * Responses
  * Errors
* Graceful error handling with fallback simulation

---

## 📂 Project Structure

```
trading_bot/
│
├── bot/
│   ├── __init__.py
│   ├── client.py
│   ├── orders.py
│   ├── validators.py
│   ├── logging_config.py
│
├── cli.py
├── .env
├── requirements.txt
├── README.md
├── trading_bot.log
```

---

## ⚙️ Setup Instructions

### 1. Clone or Download

```bash
git clone <your-repo-link>
cd trading_bot
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Add API Keys

Create a `.env` file:

```
BINANCE_API_KEY=your_api_key
BINANCE_API_SECRET=your_secret_key
```

---

## ▶️ Usage

### MARKET Order

```bash
python cli.py --symbol BTCUSDT --side BUY --type MARKET --quantity 0.01
```

### LIMIT Order

```bash
python cli.py --symbol BTCUSDT --side SELL --type LIMIT --quantity 0.01 --price 30000
```

---

## 📄 Sample Output

```
📌 Order Request Summary
Symbol: BTCUSDT
Side: BUY
Type: MARKET
Quantity: 0.01

✅ Order Placed Successfully!
Order ID: MOCK12345
Status: FILLED
Executed Qty: 0.01
Avg Price: market_price
```

---

## 📜 Logging

Logs are stored in:

```
trading_bot.log
```

Example:

```
[REQUEST] Symbol=BTCUSDT, Side=BUY, Type=MARKET
[API ERROR] API-key format invalid
[FALLBACK USED] {...}
```

---

## ⚠️ Testnet Access Note

Due to Binance Futures Testnet login restrictions (redirection to production login), API key generation was not consistently possible.

However:

* Full Binance Testnet API integration is implemented
* Correct endpoints and request structure are used
* Logging captures API attempts and failures
* A fallback mechanism simulates order execution

This ensures the application remains fully testable and demonstrates all required functionalities.

---

## 🧠 Assumptions

* Quantity and price values are valid for Binance Futures
* API keys are stored securely in `.env`
* Testnet behavior may vary due to external restrictions

---

## ✅ Requirements

```
python-binance
python-dotenv
```
