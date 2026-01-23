# Customer Analytics & Churn Prediction Project

## 📌 Project Overview
This project analyzes customer behavior, sales performance, support efficiency, and churn patterns using real-world styled datasets.  
The goal is to generate actionable business insights and predict customer churn.

---

## 🎯 Business Objectives
- Understand revenue trends and top-performing regions
- Analyze customer purchasing behavior
- Evaluate customer support efficiency
- Identify churn drivers and predict churn
- Present insights through visualizations

---

## 📁 Datasets used

This project uses three datasets:

1. **Retail Transactions Dataset**
   - File size is very large, so the raw dataset is **not uploaded to GitHub**
   - Used for revenue and sales analysis
   - Source: Kaggle (Online Retail Dataset)
   - Cleaned and processed within the notebooks
    [Retail Dataset on Kaggle](https://www.kaggle.com/code/mashlyn/onlineretail-ii-simple-eda)  
   > **Note:** This file is too large to upload to GitHub. Please download and place it in `notebooks/data/` to run the notebooks.

2. **Customer Support Tickets Dataset**
   - Used for ticket volume, resolution time, and customer satisfaction analysis
     Small CSV uploaded in `notebooks/data/`  

3. **Telecom Customer Churn Dataset**
   - Used for churn prediction and customer behavior analysis
     Small CSV uploaded in `notebooks/data/`

⚠️ Note: Due to size limitations, large raw datasets are excluded. All analysis steps are reproducible using the provided notebooks.

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
- Identified churn and revenue-related questions

### Phase 2: Data Cleaning & Preparation
- Removed missing and inconsistent values
- Created derived metrics (TotalAmount, Churn_flag)
- Saved cleaned datasets

### Phase 3: SQL Analysis
- Revenue by country and month
- Top-selling products
- Ticket resolution performance
- Churn rate by contract type
- Queries saved for Power BI use

### Phase 4: Machine Learning Modeling
- Churn prediction using classification models
- Feature selection and model evaluation
- Performance comparison

### Phase 5: Data Visualization
- Revenue trends
- Product performance
- Support ticket distribution
- Churn behavior analysis

---

## 📈 Key Insights
- A small number of countries contribute the majority of revenue
- Month-to-month revenue trends show seasonality
- Customers with month-to-month contracts churn more
- Higher monthly charges are linked to churn
- Faster support resolution improves satisfaction

---

