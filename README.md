# 🏦 Banking Customer Behavior Analysis

> **Final Project — Data Science & Data Analyst Bootcamp | dibimbing.id**  
> **Author:** Iffat Ayman Ahnaf

---

## 📌 Project Overview

This project analyzes banking customer behavior using **demographic profiling** and **RFM (Recency, Frequency, Monetary) segmentation** to help a bank identify high-value customers, detect churn risks, and formulate data-driven retention strategies.

The dataset covers **1.04 million transaction records** from an Indian bank (sourced from Kaggle), spanning August–October 2016.

---

## 🎯 Business Objectives

1. **Identify customer demographic profiles** based on generation and wealth category.
2. **Segment customers** using the RFM model to classify behavioral patterns.
3. **Formulate strategic recommendations** to prevent churn, especially among high-value segments.

---

## 📂 Project Structure

```
banking-customer-behavior-analysis/
│
├── notebooks/
│   ├── 01_Preprocessing.ipynb       # Data cleaning, outlier handling, aggregation
│   └── 02_RFM_Segmentation.ipynb    # RFM scoring and customer segmentation
│
├── assets/
│   ├── dashboard_customer_profile.png
│   ├── dashboard_rfm_segmentation_analysis.png
│   └── dashboard_strategic_recommendation.png
│
├── docs/
│   └── project_presentation.pdf     # Full slide deck
│
├── requirements.txt
└── README.md
```

---

## 🗃️ Dataset

| Attribute | Detail |
|---|---|
| **Source** | [Kaggle — Bank Transaction Dataset](https://www.kaggle.com/) |
| **Raw Rows** | 1,048,567 |
| **Final Rows (after cleaning)** | 980,856 |
| **Unique Customers** | 835,914 |
| **Period** | August – September 2016 |
| **Columns** | TransactionID, CustomerID, CustomerDOB, CustGender, CustLocation, CustAccountBalance, TransactionDate, TransactionTime, TransactionAmount (INR) |

---

## 🔧 Data Preprocessing Pipeline

| Step | Description | Rows After |
|---|---|---|
| 1. Data Initialization | Fix datatypes | 1,048,567 |
| 2. Handling Missing Values | Fill with median/mode | 1,048,567 |
| 3. Handling Outliers | Remove invalid birth years (< 1929 or > 2015) | 984,259 |
| 4. Location Standardization | Normalize 1000+ city name variations → 251 cities | 984,259 |
| 5. Data Filtering | Keep Aug–Sep 2016 transactions only | 980,856 |
| 6. Final Aggregation | Aggregate per CustomerID for RFM | **835,914 customers** |

---

## 📊 Key Findings

### 👤 Customer Profile

| Metric | Value |
|---|---|
| Total Customers | 836K |
| Total Balance | ₹ 85.85 Billion |
| Average Age | 39.98 years |
| Total Transactions | 980,856 |

**Generational Balance Distribution:**
- 🟣 Millennials: ₹ 18.96bn (largest)
- 🟠 Gen X: ₹ 18.21bn
- 🔵 Boomers: ₹ 8.08bn
- 🟡 Gen Z & Alpha: ₹ 0.06bn

**Wealth Distribution Insight:**  
While the majority of customers fall in the **Standard** (163.88K) and **Mass Market** (126.72K) tiers, the largest share of total assets is concentrated in the **Affluent** (₹ 17.37bn) and **High Net Worth** (₹ 16.14bn) segments — a classic **Pareto Principle** effect.

---

### 📈 RFM Segmentation

#### RFM Scoring Rules

| Dimension | Score 1 | Score 2 | Score 3 |
|---|---|---|---|
| **Recency** | > 35 days | 18–35 days | < 18 days |
| **Frequency** | 1 transaction | — | ≥ 2 transactions |
| **Monetary** | < ₹280 | ₹280–₹1,025 | > ₹1,025 |

#### Segment Definitions

| Segment | R | F | M | Description |
|---|---|---|---|---|
| **Champions** | 3 | 2 | 3 | Most active, high-value customers |
| **Potential Loyal** | 1–3 | 1–2 | 2–3 | Ready to be upgraded to Champions |
| **High Risk** | 1 | 1–2 | 2–3 | High-value customers going dormant |
| **Active** | 2–3 | 1–2 | 1 | Regular users with low transaction value |
| **Dormant** | 1 | 1 | 1 | Inactive, low-value customers |

#### Segment Performance

| Segment | # Customers | Total Transaction Value |
|---|---|---|
| Potential Loyal | 334.36K | ₹ 758.74M |
| High Risk | 181.06K | ₹ 425.68M |
| Active | 182.49K | ₹ 21.76M |
| Champions | 41.68K | ₹ 201.13M |
| Dormant | 96.33K | ₹ 11.42M |

---

## 💡 Strategic Recommendations

### 🚨 The Priority Catch

| Priority | Target | Action |
|---|---|---|
| **Loyalty Candidate** | 66K Potential Loyal (Affluent + HNW) | Upgrade to Champions via investment product campaigns |
| **Urgent Win-Back** | 3,394 Rich/Ultra Rich in High Risk | Immediate personal outreach by Relationship Manager |
| **High Value At-Risk** | ₹ 22bn at risk | Secure assets before full dormancy |

### 📋 Strategic Action Matrix

- **Champions (VIP Focus):** Provide priority service access and exclusive product offerings to secure core asset loyalty.
- **Potential Loyal (Up-Selling):** Run tier-upgrade campaigns and insurance/investment product offerings.
- **Active (Engagement):** Boost transaction frequency via cashback programs and merchant promos.
- **High Risk (Retention):** Immediate Relationship Manager intervention to secure ₹ 22bn at risk.
- **Dormant (Re-Activation):** Send personalized re-engagement messages with incentives like admin-fee waivers.

---

## 📊 Dashboard Preview

### Customer Profile
![Customer Profile Dashboard](assets/dashboard_customer_profile.png)

### RFM Segmentation Analysis
![RFM Dashboard](assets/dashboard_rfm_segmentation_analysis.png)

### Strategic Recommendations
![Strategic Recommendations Dashboard](assets/dashboard_strategic_recommendation.png)

> 📌 Dashboards were built using **Microsoft Power BI**.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **Python** | Data processing & analysis |
| **Pandas** | Data manipulation |
| **NumPy** | Numerical computation |
| **Jupyter Notebook** | Exploratory analysis |
| **Microsoft Power BI** | Interactive dashboards |

---

## 🚀 How to Run

1. **Clone this repository**
   ```bash
   git clone https://github.com/yourusername/banking-customer-behavior-analysis.git
   cd banking-customer-behavior-analysis
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Download the dataset**  
   Get the dataset from [Kaggle](https://www.kaggle.com/) and place it in the project root directory.

4. **Run notebooks in order**
   ```bash
   jupyter notebook notebooks/01_Preprocessing.ipynb
   jupyter notebook notebooks/02_RFM_Segmentation.ipynb
   ```

---

## 📬 Contact

**Iffat Ayman Ahnaf**  
Data Analyst in Training | dibimbing.id Bootcamp Graduate  
📚 S1 Islamic Finance & Banking — Universitas Muhammadiyah Yogyakarta  
💼 Former Intern @ Bank Muamalat Indonesia & Paste Laboratory

---

*⭐ If you found this project helpful, consider giving it a star!*
