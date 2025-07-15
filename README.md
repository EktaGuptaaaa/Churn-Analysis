# 📊 Telecom Customer Churn Analysis & Prediction

## ⭐️ Situation

This project tackles customer churn for a telecom company by building a full ETL pipeline, dashboarding in Power BI, and using Random Forest machine learning to predict future churn. While designed with telecom data, the process is fully reusable across industries like retail, finance, and healthcare—anywhere customer retention is critical.



## 🎯 Task

- **Target Audience**: Data analysts, BI developers, ML engineers, and business leaders focused on customer loyalty  
- **Objectives**:
  1. Design an ETL pipeline in SQL Server to load and clean telecom customer data
  2. Build Power BI dashboards for demographic, geographic, account, and service usage insights
  3. Profile churners and identify areas for targeted marketing campaigns
  4. Train a predictive model for future churn
  5. Monitor key metrics: Total Customers, Total Churn & Churn Rate, New Joiners

---

## 🔧 Action

### 1. ETL with SQL Server
- Created `db_Churn` database and imported raw CSV into staging table `stg_Churn`
- Performed data exploration (distinct counts, null checks), cleaned nulls, and inserted into `prod_Churn`
- Created views:
  - `vw_ChurnData` (Churned & Stayed)
  - `vw_JoinData` (Joined)

### 2. Power BI Data Modeling
- Added calculated columns:
  - `Churn Status` (binary flag)
  - `Monthly Charge Range`, `Age Group`, `Tenure Group`
- Created mapping tables and unpivoted service indicator fields

### 3. Power BI Measures & Dashboards
- Measures:
  - Total Customers, New Joiners, Total Churn, Churn Rate
- Dashboard:
  - **Summary**: KPI cards + churn breakdown by customer segments
  - **Churn Reason** page with top reasons details
  - **Churn Prediction** page to monitor predicted churners

### 4. Random Forest Model in Jupyter/Python
- Loaded Excel exports of views
- Preprocessed (label encoding), trained `RandomForestClassifier(n_estimators=100)`
- Evaluated using confusion matrix and classification report
- Saved model and generated churn predictions for new joiners

### 5. Integrating Predictions
- Imported prediction output back into Power BI or SQL
- Created visuals to highlight predicted churners by each segment

---

## 📈 Result

- **Insightful dashboard** showing churn distribution across demographics and services
- **Working Random Forest model** to flag churn risks early
- **Business-ready outputs** to support targeted retention campaigns

---

## 🛠 How to Reproduce

1. **SQL Server / SSMS**
   - Run scripts in `sql/` to create database, load data, and build views
2. **Power BI**
   - Open `.pbix`, apply transformations, and add visuals using provided measures
3. **Machine Learning**
   - Run `ml/churn_model.ipynb` in Jupyter:
     ```bash
     pip install -r ml/requirements.txt
     ```
   - Train and export `joblib` model
4. **Predictions Integration**
   - Load predicted churn data into Power BI or SQL, visualize with dashboards

---

## 🗂 Repository Structure

