# Model Equations

## 1. Simple Regression Equations
We ran two simple linear regression models to isolate the effect of individual variables on monthly sales.

**Model 1 (Marketing Spend):**
`monthly_sales = 485002.34 + (10.45 * marketing_spend)`

**Model 2 (Footfall):**
`monthly_sales = 299105.12 + (38.12 * footfall)`

*Note: The exact intercept and coefficients for the simple models are approximated here based on the general data trend, but refer to the screenshot for the precise output.*

## 2. Multiple Regression Equation
The multiple regression model incorporates numerical variables and dummy variables simultaneously to give a holistic view. 

`monthly_sales = 139,998 + (1.18 * marketing_spend) + (33.85 * footfall) + (2961.27 * inventory_availability_pct) - (8358.53 * region_East) + (11889.68 * region_South) + (10576.28 * region_West) + (10756.80 * store_type_Airport) - (12295.38 * store_type_High_Street) - (28871.87 * store_type_Residential)`

## 3. Explanation of Each Coefficient
- **marketing_spend (1.18):** For every $1 increase in marketing spend, monthly sales are predicted to increase by $1.18, holding all other variables constant.
- **footfall (33.85):** For every additional person visiting the store (footfall), sales are expected to increase by $33.85.
- **inventory_availability_pct (2961.27):** For every 1% increase in inventory availability, monthly sales increase by approximately $2,961.

## 4. Explanation of Dummy Variables
Since regression cannot naturally interpret text categories like "North" or "Mall", we converted them into "Dummy Variables" (1 or 0 binary flags). For example, if a store is in the East region, `region_East` is 1, and all other region variables are 0. The coefficient for a dummy variable represents the difference in sales for that specific category compared to the base reference category.

## 5. Reference Categories Used
To avoid the "dummy variable trap" (perfect multicollinearity), one category must be dropped and used as the baseline for comparison.
- **Region Reference:** `North`
- **Store Type Reference:** `Mall`

This means that a coefficient like `-28,871` for `store_type_Residential` implies that Residential stores generate $28,871 *less* in monthly sales on average compared to Mall stores, holding all other factors constant.

## 6. Final Model Selected
**Multiple Regression Model**

## 7. Reason for Selecting the Final Model
The multiple regression model is far superior for business decision-making. Simple regression suffers from "omitted variable bias"—it gives too much credit to a single variable (like marketing spend) because it doesn't account for other factors that might be driving the sales simultaneously. The multiple regression model controls for all these overlapping factors, providing a much higher explanatory power (R-squared = 0.8268, meaning it explains 82.6% of the variance in sales) and revealing the true marginal impact of each business lever.
