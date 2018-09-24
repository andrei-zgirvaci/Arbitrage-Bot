
# Crypto Market - Arbitrage Bot (Arbitrage-Bot)

Cryptocurrency is still a new and inefficient market. Several Cryptocurrency exchanges exist around the world and the bid/ask prices they propose can be briefly different from an exchange to another. The purpose of Arbitrage-Bot is to automatically profit from these temporary price differences while being market-neutral.

Arbitrage-Bot uses the most popular open-source trading library [ccxt](https://github.com/ccxt/ccxt) in order to find best price spread on the market.

WRITTEN BY: Andrei Zgirvaci

CONTRIBUTE: Contributions are always welcome!

*If you can, please take a minute to star this repo and follow me, It will be much appreciated!!!*

---

## Requirements

* **python** version **3.7.0** installed

## Installation

```bash
git clone https://github.com/MD3XTER/Arbitrage-Bot.git

cd Arbitrage-Bot

pip install ccxt

python3 arbitrage_bot.py
```

## Usage

First, you need to specify the markets you are going to target. Here is a [list](https://github.com/ccxt/ccxt#supported-cryptocurrency-exchange-markets) of supported markets by the [ccxt](https://github.com/ccxt/ccxt/wiki) library:

```python
exchanges = [
    "binance",
    "bittrex",
    "hitbtc",
    "poloniex",
    "exmo",
    "bitmex",
    "huobi",
]
```

In order for the bot to be able to fetch market data, it needs an **API Key** and a **Secret Token** for each market you are going to target:

```python
exchangesData = {
    "hitbtc": {
        "apiKey": "",
        "secret": "",
        "transactionFee": 0.001
    },
    "binance": {
        "apiKey": "",
        "secret": "",
        "transactionFee": 0.001
    },
    "bittrex": {
        "apiKey": "",
        "secret": "",
        "transactionFee": 0.0025
    },
    "poloniex": {
        "apiKey": "",
        "secret": "",
        "transactionFee": 0.0025
    },
    "exmo": {
        "apiKey": "",
        "secret": "",
        "transactionFee": 0.002
    },
}
```

Secondly, you need to specify for which symbols should the bot look, here is a list of the most common ones:

```python
symbols = [
    "ETH/USDT",
    "XRP/USDT",
    "BTC/USDT",
    "BCH/USDT",
    "DASH/USDT",
    "XMR/USDT",
    "LTC/USDT",
]
```

You can also specify min spread and min profit that you are interested in:

```python
min_spread = 1
min_profit = 0
```

---

Take in mind that there are two ways to create buy orders: [create_market_buy_order](https://github.com/ccxt/ccxt/wiki/Manual#market-orders) and [create_limit_buy_order](https://github.com/ccxt/ccxt/wiki/Manual#limit-orders). You should decide for yourself what method fits you better.

For more information on how each method works, take a look at the official [ccxt](https://github.com/ccxt/ccxt/wiki) documentation.