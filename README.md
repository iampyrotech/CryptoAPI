# Cryptocurrency Market Dataset using the CoinGecko API

This project collects cryptocurrency market data using the CoinGecko API and creates a cleaned dataset for analysis. The goal of this project is to demonstrate how publicly available APIs can be used to gather structured financial data for data science and statistical analysis.

---

## Motivation

Cryptocurrency markets generate large amounts of publicly available financial data including prices, market capitalizations, trading volumes, and price changes over time. Because cryptocurrency data is openly accessible through APIs, it provides a useful example for learning how to collect and curate data programmatically.

This project demonstrates how Python can be used to retrieve data from an API, clean the results, and construct a structured dataset that could later be used for analysis or modeling.

---

## Question of Interest

How do price, market capitalization, trading volume, and short-term price changes vary across major cryptocurrencies?

This dataset provides a snapshot of cryptocurrency market conditions and can be used to explore relationships between these financial metrics.

---

## Data Source

The dataset was collected using the **CoinGecko API**.

CoinGecko API documentation:  
https://www.coingecko.com/en/api/documentation

The API provides information about cryptocurrencies including:

- current price
- market capitalization
- trading volume
- supply
- recent price changes

For this project, data was retrieved using the `/coins/markets` endpoint, which returns market information for many cryptocurrencies in a single request.

---

## Responsible API Usage

This project uses the public CoinGecko API in a responsible manner.

The following practices were used to ensure ethical and appropriate API usage:

- Only publicly available data was accessed.
- The script makes a small number of API requests.
- A short delay between requests prevents unnecessary server load.
- No authentication credentials or private API keys are stored in this repository.

These practices follow standard guidelines for responsible API usage and web data collection.

---

## Data Collection Process

Data was collected using Python and the `requests` library.

The data collection workflow includes the following steps:

1. Send a request to the CoinGecko `/coins/markets` API endpoint
2. Receive a JSON response containing market data for many cryptocurrencies
3. Convert the JSON response into a pandas DataFrame
4. Select relevant variables from the raw API response
5. Rename columns to more readable variable names
6. Save the cleaned dataset as a CSV file

This process creates a structured dataset that can easily be used for further analysis.

---

## Data Cleaning and Transformation

The raw API response contains many variables that are not necessary for this project. Several cleaning steps were performed to produce the final dataset:

- Selected only relevant variables from the API response
- Renamed variables to more readable names
- Converted ticker symbols to uppercase
- Parsed timestamps into datetime format
- Removed duplicate records if present

These transformations resulted in a clean and consistent dataset suitable for analysis.

---

## Dataset Overview

The final dataset contains:

- **500 observations (rows)**
- **12 variables (columns)**

Each row represents a cryptocurrency and its current market statistics at the time the data was collected.

---

## Data Dictionary

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

---

## Limitations

This dataset represents a **snapshot in time**. Cryptocurrency markets are highly volatile, and prices, volumes, and rankings can change rapidly.

Additional limitations include:

- The dataset reflects the market state at the time of the API request.
- Some smaller or inactive coins may not appear depending on API filtering.
- Market data may vary slightly depending on the data sources used by CoinGecko.

Despite these limitations, the dataset provides a useful overview of cryptocurrency market conditions.

---

## Repository Contents

```
CryptoAPI
│
├── data
│   └── crypto_markets.csv
│
├── src
│   └── collect_crypto_data.py
│
├── README.md
└── requirements.txt
```

---

## How to Run the Project

1. Clone the repository:

```
git clone https://github.com/iampyrotech/CryptoAPI.git
```

2. Navigate to the project folder:

```
cd CryptoAPI
```

3. Install required packages:

```
pip install -r requirements.txt
```

4. Run the data collection script:

```
python src/collect_crypto_data.py
```

The script will fetch the latest cryptocurrency market data and save the dataset to:

```
data/crypto_markets.csv
```

---

## Potential Future Uses

This dataset could be used for many types of analysis, including:

- comparing market capitalization across cryptocurrencies
- analyzing relationships between price and trading volume
- studying short-term cryptocurrency price changes
- building models of cryptocurrency market behavior

---

## Author

Chase Nielsen 
