# 🚗 Automobile Data Analysis (EDA)

## 📌 Overview

This project explores the UCI Automobile dataset (205 real vehicles) to uncover patterns in vehicle characteristics such as price, engine size, fuel efficiency, and body type.

The goal is to perform **data cleaning, exploratory data analysis (EDA), and statistical investigation** to better understand the factors influencing car attributes.

---

## 📊 Dataset

* UCI Automobile Dataset (`Car Dataset.csv`) — 205 vehicles after cleaning
* Includes features such as:

  * Engine size
  * Fuel type
  * Body style
  * City & highway MPG
  * Curb weight

---

## 🔍 Key Steps

### 1. Data Cleaning

* Removed 6 duplicate records (211 → 205 rows)
* Replaced `'?'` placeholders with proper missing values and imputed them (median for numeric columns, mode for categorical)
* Verified data types and structure — notably kept `num-of-doors` as categorical text rather than incorrectly coercing it to numeric

---

### 2. Outlier Detection

* Applied the **Z-score method** (threshold = 3) to identify outliers across engine size, curb weight, fuel efficiency, and price
* Flagged 11 outlier rows out of 205 and removed them for the distribution/correlation analysis

---

### 3. Exploratory Data Analysis

* Visualised distributions using histograms and scatter plots
* Analysed relationships between variables
* Explored categorical feature patterns

---

## 🐛 Debugging Note — a bug I found and fixed in my own code

My first version of the outlier-removal step looped over each numeric column to compute
Z-scores, but the removal mask was only being built from whichever column the loop
finished on last — silently ignoring outliers in every other column. I caught this by
checking the outlier counts per column against the final removed-row count and noticing
they didn't add up.

The fix: compute Z-scores for all analysis columns at once (vectorised, not looped),
then flag a row as an outlier if it's an outlier on *any* column using `.any(axis=1)`.
That way every column actually contributes to the final removal decision, not just the
last one in the loop.

---

## 📈 Key Insights

* Larger engine sizes are generally associated with higher vehicle weight and lower fuel efficiency (engine size vs. city MPG correlation: **-0.64**; vs. highway MPG: **-0.65**)
* Hardtop and convertible body styles command the highest median prices; rear-wheel-drive vehicles also trend more expensive
* Outliers in engine size and curb weight typically represent luxury or high-performance models rather than data errors
* Mean price across the cleaned dataset: **$12,225** (median: **$10,270**), range **$5,118–$35,056**

---

## ⚠️ Limitations

* Dataset may not represent the full diversity of real-world automobile data
* Outlier removal decisions can impact analysis results
* No predictive modeling was applied in this project

---

## 🚀 Future Work

* Build a regression model to predict car prices
* Perform feature engineering for improved insights
* Deploy findings into a dashboard or interactive app

---

## 🛠️ Technologies Used

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* SciPy

---

## 👤 Author

**Arman Arabkhani**
Final-year Computer Science (Data Science) student @ Auckland University of Technology
📧 armanarabkhani.nz@yahoo.com
🔗 [LinkedIn](https://www.linkedin.com/in/arman-arabkhani-95903a384/) | [GitHub](https://github.com/AremonNZ)
