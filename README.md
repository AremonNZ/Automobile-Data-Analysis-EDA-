# 🚗 Automobile Data Analysis (EDA)

## 📌 Overview

This project explores an automobile dataset to uncover patterns in vehicle characteristics such as price, engine size, fuel efficiency, and body type.

The goal is to perform **data cleaning, exploratory data analysis (EDA), and statistical investigation** to better understand the factors influencing car attributes.

---

## 📊 Dataset

* Automobile dataset (Car Dataset.csv)
* Includes features such as:

  * Engine size
  * Fuel type
  * Body style
  * City & highway MPG
  * Curb weight

---

## 🔍 Key Steps

### 1. Data Cleaning

* Removed duplicate records
* Handled missing values
* Verified data types and structure

---

### 2. Outlier Detection

* Applied **Z-score method** to identify outliers
* Analysed numerical features such as:

  * Engine size
  * Curb weight
  * Fuel efficiency

---

### 3. Exploratory Data Analysis

* Visualised distributions using histograms and scatter plots
* Analysed relationships between variables
* Explored categorical feature patterns

---

## 📈 Key Insights

* Larger engine sizes are generally associated with higher vehicle weight and lower fuel efficiency
* Outliers exist in features like engine size and curb weight, which may affect model performance
* Certain vehicle attributes show strong relationships that could be useful for predictive modelling

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
