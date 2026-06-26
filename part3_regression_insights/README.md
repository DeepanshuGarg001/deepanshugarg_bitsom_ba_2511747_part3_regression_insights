# Part 3: Regression-Based Business Insights & Model Interpretation

## 1. Business Problem Summary
The leadership team of our retail chain wants to understand the primary factors driving monthly sales performance across 80 store locations. They need to know whether to focus on marketing spend, inventory availability, discounting, or real estate strategy (store types/regions) to maximize revenue. We are using regression analysis to identify the strongest associations and formulate actionable business recommendations.

## 2. Dataset Description
The dataset (`business_regression_data.xlsx`) contains 80 rows, with each row representing a unique retail store over a one-month period. 
**Data Preparation:** 
Rows with missing numerical values were imputed with the dataset median (e.g., missing marketing spend). Categorical variables with missing values were imputed using the mode. 

## 3. Dependent and Independent Variables
- **Dependent Variable:** `monthly_sales` (The outcome we are trying to predict/explain).
- **Potential Independent Variables:** `marketing_spend`, `footfall`, `inventory_availability_pct`, `avg_discount_pct`, `customer_rating`, `region`, `store_type`.
- **Variables dropped:** `store_id` (a unique identifier with no predictive value).

## 4. Regression Approach
We started with **Simple Linear Regression** models to isolate the impact of individual continuous variables (Marketing Spend and Footfall) against Sales. However, simple regression suffers from omitted variable bias. We then built a **Multiple Linear Regression** model incorporating our strongest numerical predictors and categorical dummy variables to isolate the true marginal impact of each business lever while controlling for other factors.

## 5. Dummy Variable Approach
Regression models require numerical inputs. We transformed the categorical variables `region` and `store_type` into binary dummy variables (1 or 0). 
To avoid perfect multicollinearity (the dummy variable trap), we dropped one category from each grouping to act as the baseline reference:
- **Reference Region:** `North`
- **Reference Store Type:** `Mall`
All resulting coefficients are interpreted in comparison to these baselines.

## 6. Model Comparison Summary
The Multiple Regression model vastly outperformed the simple models. The simple models had much lower explanatory power, whereas the multiple regression model achieved an R-squared of ~0.83. This indicates that sales are a complex function of marketing, traffic, inventory, and location, and cannot be accurately predicted by looking at just one metric in isolation. 

## 7. Final Model Selected
We selected the **Multiple Regression Model** as the final model because of its high R-squared value and ability to control for confounding variables, providing much cleaner coefficient estimates for business decision-making.

## 8. Business Recommendation
Based on the multiple regression model, leadership should prioritize improving **Inventory Availability**, as it has a massive positive impact on sales (p=0.000). They should also maintain or slightly increase **Marketing Spend** due to its proven positive return. Strategically, the company should halt expansion into **Residential** store types, as they structurally underperform Mall locations by ~$28,000 per month. Leadership should *not* over-index on Regional strategy, as the data proved region is not statistically significant.

## 9. Assumptions and Limitations
- **Linearity:** The model assumes the relationship between variables is perfectly linear, ignoring the law of diminishing returns (e.g., ad saturation).
- **Omitted Variables:** The residual analysis identified specific stores that wildly over/underperformed the prediction. This implies we are missing unquantified variables, such as local competitor density or store manager quality.
- **Correlation ≠ Causation:** The model proves an association between marketing and sales, but cannot definitively prove that marketing *caused* the sales without a controlled randomized experiment.

## 10. Screenshots Included
The following screenshots can be found in the `screenshots/` directory:
- `simple_regression_output.png` (Simple regression output)
- `multiple_regression_output.png` (Multiple regression output)
- `residuals_preview.png` (Predicted values and largest residuals)
- `model_comparison_preview.png` (Model comparison table)
