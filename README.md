# Financial Data Engineering: Social Media Sentiment & Market Data Analysis

![License](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![PRAW](https://img.shields.io/badge/PRAW-7.8+-orange.svg)
![VADER](https://img.shields.io/badge/VADER-3.3+-brightgreen.svg)

##  Project Overview

This project demonstrates a complete financial data engineering pipeline, combining traditional market data analysis with alternative data from social media. It showcases how unstructured text data (Reddit posts) can be transformed into quantifiable features for financial modeling while validating market data relationships using rigorous statistical techniques.

The project is structured into three interconnected components:

### Part 1: Market Data Analysis & Cross-Validation

* Analyzes the relationship between Open and Close prices for the iShares MSCI Chile ETF (ECH).
* Implements **5-Fold Cross-Validation** to test correlation stability.
* Demonstrates robust statistical validation techniques for financial time series.

### Part 2: Social Media Data Pipeline

* Fetches real-time Reddit data using **PRAW** (Python Reddit API Wrapper).
* Applies **VADER Sentiment Analysis** to quantify sentiment.
* Engineers key features including:

  * Compound Sentiment Score
  * Post Engagement
  * Post Velocity

### Part 3: Exploratory Data Analysis (EDA)

* Visualizes sentiment distributions and temporal trends.
* Measures post velocity as a proxy for investor attention.
* Explores the relationship between sentiment intensity and engagement.

---

#  Key Financial Data Engineering Concepts

## 1. Alternative Data Engineering

### Web Scraping & API Integration

* Uses Reddit API through PRAW to access financial discussions.
* Integrates market data from Yahoo Finance.

### Text Preprocessing

* URL removal
* Special character filtering
* Emoji and noise cleaning

### Natural Language Processing (NLP)

* VADER sentiment scoring
* Sentiment feature extraction

### Feature Engineering

Transforms raw social media text into structured numerical variables suitable for financial analysis.

---

## 2. Time Series Analysis

### Cross-Validation

* Tests stability of correlations across temporal folds.
* Reduces risk of overfitting.

### Post Velocity

* Measures discussion volume over time.
* Acts as a proxy for investor attention.

### Sentiment Trends

* Tracks sentiment changes over time.
* Potential leading indicator for market behavior.

---

## 3. Data Structure & Quality

### DataFrame Engineering

* Converts unstructured text into structured datasets.

### Data Cleaning

* Missing value handling
* Outlier treatment
* Platform-specific artifact removal

### Time Indexing

* Timestamp standardization
* Time-series resampling

---

#  Technologies & Libraries

| Category           | Libraries                           |
| ------------------ | ----------------------------------- |
| Data Acquisition   | yfinance, praw, requests            |
| Sentiment Analysis | vaderSentiment                      |
| Machine Learning   | sklearn.model_selection.KFold       |
| Visualization      | matplotlib, seaborn, plotly.express |
| Data Manipulation  | pandas, numpy                       |
| Text Processing    | re, nltk                            |
| Date & Time        | datetime, pandas                    |

---

#  Key Results & Findings

## Part 1: ECH ETF Open-Close Correlation Analysis

| Metric              | Result | Interpretation            |
| ------------------- | ------ | ------------------------- |
| Overall Correlation | 0.995  | Near-perfect relationship |
| Fold 1 Correlation  | ~0.995 | Stable                    |
| Fold 2 Correlation  | ~0.995 | Stable                    |
| Fold 3 Correlation  | ~0.995 | Stable                    |
| Fold 4 Correlation  | ~0.995 | Stable                    |
| Fold 5 Correlation  | ~0.995 | Stable                    |

### Financial Interpretation

* Open and Close prices exhibit extremely strong correlation.
* Cross-validation confirms the relationship remains stable across different periods.
* Suggests efficient pricing behavior and relatively low intraday volatility for ECH.

---

## Part 2: Social Media Sentiment Pipeline Results

| Metric            | Value         | Interpretation               |
| ----------------- | ------------- | ---------------------------- |
| API Connection    | ✅ Successful  | Connected to Reddit API      |
| Posts Fetched     | 100           | Sample from r/wallstreetbets |
| Ticker            | GME           | GameStop                     |
| Sentiment Range   | -1.0 to 1.0   | VADER compound scores        |
| Average Sentiment | 0.117         | Slightly bullish bias        |
| Engagement Range  | 1–974 Upvotes | Wide engagement variation    |

### Sample Structured Output

| Timestamp           | Ticker | Compound Score | Engagement |
| ------------------- | ------ | -------------- | ---------- |
| 2025-10-14 18:50:04 | GME    | 0.2500         | 4          |
| 2025-09-10 13:52:31 | GME    | 0.9501         | 28         |
| 2025-08-26 21:38:51 | GME    | 0.5574         | 1388       |

---

## Part 3: Exploratory Data Analysis Results

### Sentiment Distribution

* Mean Sentiment: **0.117**
* Standard Deviation: **0.418**
* Slight positive skew
* Full sentiment range from **-1.0 to 1.0**

### Post Velocity Analysis

* Volume spikes coincide with major market events.
* Activity peaks near market open and close.
* Serves as a proxy for retail investor attention.

### Sentiment-Engagement Relationship

* Highly positive and highly negative posts receive greater engagement.
* Emotional content tends to drive social media virality.
* Useful as a potential market sentiment signal.

---

#  How to Run the Project

## Prerequisites

```bash
Python 3.8+
```

## Installation

```bash
# Core libraries
pip install pandas numpy matplotlib seaborn plotly

# Financial data
pip install yfinance

# Reddit API
pip install praw

# Sentiment analysis
pip install vaderSentiment

# Text processing
pip install nltk
```

---

## Reddit API Setup

To run the social media pipeline:

1. Visit Reddit App Preferences:
   https://www.reddit.com/prefs/apps

2. Create a new application and select **Script**.

3. Obtain:

   * Client ID
   * Client Secret

4. Update your credentials:

```python
CLIENT_ID = "YOUR_CLIENT_ID"
CLIENT_SECRET = "YOUR_CLIENT_SECRET"
USER_AGENT = "your-app-name-v1"
```

---

## Usage

### Part 1: Market Data Analysis

```python
# Run the notebook cell by cell

# The code will:
# 1. Download ECH ETF data
# 2. Calculate Open-Close correlation
# 3. Perform 5-fold cross-validation
# 4. Visualize correlation stability
```

### Part 2: Social Media Data Pipeline

```python
# Run the notebook cell by cell

# The code will:
# 1. Connect to Reddit API
# 2. Fetch posts containing target ticker
# 3. Clean text data
# 4. Apply VADER sentiment analysis
# 5. Create structured DataFrame
```

### Part 3: Exploratory Data Analysis

```python
# Run the notebook cell by cell

# The code will:
# 1. Generate descriptive statistics
# 2. Create sentiment histograms
# 3. Analyze post velocity
# 4. Visualize sentiment trends
# 5. Study engagement relationships
```

---

##  Project Structure


MScFE_600_Financial_Data_GWP/
├── MScFE_600_Financial_Data_GWP_2.ipynb
├── README.md
└── requirements.txt


## Key Takeaways & Applications

## Alternative Data is Valuable

* Social media sentiment can act as a leading market signal.
* Unstructured data requires extensive engineering before becoming useful.

## Cross-Validation is Essential

* Relationships should be tested across multiple temporal samples.
* Improves robustness and reliability of findings.

## Sentiment as a Feature

* Compound sentiment scores capture overall market mood.
* Positive average sentiment indicates a bullish bias.
* Extreme sentiment often drives engagement.

## Velocity as a Signal

* Discussion volume spikes often align with market events.
* High velocity reflects increased retail investor attention.

---

# 📈 Visualizations

Generated visualizations include:

* Open-Close Correlation Across Folds
* Sentiment Distribution Histogram
* Post Velocity Chart
* Sentiment Trend Analysis
* Engagement vs Sentiment Scatter Plot

---

# 🔮 Future Improvements

## Data Expansion

* Multiple tickers (TSLA, AAPL, AMZN)
* Additional platforms (StockTwits, X/Twitter, Seeking Alpha)
* Additional sentiment features

## Predictive Modeling

* Return forecasting models
* Earnings-event studies
* Sentiment-based trading strategies

## Technical Enhancements

* Async PRAW implementation
* Real-time streaming pipeline
* SQL/NoSQL database integration
* Interactive dashboards using Plotly Dash

---

# 📝 License

This project is licensed under the MIT License.

---



Feel free to fork, star, and contribute to the project.
