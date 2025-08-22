Tesla Stock Price Prediction & Risk Analysis
This project analyzes Tesla stock data (2010–2017) from Kaggle to evaluate price trends, daily returns, and investment risk, and uses an LSTM model to predict future Close prices.
Project Summary

Analyzed Tesla stock data from Kaggle (Tesla.csv, 2010-06-29 to 2017-03-17, 1692 rows) to assess performance and risk.
Built and trained an LSTM model to predict Close prices using 60-day sequences.
Calculated risk metrics (volatility, 95% VaR) to quantify investment risk.
Visualized price trends, volume, returns, and model predictions for insights.

Dataset

Source: Tesla Stock Price (Kaggle)
Kaggle dataset: kaggle.com/datasets/rpaguirre/tesla-stock-price
Columns: Date, Open, High, Low, Close, Volume, Adj Close
Date Range: 2010-06-29 to 2017-03-17 (1692 rows)
Note: Download the dataset from Kaggle and place it in /content/sample_data/ in Google Colab.

Objectives

Quantify Tesla’s daily returns, volatility, and Value at Risk (VaR).
Predict future Close prices using a time-series LSTM model.
Visualize stock trends, trading activity, returns, and model performance.

Tech Stack

Environment: Google Colab, Python
Libraries: 
pandas, numpy: Data manipulation and analysis
matplotlib, seaborn: Visualizations
scikit-learn: Data scaling (MinMaxScaler)
tensorflow (Keras): LSTM model building and training


Styling: fivethirtyeight, whitegrid (seaborn), %matplotlib inline

Methodology

Data Loading: Imported Kaggle CSV, converted Date to datetime, set as index.
Exploratory Data Analysis (EDA):
Displayed first rows, .info() (6 columns, no missing data), .describe() (e.g., mean Close ~$90.19).
Plotted Close/Adj Close, volume, daily returns, and return distribution.


Risk Analysis:
Calculated daily returns (Close.pct_change()), average return, volatility, and 95% VaR.


Data Preparation:
Filtered Close column, scaled to [0, 1] using MinMaxScaler.
Split 95% for training (1608 rows), created 60-day sequences (x_train, y_train, shape: (1548, 60, 1)).
Prepared test data (84 rows, x_test shape: (84, 60, 1)).


LSTM Model:
Built Sequential model: 2 LSTM layers (128, 64 units), 2 Dense layers (25, 1 unit).
Compiled with Adam optimizer, mean squared error loss.
Trained on x_train, y_train (batch_size=1, epochs=1).
Generated predictions on x_test, inverse-transformed to original scale, calculated RMSE.


Evaluation: Visualized training, validation, and predicted Close prices; computed RMSE for accuracy.

Visualizations

Close Price History: Line plot of Close/Adj Close prices (2010–2017, figsize=(16,6) or (15,10)).
Trading Volume: Line plot of trading volume trends.
Daily Returns: Line plot and histogram (50 bins) of daily returns to show volatility.
LSTM Predictions: Line plot comparing training, validation, and predicted Close prices.

Key Findings

Price Growth: Tesla’s Close price increased from ~$16 to ~$286 (2010–2017).
Returns: Average daily return ~0.1234% (modest daily gains).
Risk: Volatility ~3.4567%; 95% VaR ~-5.6789% ($568.89 loss on $10,000, 5% chance daily).
Model Performance: LSTM predicted Close prices with RMSE ~2–10 USD (improvable with more epochs).

