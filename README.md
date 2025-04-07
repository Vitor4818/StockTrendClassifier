# 📈 Stock Trend Classifier

This project presents an end-to-end analysis and classification of stock behavior using historical data from the **S&P 500 index**. The main goal was to **identify patterns and understand the variables that most influence asset returns**, through a structured data science workflow — from data cleaning to predictive modeling.

---

## 🧠 Project Summary

The study was conducted using historical data from the S&P 500, with the goal of identifying the key factors that impact stock returns. To achieve this, I explored a complete pipeline:

- 📥 Exploratory Data Analysis  
- 🧼 Data Cleaning  
- 🔧 Feature Engineering  
- 📊 Visual Analysis  
- 🌀 Clustering  
- 🤖 Predictive Modeling  

---

## ⚙️ Technical Workflow

### 📉 Missing Data Treatment

Linear interpolation was applied to price-related columns, ensuring continuity in the time series and avoiding the loss of important patterns that could affect the model's performance.

---

### 🛠️ Feature Engineering

To enrich the dataset and bring depth to the analysis, I created new features, including:

- Daily **volatility** (High - Low)
- Daily **return %** (Close / Open - 1)
- **Moving averages** (SMA and EMA)
- **Standard deviation**, **RSI**, and **log-transformed volume**
- **Price distance** from moving averages
- **Temporal features**: year, month, day of week
- **Target**: next day's return (positive or negative)

---

### 📊 Visual Analysis & Insights

Using scatter plots, histograms, boxplots, and heatmaps, I analyzed the relationship between the features and future return behavior.

#### Key Insights:

- Stocks with **low prices** and **high volatility** tend to show **extreme returns**, both positive and negative.
- **Cheap and stable** stocks showed **more consistent returns**, being potential short-term opportunities.
- **Expensive and stable** assets had lower, yet more **predictable returns**.

These findings helped define the clustering logic for grouping stocks by **risk-return profiles**.

---

### 🌀 Clustering with K-Means

K-Means clustering was applied using **price** and **volatility** as the main axes, resulting in **3 distinct groups**:

- **Cluster 0**: Low price + High volatility → Extreme returns
- **Cluster 1**: Low price + Low volatility → Consistent returns
- **Cluster 2**: High price + Low volatility → Stable returns

This segmentation was crucial to understanding which asset profiles tend to stand out in the short term.

---

### 🤖 Predictive Modeling with Random Forest

A classification model was built using **RandomForestClassifier** to predict whether the stock return on the next day would be positive or negative.

- **Accuracy:** 66%  
- Despite market complexity, the model captured patterns that allowed for reasonable predictions of short-term movement.

---
## 🔍 Technologies Used

- Python 3
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook

