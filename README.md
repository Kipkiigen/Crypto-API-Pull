---

# Cryptocurrency Data Fetcher and Analyzer

## Overview
This project retrieves the latest cryptocurrency data from the **CoinMarketCap API**, processes the data, stores it in a CSV file, and performs basic analysis and visualization. The data includes information such as cryptocurrency prices, percent changes over various time intervals (1h, 24h, 7d, 30d, 60d, 90d), and timestamps of when the data was fetched.

The goal of this project is to create an automated pipeline that continuously collects and stores cryptocurrency data, which can later be analyzed for trends, correlations, and insights.

## Features
- **Data Collection**: Fetches real-time cryptocurrency data from CoinMarketCap via their API.
- **Data Storage**: Stores the fetched data into a CSV file, appending new data on each request.
- **Data Analysis**: Performs basic statistical analysis on the percentage price changes over different time periods.
- **Data Visualization**: Uses Seaborn and Matplotlib for visualizing cryptocurrency trends and price changes.
- **Automation**: Repeatedly fetches and stores new data every minute for up to 333 iterations (or more, if needed).

## Installation

### Prerequisites
To run this project, ensure that you have the following dependencies installed:

- Python 3.x
- `requests` library
- `pandas` library
- `matplotlib` library
- `seaborn` library

You can install the required libraries using `pip`:

```bash
pip install requests pandas matplotlib seaborn
```

### API Key
You will need a **CoinMarketCap API key** to access their data. You can obtain one by signing up at [CoinMarketCap](https://coinmarketcap.com/api/) and creating an API key. Replace the placeholder in the script (`'API-KEY'`) with your own API key.

### File Paths
Make sure the path where the CSV file will be saved exists or adjust the file path in the script. The default path is:

```
C:\Users\Leon\Documents\Data Analyst Projects\API Pull Results\API.csv
```

You can modify it as needed, especially if you are using a different operating system.

## Usage

### Running the Script
The script automatically fetches cryptocurrency data every minute for 333 iterations. To run the script:

1. Ensure you have set your CoinMarketCap API key and have installed all the necessary dependencies.
2. Run the script using Python:

```bash
python cryptocurrency_data_fetcher.py
```

### Data Collection
The script will:
- Fetch the latest cryptocurrency data (top 15 cryptocurrencies).
- Store the data in a CSV file (`API.csv`).
- Add a timestamp to each row of data to indicate when it was collected.
- Append new data to the file for each iteration.

### Data Analysis
The script performs some basic analysis, including:
- Grouping the data by cryptocurrency name and calculating the average percentage change over different time periods.
- Creating a stacked series and a cleaned DataFrame for further analysis.

### Data Visualization
- **Point Plot**: Visualizes the percentage changes over 1h, 24h, 7d, etc., for each cryptocurrency.
- **Line Plot**: Shows the price trend for Bitcoin over time.

### Storing and Accessing Data
The data is saved in a CSV file. Each row contains the following columns:
- `name`: The cryptocurrency's name (e.g., Bitcoin, Ethereum).
- `quote.USD.price`: The price of the cryptocurrency in USD.
- `timestamp`: The time when the data was fetched.
- `quote.USD.percent_change_*`: The percentage change in the cryptocurrency's price for various time periods (1h, 24h, 7d, etc.).

You can load the CSV file in any tool (e.g., Excel, pandas) for further analysis.

## Example Visualization
After the script runs for some time, you will be able to generate plots like the following:

- **Point plot** showing the percent change over different periods for each cryptocurrency.
- **Line plot** showing the price trend of Bitcoin over time.

## Notes
- The script uses a `for` loop to run 333 iterations (approximately 5.5 hours) with a delay of 60 seconds between each iteration.
- You can adjust the number of iterations or time delay by modifying the `for` loop in the script.
- Ensure your API key is kept secure. It is recommended to store it in an environment variable or external configuration file instead of hardcoding it in the script.
- The script is designed to run on Windows, but it can easily be adapted for use on other operating systems.

## Troubleshooting
If the script encounters connection errors or timeouts, it will print an error message. Ensure that your internet connection is stable and that the CoinMarketCap API is not experiencing downtime.

### Common Issues:
1. **API Key Invalid**: Ensure the API key is correct and has the necessary permissions.
2. **File Path Errors**: Ensure the file path for saving the CSV file exists.
3. **Module Not Found**: Ensure all dependencies are installed via `pip install`.

## License
This project is open-source. Feel free to contribute or modify it as you wish. However, please ensure that you are complying with CoinMarketCap's API usage terms.

---
