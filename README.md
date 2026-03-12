# Cryptocurrency Market Dataset using the CoinGecko API

This project collects cryptocurrency market data using the CoinGecko API and creates a cleaned dataset for analysis.

## Motivation

Cryptocurrency markets produce large amounts of publicly accessible financial data. This project demonstrates how APIs can be used to gather structured financial data for analysis.

## Question of Interest

How do price, market capitalization, trading volume, and short-term price changes vary across major cryptocurrencies?

## Data Source

The dataset was collected using the CoinGecko API:

https://www.coingecko.com/en/api

The API provides public cryptocurrency market data including prices, trading volumes, and market capitalizations.

## Data Collection

Data was collected using Python and the `requests` library.

Steps used:

1. Query the CoinGecko `/coins/markets` endpoint
2. Parse the JSON response
3. Convert the results into a pandas DataFrame
4. Select and rename relevant variables
5. Save the cleaned dataset as a CSV file

## Dataset Overview

The final dataset contains:

- **500 observations (rows)**
- **12 variables (columns)**

Variables include:

| Variable | Description |
|--------|-------------|
| coin_id | Coin identifier used by CoinGecko |
| ticker | Trading symbol |
| coin_name | Name of the cryptocurrency |
| price_usd | Current price in USD |
| market_cap_usd | Market capitalization in USD |
| market_cap_rank | Rank by market capitalization |
| volume_usd_24h | 24-hour trading volume |
| high_usd_24h | 24-hour price high |
| low_usd_24h | 24-hour price low |
| pct_change_24h | 24-hour percent price change |
| circulating_supply | Number of coins currently circulating |
| last_updated_utc | Timestamp of the last update |

## Limitations

The dataset represents a **snapshot in time**. Cryptocurrency prices and market conditions change rapidly, so the dataset may look different if collected at a later time.

## How to Run

Run the following script:

python src/collect_crypto_data.py

This will fetch the latest market data and create the dataset in `data/crypto_markets.csv`.
