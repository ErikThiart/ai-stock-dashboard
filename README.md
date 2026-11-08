# 🚀 AI-Powered Stock Market Dashboard

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28%2B-red)](https://streamlit.io/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/erikthiart/ai-stock-dashboard)](https://github.com/erikthiart/ai-stock-dashboard)

> **A Streamlit dashboard for stock charts, technical indicators and an experimental Random Forest price forecast.**

Pick a ticker and get candlestick charts, 20+ indicators, risk metrics and a plain-English summary of what the indicators say. The price forecast is a learning exercise, not a trading signal. See [Limitations](#limitations).

![Main Dashboard](screenshots/main_dashboard.jpg)

## ✨ Features

### 🤖 **Artificial Intelligence**
- **Machine Learning Price Prediction** - Random Forest model with 30+ technical features
- **AI Market Analysis** - Natural language insights based on technical indicators
- **Feature Importance Analysis** - Understand what drives price movements
- **Model Performance Metrics** - Train/test accuracy with confidence levels

### 📈 **Advanced Technical Analysis**
- **Professional Charts** - Multi-panel candlestick charts with technical overlays
- **20+ Technical Indicators** - RSI, MACD, Bollinger Bands, Moving Averages, Stochastic
- **Volume Analysis** - Volume trends and confirmation signals
- **Performance Metrics** - Sharpe ratio, volatility, maximum drawdown

### 🎯 **Real-Time Data**
- **Market Data** - Prices from Yahoo Finance through `yfinance` (free data, can be delayed)
- **Multiple Timeframes** - 1M to 5Y analysis periods
- **Popular Stock Presets** - Quick access to FAANG+ stocks
- **Custom Symbol Input** - Analyze any publicly traded stock

### 🎨 **Professional Interface**
- **Dark Theme** - Easy on the eyes for extended analysis
- **Responsive Design** - Works perfectly on desktop and mobile
- **Interactive Charts** - Zoom, pan, and explore data
- **Organized Tabs** - Clean separation of different analysis types

![Technical Analysis](screenshots/technical_analysis.jpg)

## 🚀 Quick Start

### Prerequisites

```bash
Python 3.8 or higher
```

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/erikthiart/ai-stock-dashboard.git
cd ai-stock-dashboard
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Run the application**
```bash
streamlit run stock_dashboard.py
```

4. **Open your browser**
```
Navigate to http://localhost:8501
```

![ML Predictions](screenshots/ml_predictions.jpg)

## 📦 Dependencies

```
streamlit>=1.28.0
yfinance>=0.2.18
pandas>=1.5.0
numpy>=1.24.0
plotly>=5.15.0
scikit-learn>=1.3.0
```

## 🎮 How to Use

### 1. **Select Your Stock**
- Choose from popular presets (Apple, Tesla, Google, etc.)
- Or enter any stock symbol manually
- Select your preferred analysis timeframe

### 2. **Explore the Analysis**
- **Main Dashboard**: Key metrics and price changes
- **Technical Charts**: Advanced multi-panel analysis
- **Performance**: Risk metrics and cumulative returns
- **AI Predictions**: Machine learning price forecasts
- **Market Analysis**: AI-generated insights

### 3. **Understand the Insights**
- 🟢 **Green indicators**: Bullish signals
- 🔴 **Red indicators**: Bearish signals  
- 🟡 **Yellow indicators**: Neutral/mixed signals
- ⚠️ **Warning indicators**: Overbought/oversold conditions

![Performance Metrics](screenshots/performance_metrics.jpg)

## 🧠 Machine Learning Model

Our AI uses a **Random Forest Regressor** trained on 30+ features including:

- **Price-based features**: Returns, volatility, price changes
- **Technical indicators**: RSI, MACD, moving averages
- **Volume features**: Volume ratios and trends  
- **Lag features**: Historical price and volume data
- **Statistical features**: Rolling means and standard deviations

**Model Performance:**
- The model is retrained each time you load a ticker
- Scored on a random 80/20 train/test split (see [Limitations](#limitations))
- Feature importance analysis
- Confidence metrics displayed

![AI Analysis](screenshots/ai_analysis.jpg)

## 📊 Technical Indicators

| Indicator | Purpose | Interpretation |
|-----------|---------|----------------|
| **RSI** | Momentum | >70 Overbought, <30 Oversold |
| **MACD** | Trend | Signal line crossovers |
| **Bollinger Bands** | Volatility | Price vs. bands position |
| **Moving Averages** | Trend | Price vs. MA relationships |
| **Stochastic** | Momentum | %K and %D oscillator |
| **Volume** | Confirmation | Volume vs. average ratios |

## 🎯 Use Cases

### 📈 **For Traders**
- Quick technical analysis of any stock
- Experimental next-day price estimate (not a trading signal)
- Volume confirmation signals
- Multiple timeframe analysis

### 💼 **For Investors**
- Long-term performance metrics
- Risk assessment (volatility, drawdown)
- Company fundamental information
- Market trend analysis

### 🎓 **For Learning**
- Understanding technical indicators
- Machine learning in finance
- Market behavior patterns
- Professional chart analysis

![Company Info](screenshots/company_info.jpg)

## Limitations

Read this before trusting any forecast the dashboard shows.

- **The train/test split is random, not chronological.** `train_test_split` shuffles rows, so the model is tested on days that sit between days it trained on. For time series this leaks information and makes the accuracy figures look better than they would be on genuinely unseen future data. A walk-forward split (`shuffle=False` or `TimeSeriesSplit`) is the fix.
- **One model, one stock, one year of data by default.** There is no benchmark against a naive "tomorrow equals today" baseline.
- **No transaction costs, no backtest.** The dashboard does not simulate trading.
- **Data comes from Yahoo Finance** through an unofficial library, so it can be delayed, adjusted or briefly unavailable.

## ⚠️ Disclaimer

**This tool is for educational and informational purposes only.**

- Not financial advice or investment recommendations
- Past performance doesn't guarantee future results
- Always do your own research before investing
- Consider consulting with financial professionals
- Markets involve risk and potential loss of capital

## 🛠️ Technical Architecture

```
├── stock_dashboard.py      # Main application
├── requirements.txt        # Dependencies
├── README.md              # Documentation
└── screenshots/           # UI screenshots
    ├── main_dashboard.jpg
    ├── technical_analysis.jpg
    ├── ml_predictions.jpg
    ├── performance_metrics.jpg
    ├── ai_analysis.jpg
    └── company_info.jpg
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🌟 Acknowledgments

- **Yahoo Finance** for providing free stock data
- **Streamlit** for the amazing web framework
- **Plotly** for interactive visualizations
- **scikit-learn** for machine learning capabilities

## 📞 Support

If you find this project helpful, please give it a ⭐ on GitHub!

For questions or issues:
- Open an [Issue](https://github.com/erikthiart/ai-stock-dashboard/issues)

---

<div align="center">

**Built with ❤️ and Python**

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/erikthiart)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/erikthiart)

</div>
