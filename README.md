# Power Query Set Demo (Power BI)

A small Power BI project built to demonstrate **Power Query cleaning (ETL)** + a simple **report/dashboard layer** on top of a deliberately “messy” sales dataset.

This repo is designed as a practical example of the kind of work you’d do before any visuals are trustworthy:
- fix data types
- standardise inconsistent text values
- handle errors / nulls
- build reusable calculated fields / measures
- then report on sales performance with confidence

---

## What the task was (Bootcamp-style expectation)

The typical objective for this kind of exercise is to prove you can take raw, imperfect data and:
1. **Ingest** it into Power BI
2. **Transform** it using Power Query (not manual Excel edits)
3. **Model + calculate** key business metrics (revenue, profit, margin, performance views)
4. **Deliver** a set of clear visuals that answer basic business questions

---

## What I built

### 1) Dataset (intentionally messy)
The dataset includes columns such as:
- **Order fields:** `Order ID`, `Date`, `Order Date Text`, `Year`
- **Product fields:** `Product`, `Category`
- **Geography fields:** `State`, `Region`, `Region (Messy)`, `City-State`, `Country`
- **Commercial fields:** `Quantity Sold`, `Cost Price`, `Selling Price`, `Discount Flag`, `Target Margin %`
- **People:** `Salesperson`

It contains common real-world issues, for example:
- mixed date formats across date fields
- inconsistent casing in names (e.g., salesperson values)
- categorical “unknowns” (e.g., discount flag)
- numeric fields containing errors / text values (e.g., selling price containing non-numeric values)

### 2) Power Query transformations (ETL)
In Power Query, the focus is on making the dataset reliable and model-ready. Typical steps include:
- **Type enforcement** (dates as dates, prices as numbers, quantities as whole numbers)
- **Date parsing** from multiple text patterns
- **Standardising text** (trim/clean, consistent casing, consistent category values)
- **Error handling** (replace/remove error rows where appropriate, manage nulls)
- **Derived columns** to support reporting (e.g., a clean “region”, clean salesperson)

> The overall goal: you should be able to refresh the model from the CSV and get consistent results every time.

### 3) Report / dashboard layer
The `.pbix` contains report pages built on top of the cleaned model to explore:
- overall sales performance
- breakdown by product/category
- geography views (region/state)
- salesperson comparisons
- any “data quality” implications exposed by the cleaning work

---

## How to run / view

1. Download / clone the repo
2. Open the Power BI file:

- `PowerBI/querysetdemo/powerquerydatasetwithdashboards.pbix`

3. If Power BI prompts for the data source, point it to:

- `PowerBI/querysetdemo/power_query_data_powerquery_demo.csv`

4. Click **Refresh** to re-run the Power Query steps and rebuild the report.

---

## Repo structure

```text
PowerBI/
  querysetdemo/
    powerquerydatasetwithdashboards.pbix
    power_query_data_powerquery_demo.csv
