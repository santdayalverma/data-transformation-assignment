# Python-Based Data Cleaning and Transformation

## Objective
This task involves cleaning a raw sales dataset by:
- Validating and converting data types
- Handling missing or malformed values
- Computing a derived column `total_price = quantity * price_per_unit`

## Technologies Used
- Python (pandas, datetime)
- Jupyter Notebook

## Approach

### 1. Data Loading
- Loaded the `raw_sales.csv` dataset into a pandas DataFrame.

### 2. Data Cleaning (UDF-based)
Created and applied custom functions to:
- Convert `order_id`, `product_id`, and `quantity` to integers.
- Convert `price_per_unit` to float.
- Parse `order_date` into a consistent `datetime` format.
- Replace missing or malformed values with defaults (`0`, `0.0`, or `NaT`).

### 3. Feature Engineering
- Defined a UDF `calculate_total_price` that computes total cost.
- Added a new column `total_price = quantity * price_per_unit`.

### 4. Output
- Final cleaned DataFrame saved to `cleaned_sales.csv`.

## Robustness & Scalability
- All logic encapsulated in functions.
- Data validation uses `errors='coerce'` to gracefully handle malformed inputs.
- Script is scalable to larger or more complex datasets.

## Files
- `python_task.ipynb`: Main notebook with all code and outputs.
- `raw_sales.csv`: Raw input data.
- `cleaned_sales.csv`: Cleaned and transformed output.
