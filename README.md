# Freqtrade Docker Example

Example of Freqtrade docker container that can use all strategies.

## Whait is Freqtrade
Freqtrade is a free and open source crypto trading bot written in Python. It is designed to support all major exchanges and be controlled via Telegram. It contains backtesting, plotting and money management tools as well as strategy optimization by machine learning. [more info...](https://github.com/freqtrade/freqtrade/blob/develop/README.md)

### Quick Start

#### Install
```bash
git clone https://github.com/serhankilicarslan/freqtrade-bot
cd freqtrade-bot

docker-compose run --rm freqtrade create-userdir --userdir user_data
docker-compose run --rm freqtrade new-config --config user_data/my-config.json
```

#### Edit Config File

You should edit the `user_data/my-config.json` file.
Browse to the `user_data/example-config.json` file.


#### Download Data
Download data command example.
```bash
docker-compose run --rm freqtrade download-data --userdir user_data --pairs SOL/USDT ETH/USDT BTC/USDT BTCST/USDT STMX/USDT AUTO/USDT --exchange binance --days 5 -t 5m
```

#### Backtest
Backtest command example.
```bash
docker-compose run --rm freqtrade backtesting --userdir user_data  --config user_data/my-config.json --strategy Strategy001
docker-compose run --rm freqtrade backtesting --userdir user_data  --config user_data/my-config.json --strategy Strategy002
docker-compose run --rm freqtrade backtesting --userdir user_data  --config user_data/my-config.json --strategy Strategy003
docker-compose run --rm freqtrade backtesting --userdir user_data --config user_data/my-config.json --strategy Zeus
docker-compose run --rm freqtrade backtesting --userdir user_data --config user_data/my-config.json --strategy wtc
```

#### Run
```bash
docker-compose up
```
**For deamon**
```bash
docker-compose up -d
```

	
