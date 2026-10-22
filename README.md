# SQL Summative Lab

## Project Overview
This repository contains the completed SQL Summative Lab. The project is divided into two parts:
- **Part 1:** Guided SQL queries analyzing a wholesale miniature models customer database.
- **Part 2:** Exploratory data analysis (EDA) on an IMDB movie database (2010–2019).

## Part 1: Guided SQL Queries (`data.sqlite`)
The objective was to extract business insights, perform aggregations, and visualize key results for a model company's customer and product data.

### Key Queries & Insights
1. **Limited Edition California Product:** Filtered for California customers with a credit limit over $25,000 using `CAST(creditLimit AS REAL)`.
2. **International Collectable Campaign:** Identified non-US customers whose names contain the word "Collect" using `LIKE '%Collect%'`.
3. **USA Credit & Inventory Policy:** Calculated the average credit limit by state using `GROUP BY`. Visualized with a bar chart.
4. **Top Customers:** Joined the `customers` and `payments` tables to find the top 10 customers by total payments. Visualized with a horizontal bar chart.
5. **Top Customer + Product Quantities:** Joined 4 tables (`customers`, `orders`, `orderdetails`, `products`) to find products purchased in quantities of 10 or more using `HAVING`.
6. **Product Analysis:** Analyzed the relationship between the number of distinct products in a product line and the total quantity ordered. Visualized with a scatter plot.
7. **Remote Offices:** Used a subquery to find office codes with fewer than 5 employees and retrieved those employees' details using a self-join for supervisor information.

### SQL Concepts Utilized
- `JOIN` (INNER, LEFT) & Self-Joins
- Aggregate Functions (`SUM`, `AVG`, `COUNT`)
- `GROUP BY` & `HAVING`
- Subqueries (`IN` clause)
- String matching (`LIKE`)
- Data type casting (`CAST(... AS REAL)`)

## Part 2: Exploratory Analysis (`im.db`)
The objective was to explore the IMDB dataset (movies released 2010–2019) and formulate a business question.

### Exploration & Findings
- **Initial Exploration:** Identified the top 10 most common movie genres (e.g., Drama, Comedy, Action).
- **Business Question:** *"For Action movies released between 2010 and 2019, is there a relationship between runtime and average rating?"*
- **Visualization:** Used a Seaborn `regplot` to show a slight positive correlation between runtime and average rating.
- **Data Cleaning Identified:**
  1. **Null Handling:** Excluded nulls in `runtime_minutes` and `averagerating`.
  2. **Genre Normalization:** The `genres` column contains comma-separated values. It needs to be exploded/split for accurate single-genre analysis.
  3. **Date Filtering:** Excluded data with `start_year > 2019` to ensure accuracy.

## Repository Notes
- **Large Files Excluded:** The `im.db` (161 MB) and `im.db.zip` (64 MB) files exceed GitHub's file size limits and have been excluded from this repository. They can be generated/extracted locally to run the notebook.
- **Dependencies:** `pandas`, `sqlite3`, `matplotlib`, `seaborn`.

## How to Use
1. Clone the repository.
2. Ensure `data.sqlite` and `im.db` are present in the root directory.
3. Open `SQLSummativeLab.ipynb` in Jupyter Notebook or VS Code.
4. Run all cells to reproduce the queries and visualizations.