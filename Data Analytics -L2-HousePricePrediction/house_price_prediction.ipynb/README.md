# House Price Prediction

## Objective
Build and evaluate a Linear Regression model to predict house prices based on 
features like area, bedrooms, bathrooms, location, condition, and year built.

## Dataset
2000 houses, 10 columns (Area, Bedrooms, Bathrooms, Floors, YearBuilt, Location, 
Condition, Garage, Price + Id). No missing values.

## Approach
1. EDA — inspected structure, nulls, price distribution
2. Feature selection discussion — hypothesized which features would drive price
3. One-hot encoded categorical columns (Location, Condition, Garage)
4. Correlation heatmap to check feature-price relationships
5. 80/20 train/test split
6. Trained Linear Regression, evaluated with MAE, MSE, RMSE, R²
7. Scatter plot (actual vs predicted) and residual plot
8. Coefficient analysis to see feature impact
9. Trained Random Forest as a comparison model

## Results
| Model | MAE | RMSE | R² |
| Linear Regression | 242,867 | 279,785 | -0.006 |
| Random Forest | 249,685 | 288,573 | -0.070 |

## Conclusion
Both models performed close to (or worse than) simply guessing the average price. 
The correlation heatmap showed near-zero correlation between all features and Price, 
and the coefficient analysis confirmed Area — normally the strongest price driver — 
has almost no effect in this dataset. This strongly suggests the Price column was 
generated synthetically/randomly rather than derived from the listed features. 
Testing Random Forest (a non-linear model) ruled out "wrong model type" as the 
explanation — the limitation is in the data, not the modeling approach.
