# Vietnam Stock Trading Strategy (FA+TA+ML)

## Overview

Automated stock trading strategy for **Vietnam Stock Market**, combining:
- **Fundamental Analysis (FA)**: Company financial metrics evaluation
- **Technical Analysis (TA)**: Market trends and money flow analysis  
- **Machine Learning**: Random Forest price prediction model

## Performance Results

| Metric | Value | Assessment |
|---------|---------|----------|
| **CAGR** | 25.34% | Excellent |
| **Sharpe Ratio** | 1.60 | Very Good |
| **Max Drawdown** | -16.71% | Well Controlled |
| **Total Return** | 82.08% | Outstanding |

**ML Model**: ROC AUC 0.625, Accuracy 81.2% on 842K samples

## Quick Start

### 1. Download Data
**Required**: Download `fa_ta.csv` from [Google Drive](https://drive.google.com/file/d/19uTOAK1Cuj8NC-EycfdjP293dGVu_oXz/view?usp=drive_link)
> Place the file in project root directory

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run Analysis
```bash
jupyter notebook stock_strategy.ipynb
```

## 🧠 Methodology

### Scoring System (0-100)
| Score Type | Components | Weight Distribution |
|------------|------------|-------------------|
| **FA Score** | Quality (ROE,ROA) + Growth (EPS,Revenue) + Value (P/E,P/B) | 40% + 30% + 30% |
| **TA Score** | Trend (SMA,MACD) + Flow (Volume,OBV,Foreign) | 50% + 50% |
| **ML Score** | Random Forest → P(Return > 5% in 10 days) | Algorithm-based |

### Market Regime Filter
Adaptive scoring weights based on market conditions:
- **Bull Market**: 30% FA + 70% TA (favor momentum)
- **Bear Market**: 70% FA + 30% TA (favor fundamentals)  
- **Sideways Market**: 50% FA + 50% TA (balanced approach)

### Trading Signals
**Long Entry Conditions**:
- TA Score ≥ 50
- Price ≥ 95% of 20-day high
- ATR ≤ 8% (volatility control)

**Exit Conditions**:
- Price < SMA20 (trend break)
- Stop loss/take profit triggers
- Maximum holding period: 15 days

## Key Features

- **Feature Importance**: FA_Score (37.6%) > Close Price (27.3%) > ATR (21.6%) > Volume (9.7%) > TA_Score (3.9%)
- **Portfolio Structure**: 10 Long + 6 Short positions
- **Risk Management**: Stop loss 8-10%, Take profit 15-20%
- **Rebalancing**: Every 3 days for market adaptation

## Technology Stack

- **Python 3.8+**: Core programming language
- **Pandas & NumPy**: Data manipulation and analysis
- **Scikit-learn**: Machine learning models
- **FiinQuantX**: Vietnam market data source
- **Jupyter**: Interactive development environment

## Important Notes

- **Data Dependency**: Requires FiinQuant subscription for live data
- **Transaction Costs**: Real trading costs may differ from backtest assumptions
- **Market Sensitivity**: Performance may vary with changing market conditions
- **Research Purpose**: For educational and research purposes only

## 📄 License

MIT License - See LICENSE file for details


