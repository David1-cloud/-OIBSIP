# EDA on Retail Sales Data

## Objective
Perform exploratory data analysis on the Superstore retail sales dataset to uncover 
patterns in sales trends, customer segments, product performance, and regional 
differences, and translate findings into actionable business recommendations.

## Dataset
9,800 rows, 18 columns (Superstore Sales dataset) — Order/Ship dates, Customer info, 
Segment, Region, Product Category/Sub-Category, Sales. Only Postal Code has minor 
missing values (11 rows), left as-is since geographic analysis uses City/State/Region 
instead.

## Approach
1. Data loading and inspection (shape, dtypes, nulls)
2. Descriptive statistics
3. Monthly and quarterly sales trend analysis
4. Customer segment analysis (substituted for demographics — dataset has no age/gender)
5. Product analysis — top 10 products, revenue by category
6. Correlation heatmap of numeric variables
7. Regional sales analysis (additional insight)
8. Conclusion with actionable recommendations

## Key Findings
- Sales are right-skewed: mean $230.77 vs median $54.49, driven by a few high-value orders
- Clear seasonality with a late-year sales spike and an overall 2015–2018 upward trend
- Consumer segment drives ~1.7x more revenue than Corporate, ~3x more than Home Office
- Technology category revenue is driven by a small number of high-value products
- West and East regions significantly outperform Central and South

## Conclusion & Recommendations
1. Increase inventory/staffing ahead of late-year demand
2. Prioritize marketing/retention on the Consumer segment
3. Investigate underperformance in Central and South regions
4. Maintain both high-value (Technology) and high-volume (Office Supplies) product strategies
