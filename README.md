# V4 Aziz NIFTY ATM Rolling Straddle Pine Script

This repository contains a TradingView Pine Script (v6) for **NIFTY ATM Rolling Straddle** analysis with advanced expiry, volatility, and trend features.

---

## Features

- **Dynamic Expiry Calculation**: Automatically finds the next Thursday expiry, skipping major 2025 holidays.
- **Manual Expiry Override**: Specify a custom expiry date if required.
- **Synthetic Straddle Candles**: Plots the sum of ATM call and put OHLC as synthetic candles.
- **Heikin Ashi Support**: Optionally view Heikin Ashi synthetic candles and EMAs.
- **IV (Implied Volatility) Calculation**: Computes ATM call/put IV using Black-Scholes and plots the trend/EMA.
- **Visual IV Analysis**: Z-score, standard deviation, and IV spike detection for volatility regime switching.
- **Risk Free Rate**: Uses IN10Y bond yield as the risk-free rate.
- **India VIX Overlay**: Displays India VIX for context.
- **Configurable Plots**: Toggle normal/Heikin Ashi candles, EMAs, close, and IV visuals.
- **Summary Table**: Shows IV, IV stdev, call/put IVs, and VIX in a chart overlay.

---

## How to Use

1. **Copy the Pine Script**  
   Copy the contents of `V4-Aziz-NIFTY-ATM-Rolling-Straddle.pine`.

2. **Create a New Script on TradingView**  
   - Open [TradingView](https://tradingview.com/)
   - Go to the Pine Script editor and paste the code.
   - Save and add it to your chart.

3. **Inputs & Customization**  
   - Adjust lookback, expiry, candle/EMA/IV visualizations using the indicator's settings panel.
   - Use "Show iv data" to analyze volatility regime.
   - Manual expiry input (YYMMDD) is available for backtesting or custom scenarios.

---

## Inputs Description

| Input Name        | Description                                              |
|-------------------|---------------------------------------------------------|
| Lookback          | Number of bars for calculation window                   |
| Manual Expiry     | Expiry override (YYMMDD), enable with Expiry Input      |
| EMA Lengths       | Separate EMA for indicator, normal, and Heikin Ashi     |
| Show Candles/EMA  | Toggle between price/volatility visualizations          |
| Show IV           | Plot IV trend and stats table                           |
| Risk Free Rate    | Pulls Indian 10Y bond yield, fallback to 5%             |

---

## How It Works

- **Rolling Straddle Construction**:  
  At each bar, finds ATM strike, fetches the nearest expiry NIFTY call/put OHLC, and sums for synthetic straddle candles.
- **IV Calculation**:  
  Uses Black-Scholes and a numerical solver for ATM IVs, then shows both call/put and average IV trends.
- **Expiry/Holiday Handling**:  
  Next expiry logic skips predefined 2025 holidays for realistic backtesting.

---

## Disclaimer

- The script is for **educational purposes** and may need adaptation for live trading or other years.
- Holidays are hardcoded for 2025. Update the `holidays` array for other years.
- Data feeds and instrument naming conventions must match your broker/data provider.

---

## License

MIT License. See [LICENSE](LICENSE) for details.

---

## Author

Created by [Aziz](https://github.com/noobquant1) for the Indian derivatives market.

---
