# 📈 Vietnam Stock Trading Strategy (FA+TA+ML)

## � Tổng Quan

Chiến lược giao dịch cổ phiếu **tự động** cho thị trường Việt Nam, kết hợp:
- **📊 Fundamental Analysis (FA)**: Chỉ số tài chính doanh nghiệp
- **📈 Technical Analysis (TA)**: Xu hướng và dòng tiền
- **🤖 Machine Learning**: Random Forest dự báo giá

## 🏆 Kết Quả

| Chỉ Số | Giá Trị | Đánh Giá |
|---------|---------|----------|
| **CAGR** | 25.34% | Xuất sắc |
| **Sharpe Ratio** | 1.60 | Rất tốt |
| **Max Drawdown** | -16.71% | Kiểm soát tốt |
| **Total Return** | 82.08% | Vượt trội |

**ML Model**: ROC AUC 0.625, Accuracy 81.2% trên 842K mẫu

## ⚡ Quick Start

1. Download data file
Tải file data từ:  [fa_ta.csv](https://drive.google.com/file/d/19uTOAK1Cuj8NC-EycfdjP293dGVu_oXz/view?usp=drive_link)

```bash
# 2. Install dependencies
pip install -r requirements.txt

# 3. Run notebook
jupyter notebook stock_strategy.ipynb
```

## 🧠 Methodology

### Scoring System (0-100)
| Score | Components | Weights |
|-------|------------|---------|
| **FA Score** | Quality (ROE,ROA) + Growth (EPS,Revenue) + Value (P/E,P/B) | 40%+30%+30% |
| **TA Score** | Trend (SMA,MACD) + Flow (Volume,OBV,Foreign) | 50%+50% |
| **ML Score** | Random Forest → P(Return>5% in 10 days) | Algorithm |

### Final Score & Regime Filter
- **Bull Market**: 30% FA + 70% TA
- **Bear Market**: 70% FA + 30% TA  
- **Sideways**: 50% FA + 50% TA

### Trading Signals
- **Long Entry**: TA≥50, Price≥95% High20, ATR≤8%
- **Long Exit**: Price<SMA20, Stop loss/profit, Max 15 days
- **Short**: Opposite + stricter risk management

## 📊 Key Features

- **Feature Importance**: FA_Score (37.6%) > Price (27.3%) > ATR (21.6%) > Volume (9.7%) > TA_Score (3.9%)
- **Portfolio**: 10 Long + 6 Short positions
- **Risk Management**: Stop loss 8-10%, Take profit 15-20%, Max holding 15 days
- **Rebalancing**: Every 3 days

## 🛠️ Tech Stack

**Python 3.8+** | **Pandas** | **Scikit-learn** | **FiinQuantX** | **Jupyter**

## ⚠️ Disclaimer

- Phụ thuộc dữ liệu FiinQuant
- Chi phí giao dịch thực tế có thể khác
- Hiệu suất có thể thay đổi theo thị trường
- Chỉ mục đích nghiên cứu

