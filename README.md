# 🚕 Ride-Sharing Demand & Revenue Intelligence

### NYC Yellow Taxi Data — January 2025

<img width="1536" height="846" alt="NYC Taxi" src="https://github.com/user-attachments/assets/0cefcacb-bd43-4e1a-a71f-3c6373ec164a" />

---

## 📌 Project Overview

This project analyzes **NYC Yellow Taxi trip data** to uncover demand patterns, revenue behavior, and simulate a dynamic surge pricing strategy.

The primary objectives were to:

* Perform large-scale data cleaning and feature engineering
* Analyze demand and revenue trends using SQL and Python
* Identify peak demand periods
* Simulate a percentile-based surge pricing model
* Estimate projected revenue uplift
* Build a regression model to predict fare amount
* Deliver business insights through an interactive Power BI dashboard

---

## 📊 Dataset

**Source:** NYC Taxi & Limousine Commission (TLC)
**Data Used:** January 2025 Yellow Taxi Trip Records

**Official dataset:**
https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

The dataset includes:

* Pickup & drop-off timestamps
* Trip distance
* Fare and total amount
* Tip amount
* Passenger count
* Pickup and drop-off location IDs

**Total records analyzed after cleaning:** ~3.4M+ trips

---

## 🧹 Data Cleaning & Feature Engineering

* Removed extreme outliers using 99th percentile filtering
* Handled missing values with median imputation where applicable
* Created `trip_duration_min` from pickup and drop-off timestamps
* Engineered new features:

  * Revenue per mile
  * Revenue per minute
  * Tip percentage
  * Weekend indicator
* Optimized data types for performance

---

## 🔍 Exploratory Data Analysis — SQL + Python

### 📈 Hourly Demand Insights

* Peak demand observed at **6 PM**
* Revenue peaks at **5 PM**
* Clear commuter-driven demand pattern

### 📅 Weekend vs Weekday Analysis

* Weekdays dominate total trip volume and revenue
* Minimal difference in average fare and tip percentage

### 🗺️ Geographic Insights

* Revenue is heavily concentrated in **Manhattan**
* Airport-related zones contribute significant per-trip revenue

---

## 🚀 Dynamic Surge Pricing Simulation

A percentile-based surge pricing strategy was implemented based on hourly demand:

| Demand Percentile    | Surge Multiplier |
| -------------------- | ---------------: |
| < 75th percentile    |             1.0x |
| 75th–90th percentile |             1.2x |
| 90th–97th percentile |             1.5x |
| > 97th percentile    |             2.0x |

### 📊 Results

**Projected Revenue Increase: 24.56%**

Revenue uplift was primarily concentrated during peak evening commute hours.

---

## 🤖 Fare Prediction Model

**Model:** Linear Regression

### Features Used

* Trip distance
* Trip duration

### Model Performance

| Metric              | Result |
| ------------------- | -----: |
| R² Score            |   0.92 |
| Mean Absolute Error |  $2.33 |

**Key finding:** Trip distance was identified as the strongest predictor of fare amount.

---

## 📊 Power BI Dashboard

A **3-page Power BI dashboard** was built to present demand, revenue, geographic, and surge-pricing insights.

### 1. NYC Taxi — Demand, Revenue & Surge Analysis

![Dashboard 1](https://github.com/user-attachments/assets/6da347ab-4c20-4b73-ad4e-7cf46407773b)

### 2. Location-Based Revenue Intelligence

![Dashboard 2](https://github.com/user-attachments/assets/d80013fc-08d1-4921-98c0-cdb123a5afa1)

### 3. Surge Pricing Impact

![Dashboard 3](https://github.com/user-attachments/assets/7b460a7a-dff8-438c-93c5-56e12a14db6e)

---

## 🛠️ Tech Stack

* **Python:** pandas, numpy, matplotlib, seaborn
* **SQL:** DuckDB
* **Machine Learning:** Scikit-learn
* **Visualization:** Power BI
* **Version Control:** Git & GitHub

---

## 📁 Project Structure

```text
Ride-Share-Demand-Intelligence/
│
├── Dashboard/
│   ├── Dashboard-1
│   ├── Dashboard-2
│   └── Dashboard-3
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda_analysis.ipynb
│   └── 03_simple_regression.ipynb
│
├── processed/
│   └── Cleaned datasets (excluded from Git)
│
├── raw/
│   └── Original datasets (excluded from Git)
│
├── insights/
│   └── EDA insights & summaries
│
├── README.md
├── requirements.txt
└── .gitignore
```

> **Note:** Large raw and processed datasets are excluded from GitHub because of their file size. Refer to the official NYC TLC dataset source above to obtain the original data.

---

## ▶️ How to Reproduce

### 1. Clone the repository

```bash
git clone https://github.com/baavikgithub/Ride-Share-Demand-Intelligence.git
cd Ride-Share-Demand-Intelligence
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebooks in order

```text
01_data_cleaning.ipynb
02_eda_analysis.ipynb
03_simple_regression.ipynb
```

### 4. Power BI

Open the processed dashboard dataset in Power BI and refresh the data model.

---

## 💡 Key Takeaway

This project demonstrates an **end-to-end data science and analytics workflow** — from raw data processing and exploratory analysis to machine learning, dynamic pricing simulation, and business intelligence.

The project combines **Python, SQL, Machine Learning, and Power BI** to transform large-scale transportation data into actionable, revenue-focused business insights.
