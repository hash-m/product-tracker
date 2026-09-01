# Product Tracker
A self-hosted Discord bot that tracks product prices across multiple retailers (At the moment - eBay, B&Q, Steam), alerts users when prices drop, discounts appear or stock status changes, and maintains historical price data per product.


## Features
- Scrapes data from user-selected products across multiple retailers, via API integration and browser automation (Playwright, for JS-rendered sites)
- self configurable alerts - set triggers by availability, price threshold or percentage discount
- historical price data (all time lows, highs, mean, percentage difference from initial price) displayed with /stats command


## Commands
- `/watch <url>`: start tracking a product
- `/unwatch <url>`: stop tracking a product
- `/alert [availability/percentage/price] <url> <trigger>`: setup an alert for a tracked product
- `/alert remove <url> <target>`: remove an alert for a product, specifying which alert you want to remove
- `/list`: get a list of all products tracked
- `/get [availability/price] <url>`: receive data on a product, from its last scrape
- `/stats`: get stats on a product - showing all time lows, highs, mean and percentage change from intial price
- `/load`: *(OWNER ONLY)* load a bot module without restarting the bot
- `/unload`: *(OWNER ONLY)* remove a bot module without restarting the bot



## Setup
1. Install [Python 3.14.5](https://www.python.org/downloads/).
2. Clone this project.
  ```
  git clone https://github.com/hash-m/price-watcher.git
  ```
3. Open terminal and go to the pricewatcher's file location.
```
cd pricewatcher
```
4. Create a virtual environment and activate it.
```
python3 -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
```
5. Install and setup libraries.
```
pip install -r requirements.txt
playwright install
```
6. Sign up for developer accounts on [Discord](https://discord.com/developers/home) and [eBay](https://developer.ebay.com/signin).
7. Create a .env file and paste this inside it. Afterwards, fill these variables with the secret information from [Discord](https://discord.com/developers/home) and [eBay](https://developer.ebay.com/my/keys).
```
DISCORD_TOKEN=
EBAY_CLIENT_SECRET=
EBAY_CLIENT_ID=
```
8. You can now run the code now!
```
python3 -m bot.main  
python3 -m pytest tests # for tests
```

## Roadmap
- additional retailer support (Argos, Loaded, Amazon, Currys, etc)
- more resilient scraping solution to stay within retailers rate limit
- web interface (allows for more interactive features like a price history chart)

