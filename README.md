# 📈 Stock Price Prediction Using News Sentiment and Market Data  


## 🧠 What This Project Is About

This project explores the intersection of **machine learning**, **financial market data**, and **natural language processing** by developing predictive models for **Tesla’s stock price**, based on both **historical price data** and **news sentiment**.
Traditional stock forecasting methods rely solely on numerical data. This research goes a step further by introducing **qualitative data (news sentiment)** into the modeling process, making predictions more informed and reflective of **investor psychology**.

Visitors to this repository will find a fully developed hybrid modeling framework that combines:
- 📊 Historical market patterns  
- 🗞️ Real-world investor sentiment from 30,000+ financial news articles  
- 🤖 Machine learning and deep learning models for time-series forecasting

---

## 🎯 Goals of the Project

- Predict future stock prices of Tesla using machine learning  
- Assess and compare performance of multiple models  
- Incorporate public sentiment as a predictive signal alongside price history  
- Identify whether sentiment enhances prediction accuracy  

---

## 🧾 Data Sources

- **Tesla Stock Market Data**  
  - Downloaded directly from NASDAQ official website  
  - Covered over 2,500 trading days (~9 years)

- **Financial News Articles**  
  - Collected via **Alpaca Market News API**  
  - Included 30,000+ article headlines and summaries  
  - Sentiment scores generated using a pre-trained **DistilRoBERTa model** from HuggingFace

---

## 🧪 Methodology

The project follows a structured three-part methodology:

### 1️⃣ Market Data Analysis

- Performed **exploratory data analysis (EDA)** on Tesla’s historical prices  
- Applied **decomposition and correlation analysis** to choose relevant features  
- Built models to predict **closing prices**, using:  
  - **LSTM (with and without dropout)**  
  - **GRU**  
  - **Random Forest Regressor**

### 2️⃣ Sentiment Analysis

- Used **DistilRoBERTa fine-tuned on financial news** from **Hugging Face** to analyze article sentiment  
- Generated **daily sentiment scores**  
- Normalized and merged scores with market data  
- Handled missing summaries by falling back on headlines  

### 3️⃣ Hybrid Modeling

- Combined historical stock data with sentiment scores  
- Trained a **hybrid LSTM model** using both quantitative and qualitative features  
- Tested two sequence lengths: **5 days (weekly)** and **20 days (monthly)**  
- Evaluated models using **MSE, MAE, and MAPE**

---

## 🔁 Models and Results Overview

### 🔹 LSTM (Long Short-Term Memory)

- Trained with and without dropout layers  
- **Best standalone result (no dropout)**: MAPE = **22.79%**  
- Captured general patterns but struggled with dips  

### 🔹 GRU (Gated Recurrent Unit)

- Faster and simpler than LSTM  
- **MAPE = 4.78%**  
- Showed **lag in predictions**, limiting real-world usability  

### 🔹 Random Forest

- Traditional ML model for regression  
- **MAPE = 4.53%**  
- Fast but **overfit** the data and ignored time-series patterns  

---

## 🧬 Hybrid LSTM Model (Sentiment + Market Data)

The hybrid approach integrated both stock data and sentiment scores.

| **Sequence Length** | **MSE**   | **MAE**  | **MAPE**  |
|---------------------|-----------|----------|-----------|
| 5 Days (weekly)     | 174.47    | 9.04     | **4.31%** ✅  
| 20 Days             | 152.66    | 9.47     | 4.71%  

📌 **Best result**: Hybrid LSTM model with **5-day sequence length**, striking a balance between **temporal pattern learning** and **real-world news influence**.

---

## 📽️ Project Presentation & Report

- 📄 [**Full Dissertation Report (PDF)**](Predicting Stock price with news sentiment and market data.pdf)  
- 🧑‍🏫 [**Presentation Slides (PPTX)**](ppt dissertation.pptx)

The slides and report walk through the **problem definition**, **model-building pipeline**, **visualizations**, and the **business case for hybrid forecasting models** in finance.

---

## 🌟 Why This Matters

This project shows that **combining human sentiment with machine learning** can lead to more accurate, more intuitive stock predictions.  
It demonstrates the **real-world application of NLP** in financial analytics, and how **hybrid models** outperform traditional ones by capturing both **patterns and perception**.

Whether you're an investor, ML practitioner, or financial researcher—this project offers a **blueprint for blending data science with behavioral finance**.

