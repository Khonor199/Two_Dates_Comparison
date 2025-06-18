# Two_Dates_Comparison

# 📊 Price Dynamics Analysis by Supplier and Category

## 🧾 Task Description

The goal of this query is to analyze the change in median prices for products across different suppliers and categories over a 7-day period (from today's date). Additionally, it calculates the percentage of offers that changed their price during this time.

Data is sourced from the `price_snapshot` table, which contains historical pricing data for offers, grouped by category, catalog, and supplier.

---

## 🛠️ Technical Implementation

- **Data Source:** `default.price_snapshot`
- **Dictionaries Used:**
  - `supplier_service_supplier_dict` — to retrieve supplier names
  - `pim_catalog_category_dict` — to retrieve category names
- **ClickHouse Features Applied:**
  - Common Table Expressions (`WITH`)
  - Date filtering (`today()`)
  - Dictionary lookups via `dictGet`
  - Aggregation with `median()` function
  - Conditional logic using `CASE`
  - Optional filtering using Metabase-style placeholders `[[ ]]`

---

## 📌 Key Metrics

| Metric | Description |
|-------|-------------|
| `before_price_50_percentile` | Median price from 8 days ago |
| `current_price_50_percentile` | Median price from yesterday |
| `percent` | Percentage change in median price over the week |
| `counts` | Number of offers whose price has changed |
| `all` | Total number of offers analyzed |

---

## 🔍 Business Insights

This query helps answer the following business questions:

- Which suppliers experienced the largest price changes?
- How volatile are prices within each product category?
- What percentage of offers had price changes in the last week?
- Which suppliers or categories should be monitored due to significant price fluctuations?

---

## 🖥️ Sample Output

![image](https://github.com/user-attachments/assets/f3c22f87-c48e-4952-a4da-70d463bfefbc)
