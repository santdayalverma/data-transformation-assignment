# SQL-Based Table Comparison

## Objective
This task compares two product catalog CSV files from two different days to:
- Identify full rows that were added or removed.
- Detect column-level changes (such as changes in `price` or `stock`) for matching product IDs.

## Technologies Used
- Python (Jupyter Notebook)
- SQLite (via `sqlite3`)
- Pandas

## Approach

### 1. Data Import
- Loaded `products_day1.csv` and `products_day2.csv` into pandas DataFrames.
- Stored these tables in an in-memory SQLite database using `sqlite3`.

### 2. Full Row Comparison
- Used SQL `EXCEPT` clause to find:
  - Rows present in Day 1 but not in Day 2 (`REMOVED`)
  - Rows present in Day 2 but not in Day 1 (`ADDED`)
- Merged both result sets into a final DataFrame with a `change_type` column.

### 3. Column-Level Comparison
- Performed `JOIN` on `product_id`.
- Compared `price` and `stock` columns using SQL `WHERE` clause.
- Captured changes with the structure:
  - `product_id`, `column_changed`, `old_value`, `new_value`

## Output
- `changes_df`: Full row changes with `ADDED` or `REMOVED` status.
- `column_diff_df`: Field-level differences for updated rows.

## Scalability
- Queries are dynamic and do not rely on hardcoded values.
- Designed to handle any number of columns by modifying query logic programmatically if needed.

## Files
- `sql_task.ipynb`: Contains all code and outputs.
- `products_day1.csv`, `products_day2.csv`: Input data files.
