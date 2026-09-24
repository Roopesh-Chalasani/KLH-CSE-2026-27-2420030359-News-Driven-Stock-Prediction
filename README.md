# AI-Based Financial News Sentiment Analysis for Stock Market Prediction

## 📌 Project Overview

This project presents an AI-based approach for predicting stock market direction using financial news sentiment and market-related features.

The proposed framework, **FinSent-Momentum Fusion (FSMF)**, combines financial-news sentiment obtained using **FinBERT** with engineered momentum, volatility, technical-indicator, volume, and interaction features. These features are then provided to a **Gradient Boosting Classifier** to predict the stock's market direction.

The project uses the **TRACE AAPL dataset** for Apple (AAPL).

---

## 🎯 Objectives

- Analyze financial news using a financial-domain language model.
- Extract positive, negative, and neutral sentiment information.
- Combine news sentiment with historical market information.
- Engineer momentum, volatility, technical, volume, and interaction features.
- Predict stock market direction (UP/DOWN).
- Compare the proposed FSMF model with baseline and literature-based approaches.

---

## 🧠 Proposed FSMF Model

The complete pipeline is:
Financial News / Tweets
          ↓
       FinBERT
          ↓
Positive / Negative / Neutral Scores
          ↓
   Feature Engineering
          ↓
35 Engineered Features
          ↓
 Gradient Boosting Classifier
          ↓
      UP / DOWN

FinBERT
The project uses:
ProsusAI/finbert

FinBERT converts financial text into sentiment scores:
- Positive
- Negative
- Neutral
FSMF Features
The proposed feature set contains 35 engineered features, including:
- Sentiment score
- Sentiment pressure
- Sentiment changes
- Sentiment momentum
- Sentiment acceleration
- Sentiment volatility
- Tweet-count features
- Historical returns
- Momentum features
- Volatility
- RSI
- MACD
- Bollinger Bands
- Volume features
- Sentiment × momentum
- Sentiment × volatility
- Sentiment × volume
📊 Dataset
The project uses the TRACE AAPL dataset.
The dataset contains:
- AAPL market information
- Daily financial/social text
- Daily target labels
- Historical stock-related features
The official prediction target used in the project is:
Target1d

The target represents the stock-direction classification used by the TRACE dataset.
🤖 Machine Learning Model
The proposed classifier is:
GradientBoostingClassifier

Configuration used:
GradientBoostingClassifier(    n_estimators=150,    learning_rate=0.05,    max_depth=2,    random_state=42)


📈 Results
The current FSMF model achieved:
Metric	Test Result
Accuracy	69.12%
Precision	61.90%
Recall	83.87%
F1-Score	71.23%


The results are obtained on the held-out chronological test period of the TRACE AAPL dataset.
🔬 Literature Comparison
The project also studies previous approaches including:
- Tetlock (2007) – Media Sentiment Analysis
- Schumaker & Chen (2009) – AZFinText
- Bollen et al. (2011) – Twitter Mood Analysis
- Ding et al. (2015) – NTT + CNN
- Moore & Rayson (2017) – SVR + BLSTM
- Xu & Cohen (2018) – StockNet
- Araci (2019) – FinBERT
- Li et al. (2020) – LSTM + Technical Indicators
- Hybrid sentiment and technical-feature approaches
- FSMF – Proposed Model
Literature results reported in the original papers are not directly treated as equivalent to results obtained on the TRACE AAPL dataset because the datasets, targets, and experimental settings can differ.
🛠️ Technologies Used
- Python
- Pandas
- NumPy
- Scikit-learn
- PyTorch
- Transformers
- FinBERT
- Streamlit
- Matplotlib
📁 Project Structure
NewsDrivenStockPrediction/
│
├── data/
│   ├── TRACE_ACL18_joint_prediction_model_set/
│   ├── AAPL_daily_sentiment.csv
│   ├── AAPL_model_dataset.csv
│   ├── AAPL_features.csv
│   └── AAPL_FSMF_features.csv
│
├── models/
│   ├── logistic_regression_model.pkl
│   └── fsmf_model.pkl
│
├── src/
│   ├── app.py
│   ├── preprocessing.py
│   ├── sentiment_analysis.py
│   ├── stock_data.py
│   ├── feature_engineering.py
│   ├── proposed_features.py
│   ├── train_model.py
│   ├── evaluate_model.py
│   ├── build_sentiment_features.py
│   ├── build_model_dataset.py
│   └── train_fsmf_model.py
│
└── README.md

▶️ How to Run the Project
1. Clone the repository
git clone YOUR_GITHUB_REPOSITORY_URL

2. Open the project
cd NewsDrivenStockPrediction

3. Create/activate the virtual environment
Windows PowerShell:
.\venv\Scripts\Activate.ps1

4. Install dependencies
pip install -r requirements.txt

5. Run the Streamlit application
streamlit run src/app.py

The application will open at:
http://localhost:8501

🧪 Example Input
You can test the application using:
Apple reports strong quarterly earnings, record revenue growth, and increased investor confidence in its future performance.

The application processes the text using FinBERT and then uses the FSMF model to generate a stock-direction prediction.
👥 Project Team
Team Number: 11
Section: 7
Cluster: 3
Team Members
- Roopesh – 2420030359
- Deepthi Anusha – 2420030448
- Vyshnavi – 2420030449
Supervisor
Dr. K. SWANTHANA
⚠️ Disclaimer
This project is developed for academic and research purposes. The predictions generated by the system should not be considered financial advice or a recommendation to buy or sell any security.
📜 License
This project is intended for academic and educational use.

### One important thing before pushing to GitHub

**Do not upload your `venv` folder or large model/cache files unnecessarily.** Add a `.gitignore` containing:

```gitignore
venv/
__pycache__/
*.pyc
.ipynb_checkpoints/
.streamlit/secrets.toml
.env
