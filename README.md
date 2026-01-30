
Unity Catalog is used for **data governance**, **table management**, and **volume-based storage**.

---

## 🧰 Tech Stack
- Databricks (Community / Free Edition)
- Apache Spark (PySpark)
- Delta Lake
- Unity Catalog
- Spark MLlib
- Python
- Databricks SQL Dashboards

---

## 📁 Project Structure

```text
walmart-demand-forecasting-databricks/
├── data/
│   ├── raw/
│   │   └── walmart/
│   │       ├── train.csv
│   │       ├── test.csv
│   │       ├── features.csv
│   │       └── stores.csv
├── notebooks/
│   ├── 01_bronze_ingestion.ipynb
│   ├── 02_silver_transformation.ipynb
│   ├── 03_gold_feature_engineering.ipynb
│   ├── 04_model_training.ipynb
│   ├── 05_Gold_Insights_Dashboard.ipynb
│   ├── 06_model_evaluation.ipynb
│   └── 07_business_insights_dashboard.ipynb
├── dashboards/
│   ├── Actual_Sales_vs_Predicted_Sales.png
│   ├── Holiday_vs_Non_Holiday_Sales.png
│   ├── Temperature_Impact_on_Sales.png
│   ├── Top_5_Stores_by_Sales.png
│   ├── Top_5_Stores_by_Revenue.png
│   ├── Weekly_Sales.png
│   └── Error_by_Stores.png
└── README.md

---

## 📘 Notebook Details

### 1️⃣ Bronze Layer – Data Ingestion
**Notebook:** `01_bronze_ingestion.ipynb`
- Ingests raw CSV files (sales, stores, features)
- Adds ingestion timestamp
- Stores raw data as Delta tables

**Purpose:** Preserve raw data for traceability and replayability

---

### 2️⃣ Silver Layer – Data Cleaning & Transformation
**Notebook:** `02_silver_transformation.ipynb`
- Handles missing and invalid values
- Casts columns to correct data types
- Joins datasets (sales, stores, features)
- Applies data quality checks

**Purpose:** Create a clean, analytics-ready dataset

---

### 3️⃣ Gold Layer – Feature Engineering
**Notebook:** `03_gold_feature_engineering.ipynb`
- Time-based features (year, month, week)
- Lag features and rolling averages
- Holiday indicators

**Purpose:** Prepare features for ML and analytics

---

### 4️⃣ Machine Learning – Model Training
**Notebook:** `04_model_training.ipynb`
- Feature vector creation using VectorAssembler
- Random Forest Regressor training
- Model saved to Unity Catalog volume
- Sales predictions generated

**Purpose:** Forecast weekly sales

---

### 5️⃣ Model Evaluation
**Notebook:** `06_model_evaluation.ipynb`
- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)

**Purpose:** Measure model accuracy and performance

---

### 6️⃣ Insights & Dashboards
**Notebooks:**
- `05_Gold_Insights_Dashboard.ipynb`
- `07_business_insights_dashboard.ipynb`

Visualizations include:
- Sales trends over time
- Store-wise revenue performance
- Holiday vs non-holiday sales comparison
- Actual vs predicted sales

**Purpose:** Convert analytics and ML output into business insights

---

## 📊 Key Business Insights
- Sales increase significantly during holiday weeks
- Larger stores generally generate higher revenue
- Lag and rolling average features strongly influence predictions
- Model captures seasonality and trends effectively

---

## 🎓 Learning Source & Credits
This project is inspired by and based on a **Codebasics data engineering challenge**, designed to simulate real-world analytics and ML workflows using Databricks.

Additional enhancements such as:
- Extended feature engineering
- Unity Catalog usage
- Model evaluation
- Business-focused dashboards  

were implemented to strengthen real-world applicability.

---

## ⚠️ Assumptions & Limitations
- Dataset is historical and static
- External factors like promotions are not included
- MLflow not used due to free-tier limitations
- Model performance can be improved further

---

## 🚀 Future Improvements
- Add MLflow experiment tracking
- Hyperparameter tuning
- Real-time ingestion with Auto Loader
- CI/CD pipeline integration
- External BI tool integration

---

## ✅ Conclusion
This project demonstrates a **production-style data engineering and machine learning workflow** using Databricks Lakehouse principles. It highlights strong understanding of scalable data pipelines, feature engineering, ML modeling, and business analytics.

---

**Author:** Krunal Bhoir  
**Project Type:** Databricks Lakehouse + Machine Learning  
**Platform:** Codebasics  
**Dataset:** Walmart Sales Forecasting Dataset
