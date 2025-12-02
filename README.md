
# 🛍️ Customer Behavior Analytics – End-to-End Data Analyst Portfolio Project

**Python • SQL • Power BI • Data Cleaning • Dashboard • Business Insights**

This project demonstrates a **complete, industry-level data analytics workflow**, designed to showcase your skills as a Data Analyst. It covers **data cleaning, exploratory analysis, SQL analytics, dashboard building, and business recommendations** — exactly what hiring managers expect in a portfolio project.

---

## 🚀 Project Highlights

✔ **Clean & preprocess raw customer shopping data** using Python
✔ **Load processed data into SQL** database
✔ **Answer business questions** using advanced SQL queries
✔ **Build a Power BI dashboard** to visualize trends and insights
✔ **Write actionable business recommendations** based on findings

---

## 📁 Repository Structure

```
customer-behavior-data-analysis/
│
├── data/
│   ├── raw/                     # Original dataset
│   └── processed/               # Cleaned dataset
│
├── notebooks/
│   └── customer_behavior_analysis.ipynb
│
├── sql/
│   ├── schema.sql               # Database table structure
│   └── analysis_queries.sql     # All SQL queries for insights
│
├── powerbi/
│   └── customer_behavior_dashboard.pbix
│
├── reports/
│   ├── project_report.pdf
│   └── presentation_slides.pdf
│
├── src/
│   ├── data_cleaning.py
│   └── sql_load.py
│
├── requirements.txt
└── README.md
```

---

## 🧼 1. Data Cleaning & Preparation (Python)

### Steps performed:

* Standardized column names
* Handled missing values
* Removed duplicates
* Converted datatypes
* Created new derived features such as **Sales**, **Customer Recency**, and **RFM metrics**

### Sample Code:

```python
df.columns = df.columns.str.lower().str.replace(' ', '_')

df['order_date'] = pd.to_datetime(df['order_date'], errors='coerce')
df.drop_duplicates(inplace=True)

df['sales'] = df['quantity'] * df['unit_price']
```

Cleaned data saved to:
`data/processed/transactions_cleaned.csv`

---

## 🗄️ 2. Load Data into SQL Database

Using SQLAlchemy, the cleaned dataset is loaded into a relational database (MySQL/PostgreSQL/MS SQL Server).

```python
from sqlalchemy import create_engine
engine = create_engine('mysql+pymysql://user:password@localhost:3306/customerdb')

df.to_sql('transactions', engine, if_exists='replace', index=False)
```

---

## 🧠 3. SQL Analysis – Business Insights

### Key Questions Answered:

✔ Which customer segments generate the highest revenue?
✔ Which products have the highest profitability?
✔ What is the repeat purchase rate?
✔ What are the retention trends across cohorts?
✔ Which customers are at risk of churn?

### Sample SQL Query:

```sql
SELECT customer_id, SUM(sales) AS total_revenue
FROM transactions
GROUP BY customer_id
ORDER BY total_revenue DESC
LIMIT 10;
```

---

## 📊 4. Power BI Dashboard

The dashboard includes:

* **Revenue Trends (Daily/Monthly)**
* **Top Customers & Product Categories**
* **RFM Segmentation Visualization**
* **Customer Churn Indicators**
* **Cohort Retention View**

> File located at: `powerbi/customer_behavior_dashboard.pbix`

---

## 📝 5. Key Insights & Recommendations

**Findings:**

* Top 10% customers contribute a major portion of total revenue
* Repeat purchase rate is moderate → potential for retention programs
* Significant drop in retention after Month 2
* Category X is the highest selling, but Category Y has the highest AOV

**Recommendations:**

* Launch targeted email campaigns for churn-risk customers
* Introduce loyalty rewards for high-value customers
* Bundle complementary products to increase average order value
* Focus marketing on high-performing categories

---

## 🛠️ Tech Stack

**Python (Pandas, NumPy)**
**SQL (MySQL/PostgreSQL)**
**Power BI**
**Jupyter Notebook**
**SQLAlchemy**

---

## 📄 License

MIT License — free to use and modify for learning & portfolio.

---

## 👩‍💻 Author

**Diksha Singh**
Aspiring Data Analyst | Python • SQL • Power BI
📧 Email: itsdsr98@gmail.com
🔗 LinkedIn: www.linkedin.com/in/diksha-singh-521270271

