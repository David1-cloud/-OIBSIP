# Task 3: Data Cleaning

## About
This project is Task 3 of the Oasis Infobyte Data Analytics Internship (OIB-SIP). 
The goal was to take a deliberately messy retail sales dataset and transform it 
into a clean, analysis-ready dataset, documenting every decision made along the way.

## Dataset
- File used: retail_sales_dataset.csv
- Contains order-level retail data: order details, customer demographics, 
  product information, sales figures, shipping, and satisfaction ratings.

## Tools Used
- Python
- Pandas
- NumPy
- Jupyter Notebook

## What I Did

**1. Data Quality Report**
Checked nulls, duplicates, data types, and value ranges before making any changes.

**2. Missing Data Handling**
- `order_date`: ~7% of rows had missing/unparseable dates. Since dates can't 
  be reliably estimated, these rows were dropped.
- `age`, `quantity`, `days_to_ship`: filled with median (resistant to outlier distortion).
- `discount_pct`: filled with 0 (assumed missing means no discount applied).
- `customer_satisfaction`: filled with median.

**3. Outlier Detection & Correction**
Found impossible values before imputing missing data:
- `age`: contained -7 and 999 (impossible ages)
- `quantity`: contained -1 and 999 (impossible order quantities)
- `days_to_ship`: contained -1 and 100 (impossible/implausible shipping times)

These were converted to missing values first, then filled using the same 
median strategy as genuine nulls, to avoid distorting the dataset with 
impossible numbers.

**4. Duplicate Removal**
Identified and removed exact duplicate rows.

**5. Standardization**
- `gender`: normalized inconsistent casing and abbreviations 
  (e.g. "M", "male", "MALE" → "Male")
- `order_status`: normalized inconsistent casing 
  (e.g. "delivered", "Delivered" → "Delivered")
- `order_date`: converted to proper datetime format

**6. Data Type Correction**
Verified all columns had correct types:
- IDs (`customer_id`, `order_id`) as string/object
- Monetary columns (`sales_amount`, `profit`, `shipping_cost`, `unit_price`) as float

**7. Before vs. After Summary**
Produced a comparison table of row count, total nulls, and duplicate rows 
between the raw and cleaned dataset.

## Key Results
| Metric | Before | After |
|---|---|---|
| Row Count | [4310] | [3933] |
| Total Nulls | [1455] | 0 |
| Duplicate Rows [109] | 0 |

## How to Run
1. Clone this repository
2. Open `[your_notebook_filename].ipynb` in Jupyter Notebook
3. Run all cells in order to reproduce the cleaning process

## Output
The cleaned dataset is saved as `cleaned_retail_sales_dataset.csv`.

## Author
David Fiyinfoluwa Okusanya — Oasis Infobyte Data Analytics Intern
