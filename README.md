# Customer_behavior_analysis
End-to-end customer shopping behavior analysis using Python, SQL, and Power BI to explore purchasing patterns, analyze customer data, and generate actionable business insights through an interactive dashboard.

# Customer Shopping Behavior Analysis

**An end-to-end data analytics project using Python, MySQL, and Power BI**

![Python](https://img.shields.io/badge/Python-Data%20Preparation-blue?logo=python&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-SQL%20Analysis-4479A1?logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)

## 1. Overview

This project explores customer shopping behavior to identify patterns in spending, product preferences, discounts, shipping choices, customer segments, and subscription status. It follows a practical analytics workflow: **prepare and clean the data in Python, answer business questions with SQL in MySQL, and communicate the findings through an interactive Power BI dashboard**.

The goal is to turn transaction-level data into useful insights and recommendations that can support marketing, customer retention, and product decisions.

## 2. Dataset

The dataset contains **3,900 purchase records and 18 columns** before cleaning.

It includes information about:

- **Customer profile:** age, gender, location, and subscription status
- **Purchase details:** item, category, purchase amount, season, size, and color
- **Shopping behavior:** discount use, previous purchases, and purchase frequency
- **Customer experience and fulfillment:** review rating and shipping type

**Data quality issue:** 37 values were missing from the `Review Rating` column.

> Place the source CSV in your repository's `data/` folder, subject to the dataset's applicable usage and sharing terms. Update the file path in the notebook to match its actual filename.

## 3. Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data preparation, cleaning, exploratory data analysis, and feature engineering |
| Pandas | Loading, inspecting, transforming, and preparing the dataset |
| MySQL | Storing the cleaned data and running business-focused SQL queries |
| Power BI | Creating KPI cards, comparisons, and interactive dashboard filters |
| Jupyter Notebook | Documenting and running the Python workflow |
| PowerPoint | Presenting the project workflow, findings, and recommendations |

## 4. Project Workflow

### Step 1 — Load and explore the data with Python

- Loaded the dataset using Pandas.
- Inspected the structure, column types, and summary statistics using methods such as `df.info()` and `df.describe()`.
- Reviewed missing values and checked the data before analysis.

### Step 2 — Clean and prepare the data

- Filled the 37 missing review ratings using the **median rating for the corresponding product category**.
- Standardized column names to `snake_case` for consistent use in Python and SQL.
- Created an `age_group` feature from customer ages.
- Created a `purchase_frequency_days` feature from purchase-frequency information.
- Checked whether `discount_applied` and `promo_code_used` were redundant and removed `promo_code_used` from the cleaned dataset.

### Step 3 — Load the cleaned data into MySQL

Connected Python to MySQL and loaded the prepared DataFrame into a database table for SQL-based analysis.

### Step 4 — Answer business questions with SQL

The MySQL queries examined ten business questions:

1. How does total revenue compare by gender?
2. Which customers used discounts but spent more than the average purchase amount?
3. Which five products have the highest average review ratings?
4. How do average purchase amounts compare between Express and Standard shipping?
5. How do subscriber and non-subscriber groups compare in customer count, average spend, and revenue?
6. Which products have the highest proportion of discounted purchases?
7. How many customers fall into New, Returning, and Loyal segments?
8. Which products are purchased most often within each category?
9. What is the subscription status of customers with more than five purchases?
10. Which age groups contribute the most revenue?

### Step 5 — Build the Power BI dashboard

Created an interactive dashboard to present key performance indicators and comparisons. The dashboard includes headline metrics, subscription mix, revenue comparisons, and category and age-group views. Filters cover **subscription status, gender, product category, and shipping type**.

### Step 6 — Communicate the findings

Summarized the workflow, findings, and business recommendations in a project report and presentation.

## 5. Dashboard Highlights

The Power BI dashboard brings the analysis together with key metrics and interactive filtering.

| KPI | Reported value |
|---|---:|
| Purchase records | 3,900 |
| Average purchase amount | $59.76 |
| Average review rating | 3.75 |
| Subscribers | 27% |
| Non-subscribers | 73% |

*Values reflect the dataset and dashboard used in this project.*

## 6. Key Results

- **Revenue by gender:** Male customers generated $157,890 in total revenue, compared with $75,191 from female customers. Total revenue alone does not indicate which group has higher per-customer value.
- **Shipping comparison:** The average purchase amount was $60.48 for Express shipping and $58.46 for Standard shipping, a difference of $2.02.
- **Product ratings:** Gloves had the highest average review rating among the five products reported, at 3.86.
- **Discount rate:** Hat had the highest reported discounted-purchase rate, at 50.00%.
- **Customer segments:** The analysis classified 3,116 customers as Loyal, 701 as Returning, and 83 as New.
- **Subscriptions:** There were 1,053 subscribers and 2,847 non-subscribers. Their average purchase amounts were $59.49 and $59.87, respectively.
- **Age-group revenue:** The Young Adult segment contributed the most revenue among the age groups shown, at $62,143.

These results are descriptive findings from the analyzed dataset. They do not, by themselves, establish that shipping type, discounts, or subscriptions caused changes in spending.

## 7. Business Recommendations

1. **Test subscription benefits:** Evaluate targeted offers and clearly communicate subscriber benefits to encourage sign-ups.
2. **Strengthen customer loyalty:** Develop retention campaigns for Returning customers and reward repeat purchasing behavior.
3. **Review discount effectiveness:** Compare additional sales against discount cost and profit margins before expanding promotions.
4. **Promote well-rated products:** Consider featuring highly rated products, such as Gloves, alongside category best-sellers.
5. **Refine customer targeting:** Test campaigns for higher-revenue age groups and review fulfillment preferences using customer-level measures.

Recommendations should be validated with further analysis, especially customer-level conversion rates, profit margins, and trends over time.

## 8. Repository Structure

A suggested layout for keeping the project files organized is shown below. Adjust the names to match the files in your repository.

```text
customer-shopping-behavior-analysis/
├── data/
│   └── <source-dataset.csv>
├── notebooks/
│   └── customer_shopping_analysis.ipynb
├── sql/
│   └── customer_shopping_analysis.sql
├── powerbi/
│   └── customer_shopping_dashboard.pbix
├── reports/
│   └── Customer_Shopping_Behavior_Analysis.pdf
├── presentation/
│   └── Customer_Shopping_Analysis.pptx
└── README.md
```

Only include files and folders that are actually present in your GitHub repository. If the dataset is too large or has sharing restrictions, document its source and instructions for obtaining it instead of committing it.

## 9. How to Run the Project

### Prerequisites

- Python 3.x
- Jupyter Notebook or JupyterLab
- MySQL Server and MySQL Workbench
- Power BI Desktop to open and interact with the `.pbix` dashboard
- The source CSV dataset

### Run the Python analysis

1. Clone your repository and open the project folder:

   ```bash
   git clone <your-repository-url>
   cd <repository-folder>
   ```

2. (Recommended) Create and activate a virtual environment:

   ```bash
   python -m venv .venv
   ```

   On Windows:

   ```bash
   .venv\Scripts\activate
   ```

3. Install the Python packages required by your notebook. A typical setup uses:

   ```bash
   pip install pandas jupyter sqlalchemy pymysql
   ```

   If your notebook uses a different MySQL driver, install that driver instead.

4. Place the CSV file in the expected location and update the notebook's file path if necessary.
5. Start Jupyter:

   ```bash
   jupyter notebook
   ```

6. Open the project notebook and run the cells in order to explore, clean, and prepare the dataset.

### Run the SQL analysis

1. Start MySQL Server and create or select a database for the project.
2. Run the notebook's database-loading step to write the cleaned data to MySQL.
3. Open the SQL script in MySQL Workbench, confirm that the database and table names match your setup, and run the queries.

### Open the Power BI dashboard

1. Open the project's `.pbix` file using Power BI Desktop.
2. If prompted, configure the data source to match your MySQL setup or use the model included in the report.
3. Refresh the data if your database connection is configured, then explore the dashboard filters and visuals.

**Security note:** Do not commit database passwords, API keys, or other credentials to GitHub. Use local configuration or environment variables for connection details.

## 10. Skills Demonstrated

- Exploratory data analysis (EDA)
- Data cleaning and feature engineering with Pandas
- Connecting Python to a relational database
- Writing SQL queries for business analysis
- Customer segmentation and comparative analysis
- Building KPI-focused Power BI dashboards
- Translating analytical results into recommendations and project documentation

## 11. Project Deliverables

- Python notebook for data inspection, cleaning, and preparation
- MySQL queries for the ten business questions
- Interactive Power BI dashboard
- Project report
- Project presentation

---

**Project focus:** Turning customer shopping data into understandable insights through Python, MySQL, and Power BI.
