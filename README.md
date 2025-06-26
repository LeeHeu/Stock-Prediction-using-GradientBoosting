# Stock Price Prediction using Machine Learning

This project leverages machine learning techniques to predict stock prices of leading Vietnamese companies using historical data. It focuses on analyzing and forecasting the stock performance of companies such as **FPT**, **PNJ**, **VIC**, and **MSN**.

## 📁 Project Structure

```
├── data/
│   ├── FPT.csv
│   ├── PNJ.csv
│   ├── VIC.csv
│   └── MSN.csv
├── stockprediction.ipynb
└── README.md
```

## 📊 Data Description

The dataset includes historical stock prices with the following columns:
- `Date`: Trading date
- `Open`: Opening price
- `High`: Highest price during the day
- `Low`: Lowest price during the day
- `Close`: Closing price
- `Volume`: Trading volume

Each `.csv` file corresponds to one listed company on the Vietnamese stock market.

## 🧠 Methodology

The prediction model is built using time series and machine learning techniques. Key steps include:

1. **Data Preprocessing**
   - Handling missing values
   - Normalizing price data
   - Feature engineering (moving averages, returns, etc.)

2. **Model Training**
   - Splitting data into training and testing sets
   - Using regression models to predict future closing prices

3. **Evaluation**
   - Evaluation metrics: RMSE, MAPE
   - Visual comparison of actual vs predicted prices

## 📈 Results

The model demonstrates the ability to track stock price trends with reasonable accuracy, especially for stocks with stable long-term movement like FPT.

### 📊 2. Result Evaluation: Visual & Honest

| Ticker | RMSE   | Naïve RMSE | Δ (%)    | MAPE   | Honest Commentary                               |
|--------|--------|-------------|----------|--------|-------------------------------------------------|
| FPT    | 0.1534 | 0.1008      | -52.2%   | 0.20%  | Much worse than baseline. The model failed.     |
| MSN    | 0.0738 | 0.0806      | +8.5%    | 0.07%  | Slightly better than baseline, modest gain.     |
| PNJ    | 0.0881 | 0.0876      | -0.6%    | 0.09%  | Almost no improvement, likely just noise.       |
| VIC    | 0.0917 | 0.1118      | +17.9%   | 0.06%  | Best among the four, with relatively solid gain.|

---

### 🎯 Practical Implications

- Only **VIC** and **MSN** outperformed the baseline model.
- **FPT** performed very poorly — RMSE was 50% worse than the naïve forecast, suggesting trend misdirection or severe overfitting.
- **MAPE values** are low, indicating close absolute predictions — **but this does not guarantee trend accuracy**.

---

### ⚠️ Overall Assessment

💣 **Blunt Conclusion**:  
The **Gradient Boosting Regressor** model is **not genuinely useful** for absolute closing price prediction. In most cases, the naïve method performs even better.

---

### 🛠️ Realistic and Useful Suggestions

| Suggestion                                  | Reason                                                                 |
|---------------------------------------------|------------------------------------------------------------------------|
| Predict returns instead of absolute prices  | Less influenced by long trends; easier to learn; smaller scale.        |
| Predict direction (classification task)     | More relevant to practical use (Buy/Sell decisions).                   |
| Try XGBoost + SHAP for feature importance   | Identify and remove noisy/irrelevant features.                         |
| Use feature reduction (PCA or selection)    | Reduce multicollinearity and overfitting risk.                         |
| Tune hyperparameters                        | Default GBM settings are weak and suboptimal.                          |

---

### 📌 Summary Table

| Category              | Evaluation                                      |
|-----------------------|-------------------------------------------------|
| Code structure        | ⭐️⭐️⭐️⭐️☆                                        |
| Feature richness      | ⭐️⭐️⭐️⭐️⭐️                                        |
| Evaluation setup      | ⭐️⭐️⭐️⭐️☆                                        |
| RMSE result quality   | ⭐️⭐️☆☆☆                                        |
| Compared to Naïve     | ❌ 2 tickers did worse than baseline            |
| Real-world usability  | ⚠️ Very limited if predicting absolute prices  |

---

## 🛠️ Dependencies

To run this project, install the following Python libraries:

```bash
pip install pandas numpy matplotlib scikit-learn xgboost
```

## 💡 Future Improvements

- Incorporate news sentiment or macroeconomic indicators
- Try deep learning models (LSTM/GRU)
- Develop a web-based dashboard for live prediction updates

## 📚 References

- Historical stock data from HOSE/VNDirect
- Scikit-learn, XGBoost official documentation
- Time series forecasting and financial ML literature

## 🤝 Authors

- Project created by Vo Le Hieu
