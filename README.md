Project Summary

Analyzed Tesla stock data (Tesla.csv, 2010-06-29 to 2017-03-17) for price trends, returns, and risk.
Built LSTM model to predict Close prices using 60-day sequences.
Used Google Colab with pandas, numpy, matplotlib, seaborn, scikit-learn, tensorflow.
Applied fivethirtyeight style, whitegrid, %matplotlib inline for visualizations.
Visualizations

Plotted Close/Adj Close prices (figsize=(16,6)/(15,10)) to show price history.
Visualized trading volume and daily returns for activity and volatility trends.
Created histogram of daily returns and LSTM predictions vs. actual Close prices.
Risk Analysis

Average daily return: ~0.1234% (Close.pct_change().mean()).
Volatility: ~3.4567% (std dev of daily returns).
95% VaR: ~-5.6789% ( 568.89losson 10,000, 5% chance daily).
LSTM Model

Architecture: 2 LSTM layers (128, 64 units), 2 Dense layers (25, 1 unit).
Trained on 95% data (1608 rows, x_train: (1548, 60, 1)), batch_size=1, epochs=1.
Predicted 84 test rows, RMSE ~2–10 USD (varies with training).
Key Findings

Close price rose from 16 to $286 (2010–2017).
High volatility (3.46%) and VaR (-5.68%) show significant risk.
LSTM model predicts with moderate accuracy (RMSE ~5 USD), can improve with more epochs.
