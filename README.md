# 📈 Stock Trend Prediction using Random Forest (TOBA)

This repository provides an implementation of a **Random Forest Classifier** to predict the trend of TOBA stock prices based on historical data and technical indicators. It covers the full pipeline from data preprocessing, training, evaluation, and hyperparameter tuning.

---

## 📁 Project Structure

```
📦 Stock_Trend_Prediction
├── main.ipynb           # Jupyter notebook containing the full workflow
├── toba.csv             # Historical TOBA stock data enriched with technical indicators
└── README.md            # Project documentation
```

---

## 📌 Key Features

- ✅ Historical trend prediction using Random Forest
- 🔁 Data cleaning, feature engineering, and labeling
- 📊 Model evaluation using Accuracy, Precision, Recall, F1 Score, ROC AUC
- 🔍 Feature importance analysis
- 🔧 Hyperparameter tuning via RandomizedSearchCV

---

## 🗃 Dataset Overview

The dataset `toba.csv` includes:

- OHLCV Data: `Open`, `High`, `Low`, `Close`, `Adj Close`, `Volume`
- Technical Indicators: `MACD`, `RSI`, `MTM`, `ATR`, `ADOSC`, `CCI`, `MFI`, `ULTSOC`, `Donchian Channels`, `Bollinger Bands`, `OBV`, `SMA`, `TSI`, `CC`, `SO%k`, `SO%d`, `MI`, `EMV`, `+VI`, `-VI`, `CO`, `ROC`
- Target: `trend` (1 for uptrend, -1 for downtrend)

---

## 🛠 How It Works

1. **Preprocessing**
   - Drop unnecessary columns (`Open`, `High`, etc.)
   - Create `trend` column based on future price movement
   - Handle missing values and align features

2. **Model Training**
   - Split data into `train` and `test` using `train_test_split`
   - Fit a RandomForestClassifier with base parameters:
     ```python
     RandomForestClassifier(
         n_estimators=350,
         max_depth=3,
         min_samples_split=2,
         min_samples_leaf=14,
         max_features=0.5,
         random_state=70
     )
     ```

3. **Evaluation**
   - Metrics:
     - Accuracy: ~65.3%
     - Precision: ~68.5%
     - Recall: ~49.1%
     - F1 Score: ~57.2%
     - ROC AUC: ~64.4%
   - Includes confusion matrix and ROC curve visualization

4. **Feature Importance**
   - Extract top features based on importance score
   - Retrain model using only top contributing features

5. **Hyperparameter Tuning**
   - Performed with `RandomizedSearchCV` on key parameters:
     - `n_estimators`, `max_depth`, `min_samples_leaf`, `max_features`, etc.

---

## 📉 Example Output

| Metric     | Score   |
|------------|---------|
| Accuracy   | 0.653   |
| Precision  | 0.685   |
| Recall     | 0.491   |
| F1 Score   | 0.572   |
| ROC AUC    | 0.644   |

---

## 📬 Contact

**Alexander Tiopan**  
📧 alexandertiopan1212@gmail.com  
[GitHub](https://github.com/alexandertiopan1212) | [LinkedIn](https://www.linkedin.com/in/alexander-tiopan/)

---

## 📝 License

This project is licensed under the MIT License — use it freely and responsibly.

