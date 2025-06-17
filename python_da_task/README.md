# Python Data Cleaning Task

## Objective
Clean and transform raw sales data, compute total prices, and export cleaned data.

## Approach
- Loaded `raw_sales.csv`
- Converted data types with UDFs:
  - Integers: `order_id`, `product_id`, `quantity`
  - Float: `price_per_unit`
  - Datetime: `order_date`
- Handled missing/invalid values using `errors='coerce'` and `.fillna()`
- Created and applied UDF to compute `total_price = quantity * price_per_unit`
- Saved cleaned dataset to `cleaned_sales.csv`
