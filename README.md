---
  Equity Sentiment Analysis
  
  A web application that combines real-time stock data with Twitter sentiment analysis to help investors make informed decisions.

  ---
  What It Does

  Enter a stock symbol (e.g. AAPL, TSLA, GOOGL) and the app will:
  - Fetch real-time stock price, open, high, low, and previous close
  - Scrape recent tweets about that stock
  - Run sentiment analysis on each tweet (Positive / Neutral / Negative)
  - Display aggregated sentiment scores alongside stock data

  ---
  Features

  - Real-time stock data via Finnhub API
  - Live tweet fetching via Twitter (twikit)
  - NLP sentiment analysis using RoBERTa (cardiffnlp/twitter-roberta-base-sentiment)
  - Clean web UI built with Flask
  - Sentiment breakdown per stock symbol

  ---
  Tech Stack

  ┌──────────────────┬────────────────────────────────────┐
  │    Component     │             Technology             │
  ├──────────────────┼────────────────────────────────────┤
  │ Backend          │ Flask (Python)                     │
  ├──────────────────┼────────────────────────────────────┤
  │ Sentiment Model  │ RoBERTa (HuggingFace Transformers) │
  ├──────────────────┼────────────────────────────────────┤
  │ Stock Data       │ Finnhub API                        │
  ├──────────────────┼────────────────────────────────────┤
  │ Twitter Scraping │ twikit                             │
  ├──────────────────┼────────────────────────────────────┤
  │ Frontend         │ HTML + Jinja2 Templates            │
  └──────────────────┴────────────────────────────────────┘

  ---
  How It Works

  User enters stock symbol
          ↓
  Finnhub API → real-time stock price
          ↓
  Twitter API → recent tweets about symbol
          ↓
  RoBERTa model → sentiment score per tweet
          ↓
  Aggregated results displayed on dashboard

  ---
  Setup

  Install dependencies
  pip install flask requests twikit transformers scipy

  Add your API keys
  API_KEY = 'your_finnhub_api_key'
  cookies_file_path = 'converted_cookies.json'

  Run
  python app.py

  Then open: http://localhost:5000

  ---
  Project Structure

  ├── app.py                  # Flask server + sentiment pipeline
  ├── templates/
  │   ├── index.html          # Home page
  │   └── sentiment.html      # Sentiment analysis results page
  └── converted_cookies.json  # Twitter session cookies

  ---
  API Endpoints

  ┌──────────────────────────────────┬─────────────────────────────────┐
  │             Endpoint             │           Description           │
  ├──────────────────────────────────┼─────────────────────────────────┤
  │ GET /                            │ Home page                       │
  ├──────────────────────────────────┼─────────────────────────────────┤
  │ GET /api/tweets?symbol=AAPL      │ Fetch tweets + sentiment scores │
  ├──────────────────────────────────┼─────────────────────────────────┤
  │ GET /get_stock_info?symbol=AAPL  │ Fetch real-time stock data      │
  ├──────────────────────────────────┼─────────────────────────────────┤
  │ GET /sentiment_analysis/<symbol> │ Full sentiment analysis page    │
  └──────────────────────────────────┴─────────────────────────────────┘

  ---
  License

  Private — all rights reserved.
