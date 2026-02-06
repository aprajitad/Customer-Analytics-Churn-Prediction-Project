# Customer Analytics & Churn Prediction Project

## 📌 Project Overview
This project analyzes customer behavior, sales performance, customer support efficiency, and churn patterns using real-world styled datasets.  
The goal is to generate **actionable business insights** and understand **factors influencing customer churn**.

---

## 🎯 Business Objectives
- Understand revenue trends and top-performing regions
- Analyze customer purchasing behavior
- Evaluate customer support efficiency
- Identify churn drivers
- Present insights using clear visualizations

---

## 📁 Datasets Used

This project uses **three datasets**:

### 1️⃣ Retail Transactions Dataset
- Used for revenue, sales trends, and product analysis
- **Large file — not uploaded to GitHub due to size limits**
- Source: Kaggle (Online Retail Dataset)

🔗 Kaggle link:  
[Online Retail Dataset](https://www.kaggle.com/code/mashlyn/onlineretail-ii-simple-eda)

> **Note:**  
> Download the dataset from Kaggle and place it inside:  
> `notebooks/data/retail_cleaned.csv`  
> to run the notebooks successfully.

---

### 2️⃣ Customer Support Tickets Dataset
- Used for ticket volume, resolution time, and customer satisfaction analysis
- Cleaned CSV is uploaded to GitHub  
- Location: `notebooks/data/`

---

### 3️⃣ Telecom Customer Churn Dataset
- Used for churn analysis and modeling
- Cleaned CSV is uploaded to GitHub  
- Location: `notebooks/data/`

⚠️ **Important:**  
Large raw datasets are excluded due to GitHub size limits.  
All analysis steps remain **fully reproducible** using the provided notebooks.

---

## 🛠 Tools & Technologies
- Python (Pandas, NumPy)
- SQL (SQLite)
- Matplotlib & Seaborn
- Scikit-learn
- Jupyter Notebook

---

## 📊 Project Phases

### Phase 1: Business Understanding
- Defined business problems and KPIs
- Identified revenue and churn-related questions

### Phase 2: Data Cleaning & Preparation
- Handled missing and inconsistent values
- Created derived metrics (e.g., `TotalAmount`, `Churn_flag`)
- Saved cleaned datasets for analysis

### Phase 3: SQL Analysis
- Revenue by country and month
- Top-selling products
- Support ticket performance
- Churn rate by contract type
- SQL outputs saved as CSV files

### Phase 4: Machine Learning Modeling
- Churn analysis using classification models
- Feature selection and evaluation
- Model performance comparison

### Phase 5: Data Visualization
- Revenue trends
- Product performance
- Support ticket distribution
- Churn behavior insights

---

## 📈 Key Insights
- A small number of countries generate the majority of revenue
- Revenue shows seasonal trends over time
- Customers on month-to-month contracts have higher churn
- Higher monthly charges are associated with churn
- Faster ticket resolution improves customer satisfaction

---

## ▶️ How to Run the Project

1️⃣ Clone the repository
```bash
git clone https://github.com/aprajitad/Customer-Analytics-Churn-Prediction-Project.git
2️⃣ Install required libraries

pip install -r requirements.txt


3️⃣ Open Jupyter Notebook
Run notebooks phase-by-phase in order

## 📂 Repository Structure

Customer-Analytics-Churn-Prediction-Project/
│
├── notebooks/
│   ├── data/
│   │   ├── support_cleaned.csv
│   │   ├── telco_cleaned.csv
│   │   └── retail_cleaned.csv (download from Kaggle)
│   │
│   ├── Phase_1_Business_Understanding.ipynb
│   ├── Phase_2_Data_Loading_and_Cleaning.ipynb
│   ├── Phase_3_SQL_Analysis.ipynb
│   ├── Phase_4_ML_Modeling.ipynb
│   └── Phase_5_Data_Visualization.ipynb
│
├── sql/
│   ├── sqlqueries_README.md
│   ├── sql_outputs/
│   │   └── *.csv
│   └── README.md
│
├── visualizations/
│   └── *.png
│
├── requirements.txt
└── README.md

👤 Author

Aprajita Dixit
Data Analyst | Business Analyst


---
