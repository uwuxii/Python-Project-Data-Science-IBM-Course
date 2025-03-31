# Python Project for Data Science - IBM Course

This repository contains the code and notebooks for the Python Data Science course from IBM. The project demonstrates data analysis, financial data collection, web scraping, and visualization techniques.

## Project Description

This project focuses on using Python to:
- Analyze financial data from Yahoo Finance using `yfinance`.
- Scrape data from websites using `requests` and `BeautifulSoup`.
- Process and clean data using `pandas`.
- Create interactive visualizations using `plotly`.

The project covers the following key areas:
- **Financial data analysis**: Using Yahoo Finance API (`yfinance`) to fetch historical market data.
- **Web scraping**: Collecting data from websites using `BeautifulSoup` and processing it with `pandas`.
- **Data analysis and visualization**: Cleaning and analyzing data with `pandas`, and creating interactive visualizations using `plotly`.

## Libraries Used

The following libraries are used in this project:

- `yfinance`: For fetching historical financial data from Yahoo Finance.
- `bs4` (BeautifulSoup): For web scraping to extract data from HTML documents.
- `pandas`: For data manipulation and analysis.
- `requests`: For sending HTTP requests and interacting with APIs or web pages.
- `plotly`: For creating interactive and visually appealing plots.
- `nbformat`: For working with Jupyter notebooks programmatically.

## Web Scraping Example

This project includes an example of web scraping using `requests` and `BeautifulSoup` to extract data from a webpage and process it with `pandas`.

Here is an example of scraping a table of data from a webpage:

```python
import requests
import pandas as pd
from bs4 import BeautifulSoup

# Send a GET request to the webpage
url = 'https://example.com/data-table'
response = requests.get(url)

# Parse the HTML content using BeautifulSoup
soup = BeautifulSoup(response.content, 'html.parser')

# Find the table you want to scrape
table = soup.find('table')  # You may need to adjust this based on the webpage structure

# Convert the HTML table into a pandas DataFrame
df = pd.read_html(str(table))[0]  # pd.read_html reads the HTML table into a DataFrame

# Display the first few rows of the DataFrame
print(df.head())
