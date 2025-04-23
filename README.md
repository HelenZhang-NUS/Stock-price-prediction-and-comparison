This project presents a complete workflow for stock price prediction using a combination of technical indicators and various machine learning models. The stock used for the experiment is **Ping An Insurance (601318.SH)**, with data sourced from **Tushare**.

📌 **Highlights:**

- Generation of over 15 technical indicators including MACD, EMA, ATR, CCI, OBV, ROC, and Bollinger Bands using the `ta` package.
- Data visualizations to explore trends and indicators (line chart, bar chart, MA comparison, MACD, Bollinger Bands).
- Data preprocessing: missing value removal, train-test split, log transformation, MinMax scaling.
- Supervised learning models used:
  - **Random Forest** (lowest MAE and MSE on raw data)
  - **Support Vector Machine (SVM)**
  - **CNN-LSTM** (deep learning model with temporal features)
- Dimensionality reduction using **PCA** and **Kernel PCA**, followed by re-training models.
- Model evaluation based on **MSE** and **MAE** for both original and PCA-reduced datasets.

📊 **Key Results:**

| Model         | MAE (Raw Data) | MAE (PCA) | MSE (Raw Data) | MSE (PCA) |
| ------------- | -------------- | --------- | -------------- | --------- |
| Random Forest | 0.2937         | 1.6227    | 0.3224         | 3.6923    |
| SVM           | 2.4237         | 2.2904    | 6.2998         | 5.5985    |
| CNN-LSTM      | 0.4126         | 1.3225    | 0.4515         | 2.7863    |

💡 **Conclusion:**
Random Forest performed the best on the original dataset. PCA helped SVM by reducing dimensional noise, while CNN-LSTM remained robust but more resource-intensive.

📁 **Structure:**

- `data/` – stock data and indicators
- `visualizations/` – charts and plots
- `models/` – training code for each model
- `evaluation/` – MAE/MSE comparisons

🛠️ **Technologies:**

- Python, pandas, numpy, matplotlib, scikit-learn, TensorFlow/Keras
- `ta` library for technical indicators
- RandomizedSearchCV + TimeSeriesSplit for hyperparameter tuning
