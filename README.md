# Logistics Data Analyst Intern – Week 1

## Strategic Planning and Data Exploration in Logistics

**Internship:** Logistics Data Analyst Intern – YuvaIntern  
**Week:** 1  
**Project:** E-commerce Logistics Delivery Performance Analysis  
**Author:** Bhakti Dayanand Jirge

---

## 1. Project Overview

This project establishes a strategic data-analytics framework for improving last-mile delivery performance in an e-commerce logistics operation.

The project uses the **Brazilian E-Commerce Public Dataset by Olist**, a historical and anonymised dataset containing approximately 100,000 orders from 2016–2018. The dataset contains information about orders, products, sellers, customers, payments, reviews, freight values and geographic information.

The main business questions are:

- Which orders or regions are associated with delivery delays?
- How does freight cost vary across orders and operational segments?
- What relationships exist between delivery time, freight value, order value and customer review score?
- How can predictive modelling identify potentially late deliveries?
- How can clustering help identify operationally different delivery segments?
- How could routing/resource optimisation be explored in a future stage?

> **Important:** This Week 1 repository contains the planning framework and an executable Python analysis script. The historical Olist data is not included in this repository. Therefore, this project does not claim live logistics results.

---

## 2. Objectives

1. Measure delivery performance and logistics cost using clearly defined KPIs.
2. Identify geographic, product and seller-related patterns associated with delayed deliveries.
3. Explore relationships between freight value, delivery time, order value and customer satisfaction.
4. Develop a baseline approach for predicting delivery time or late-delivery probability.
5. Use clustering to segment orders/regions according to operational characteristics.
6. Investigate route/resource optimisation as a future analytical stage.
7. Translate analytical findings into practical logistics decision-support outputs.

---

## 3. Key Performance Indicators

| KPI | Definition | Target Direction |
|---|---|---|
| On-Time Delivery Rate | Orders delivered on/before estimated date ÷ delivered orders × 100 | Increase |
| Average Delivery Time | Average days from purchase to customer delivery | Decrease |
| Late-Delivery Rate | Late delivered orders ÷ delivered orders × 100 | Decrease |
| Freight Cost per Order | Total freight value ÷ number of orders | Decrease without reducing service |
| Average Review Score | Mean customer review score for delivered orders | Increase |

---

## 4. Dataset

The project is designed for the following Olist CSV files:

```text
olist_orders_dataset.csv
olist_order_items_dataset.csv
olist_customers_dataset.csv
olist_sellers_dataset.csv
olist_products_dataset.csv
olist_order_reviews_dataset.csv
olist_geolocation_dataset.csv
```

Download the dataset from Kaggle:

https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

### Data placement

After downloading and extracting the dataset, place the CSV files inside:

```text
data/
```

The dataset itself is intentionally excluded from GitHub because it is not required for the repository structure and may be large.

---

## 5. Project Structure

```text
logistics-data-analyst-week1/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   └── README.md
│
├── src/
│   └── logistics_analysis.py
│
└── outputs/
    └── README.md
```

---

## 6. Methodology

### Step 1 – Data Loading
Load the Olist orders and order-items tables using Pandas.

### Step 2 – Data Preparation
- Convert timestamp columns to datetime.
- Inspect missing values.
- Aggregate freight value at order level.
- Create derived variables.
- Keep the data preparation process reproducible.

### Step 3 – Feature Engineering

The script creates:

- `delivery_days`
- `late_flag`
- aggregated `freight_value`

The `late_flag` is based on whether the actual delivery date is later than the estimated delivery date.

### Step 4 – KPI Analysis

The Python script calculates:

- On-time delivery rate
- Average delivery days
- Average freight per order

### Step 5 – Exploratory Analysis

The planned analysis includes:

- Delivery-time distributions
- Late-delivery patterns
- Freight-cost distributions
- Regional summaries
- Product/seller patterns
- Outlier identification

### Step 6 – Predictive Modelling

Future modelling can use:

- Linear Regression for delivery-time estimation
- Logistic Regression or Random Forest for late-delivery classification

Suggested evaluation metrics:

- MAE
- RMSE
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

### Step 7 – Clustering

K-Means or another clustering method can segment orders/regions using variables such as:

- Delivery time
- Freight cost
- Order volume
- Delay rate

### Step 8 – Optimisation

A future stage can investigate Vehicle Routing Problems using Google OR-Tools, including constraints such as vehicle capacity and delivery time windows.

---

## 7. How to Run

### Install dependencies

```bash
pip install -r requirements.txt
```

### Add the dataset

Put the required Olist CSV files into:

```text
data/
```

### Run the analysis

```bash
python src/logistics_analysis.py
```

The script prints the main KPIs and creates an output CSV when the required dataset is available.

---

## 8. Example Output

The script produces values such as:

```text
Logistics Data Analysis – Week 1
--------------------------------
On-time delivery rate : XX.XX%
Average delivery days : XX.XX
Average freight/order : XX.XX
```

The actual values depend on the dataset files supplied at runtime.

---

## 9. Limitations

- The Olist dataset represents historical Brazilian e-commerce activity from 2016–2018.
- It is not live logistics data.
- Variables such as live traffic, weather, driver availability and vehicle capacity may not be directly available.
- Geographic distance may need to be approximated from postal-code coordinates.
- Predictive performance depends on data quality and the final feature set.
- Routing optimisation requires realistic operational constraints and cost assumptions before production use.

---

## 10. Expected Business Impact

The analytical framework is intended to help logistics managers:

- Monitor delivery reliability.
- Identify high-risk shipment segments.
- Investigate unusual freight costs.
- Compare operational segments.
- Support delivery-capacity planning.
- Evaluate resource-allocation strategies.
- Prepare for future route optimisation.

The project is a decision-support case study rather than a claim about a current logistics network.

---

## 11. References

1. Olist / Kaggle – Brazilian E-Commerce Public Dataset by Olist  
   https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

2. World Bank – Logistics Performance Index 2023  
   https://www.worldbank.org/en/news/press-release/2023/04/21/world-bank-releases-logistics-performance-index-2023

3. scikit-learn – Clustering User Guide  
   https://scikit-learn.org/stable/modules/clustering.html

4. Google OR-Tools – Vehicle Routing Problem  
   https://developers.google.com/optimization/routing/vrp

---

## 12. Week 1 Deliverable

This repository demonstrates the first stage of the internship project:

**Business Problem → KPI Definition → Data Preparation Plan → EDA Plan → Predictive Modelling Plan → Clustering → Optimisation Concept → Decision Support**

The next stage is to execute the data pipeline, perform exploratory data analysis, build baseline models and document measurable findings.
