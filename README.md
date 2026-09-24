# 📊 Customer Churn Prediction System

A complete end-to-end churn prediction pipeline combining **SQL**, **Python (ML)**, and **Power BI** to identify at-risk telecom customers and visualize actionable insights.

---

## 🔍 Project Overview

Customer churn is one of the most critical problems in the telecom industry. This project builds a full-stack churn analysis system that:

1. **Ingests & cleans** raw customer data using SQL Server
2. **Trains ML models** (Logistic Regression, Random Forest, XGBoost) in Python to predict churn
3. **Visualizes** churn trends and predicted churners through an interactive Power BI dashboard

---

## 🏗️ Project Architecture

```
SQL Server  ──►  Python (ML)  ──►  Power BI Dashboard
   │                  │                   │
   │  Data cleaning   │  Model training   │  Churn summary
   │  & staging       │  & prediction     │  & forecasting
```

---

## 📁 Repository Structure

```
churn-prediction-system/
│
├── data/
│   └── Customer_Data.csv              # Raw customer dataset
│
├── notebooks/
│   └── churn_prediction_model.ipynb   # ML model training (LR, RF, XGBoost)
│
├── sql/
│   └── churn_queries.sql              # Data exploration, cleaning & views
│
├── powerbi/
│   └── ChurnAnalysis.pbix             # Power BI dashboard file
│
├── docs/
│   └── Power_Query_and_DAX.md         # Power Query steps & DAX measures
│
├── assets/
│   └── images/                        # Dashboard screenshots & icons
│       ├── Summary.PNG
│       └── Prediction.PNG
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 🧰 Tech Stack

| Layer | Tools |
|---|---|
| Data Storage | SQL Server |
| Data Processing | SQL (T-SQL) |
| Machine Learning | Python, scikit-learn, XGBoost |
| Visualization | Power BI |
| Environment | Jupyter Notebook / Anaconda |

---

## ⚙️ Setup & Usage

### 1. SQL – Data Preparation

Run the queries in `sql/churn_queries.sql` in the following order:

1. **Data Exploration** — check distinct values and null counts in `stg_Churn`
2. **Data Cleaning** — replace nulls and load clean data into `prod_Churn`
3. **Create Views** — create `vw_ChurnData` and `vw_JoinData` for Power BI

### 2. Python – ML Model Training

**Install dependencies:**

```bash
pip install -r requirements.txt
```

**Run the notebook:**

Open `notebooks/churn_prediction_model.ipynb` in Jupyter Notebook and run all cells.

The notebook covers:
- Data loading and label encoding
- Train/test split (80/20)
- Training and evaluating three models:
  - Logistic Regression
  - Random Forest (200 estimators)
  - XGBoost (300 estimators, learning rate 0.05)
- Exporting predictions for Power BI

### 3. Power BI – Dashboard

Open `powerbi/ChurnAnalysis.pbix` in Power BI Desktop.

Power Query transformations and all DAX measures are documented in `docs/Power_Query_and_DAX.md`.

---

## 📊 Dashboard Preview

**Summary Page**

![Summary Dashboard](assets/images/Summary.PNG)

**Churn Prediction Page**

![Prediction Dashboard](assets/images/Prediction.PNG)

---

## 📈 Model Results

Three classification models were trained and compared on the customer dataset:

| Model | Notes |
|---|---|
| Logistic Regression | Baseline model |
| Random Forest | 200 estimators, best interpretability |
| XGBoost | 300 estimators, highest accuracy |

---

## 📂 Dataset

The dataset (`data/Customer_Data.csv`) contains customer-level telecom data including demographics, services subscribed, billing information, and churn status.

**Key columns:** `Customer_ID`, `Gender`, `Age`, `Tenure_in_Months`, `Internet_Service`, `Contract`, `Monthly_Charge`, `Total_Revenue`, `Customer_Status`

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

---

## 📄 License

This project is for educational and portfolio purposes.
