# Shopee Scraper

A Python-based scraper for Shopee.

## Overview
This project automates the following steps:
- Login with your Shopee credentials
- Search for a specific keyword
- Extract product details (name, price, variants, stock, category, seller info, ratings, etc.)
- Logout to end the session cleanly

## Getting Started

### Clone the Repository
```sh
git clone https://github.com/bohyanggg/scraper.git
cd shopee-scraper
```

### Install Dependencies
```sh
pip install -r requirements.txt
```
Ensure you have Python 3.7+ and a supported WebDriver environment.

### Setup
Make a copy of the env file and rename it as `.env`. Fill in your credentials:
```env
SHOPEE_USERNAME=your_username
SHOPEE_PASSWORD=your_password
APP_SECRET_KEY=optional-random-string
```

## Web App
A minimal local web UI is provided in `webapp/` to make scraping easier for non-technical users.

### Run
```sh
python webapp/app.py
```
Then open http://127.0.0.1:5000/ in your browser.

Enter a keyword, the number of pages, and items per page, then click "Start Scraping". The app will:
- Use credentials from `.env`
- Run the existing `ShopeeScraper`
- Save results as JSON files under `downloaded_files/`
- Show a human-readable results page with a download link

This web app is intended for local use only as a proof of concept.

## Notes
### CAPTCHA Handling
Shopee may occasionally require manual CAPTCHA solving. When this occurs, you may need to solve it for the scraper to continue.

### Rate Limits & Anti-Bot Measures
Use the scraper responsibly to avoid IP blocking or violations of Shopee's terms of service.

## For Command Line based use
### Configure Your Credentials & Parameters
This project accepts parameters via the command-line.

#### Required Parameters:
- `--username`: Your Shopee username.
- `--password`: Your Shopee password.
- `--keyword`: The search keyword.

#### Optional Parameters:
- `--numpage`: The number of pages to scrape.
- `--itemperpage`: The number of items per page to scrape.

#### Example Command:
```sh
python main.py --username your_username --password your_password --keyword "iphone" --numpage 2 --itemperpage 5
```

A browser window should open, navigate to Shopee, log in with your credentials, perform the search, scrape the product data, and then log out.

### Review Output
By default, the scraper prints the resulting JSON output to the downloaded_files folder

