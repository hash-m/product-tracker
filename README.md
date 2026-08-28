# Price Watcher
A self-hosted Discord bot that tracks product prices across multiple retailers (At the moment - eBay, B&Q, Steam), alerts users when prices drop, discounts appear or stock status changes, and maintains historical price data per product.


# Features
- scrapes data from user selected products 
- self configurable alerts (set them by availability, price or percentage changes)
- historical price data (all time lows,highs, mean, percentage difference) displayed with /stats command



# Setup
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

# Planned to be added later
