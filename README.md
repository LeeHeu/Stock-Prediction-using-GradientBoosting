
# 📈 Stock Price Prediction using Deep Learning (FPT, MSN, PNJ, VIC)

## 🔍 Overview

This project focuses on predicting stock prices of **four major Vietnamese companies (FPT, MSN, PNJ, VIC)** based on historical data from **December 2018 to December 2020**.  
We employ deep learning models such as **LSTM** and **CNN-1D** to forecast future price movements and evaluate model performance.

---

## 🗃️ Dataset

- **Source:** Yahoo Finance via `yfinance` API
- **Timeframe:** 2018-12 to 2020-12 (daily granularity)
- **Companies:**
  - `FPT` (FPT Corporation)
  - `MSN` (Masan Group)
  - `PNJ` (Phu Nhuan Jewelry)
  - `VIC` (Vingroup)

Each stock dataset includes:
- `Open`, `High`, `Low`, `Close`, `Volume`
- Preprocessed using `MinMaxScaler` or `RobustScaler`

---

## 🧪 Methodology

### 📊 Data Preprocessing
- Downloaded using `yfinance`
- Missing value handling, scaling with `MinMaxScaler`
- Created sliding windows of historical prices as input

### 🤖 Model Architectures
- **LSTM (Long Short-Term Memory):**
  - Captures long-range dependencies in stock trends
- **CNN-1D:**
  - Extracts spatial patterns in time-series windows
- Combined layers with:
  - `Dropout`, `BatchNormalization`, `Dense` output
  - Early stopping and learning rate scheduling

### 🧮 Evaluation
- Train/Test split by time (no data leakage)
- Loss: `MSE`, `MAE`
- Visual comparison of predicted vs. actual stock prices

---

## 📂 Project Structure

```
├── Model.ipynb                # Main notebook
├── README.md                  # Project documentation
```

---

## 📈 Sample Results

- LSTM model was able to track overall trend in closing prices.
- CNN-1D provided faster convergence but may be less stable on noisy stocks.
- Model performance can be improved by:
  - Incorporating technical indicators (RSI, MACD)
  - Using external sentiment/news signals

---

## ⚙️ Requirements

```bash
Python >= 3.8

# Install core libraries
pip install numpy pandas matplotlib yfinance scikit-learn tensorflow
```

---

## 🚀 To Run the Notebook

```python
# Inside Model.ipynb
- Run all cells from top to bottom
- Make sure you have internet connection for yfinance to fetch data
```

---

## 👨‍💻 Author

Project by: *[Your Name or Team Name]*  
Course: Time Series Forecasting / Deep Learning / Applied Finance
