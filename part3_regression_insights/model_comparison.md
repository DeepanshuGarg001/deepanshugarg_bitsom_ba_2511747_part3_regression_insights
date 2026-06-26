# Model Comparison

We built and analyzed three different models to understand the drivers of monthly sales.

| Required Item | Explanation |
| :--- | :--- |
| **Model Name** | Simple Reg (Marketing), Simple Reg (Footfall), Multiple Regression |
| **Variables Used** | **Model 1:** Marketing Spend.<br>**Model 2:** Footfall.<br>**Model 3:** Marketing spend, footfall, inventory availability pct, region (dummy), store_type (dummy). |
| **R-squared** | The Multiple Regression model drastically outperforms the simple models. It achieved an R-squared of **0.8268** (explaining ~83% of the variance in sales). The simple models performed significantly worse because they try to force a single variable to explain all the variance, ignoring the reality that sales are multi-faceted. |
| **Significant Variables** | In the multiple regression model, the highly significant variables (p-value < 0.05) are: `marketing_spend` (p=0.000), `footfall` (p=0.000), `inventory_availability_pct` (p=0.000), and `store_type_Residential` (p=0.000). The Region variables were generally not statistically significant (p-values > 0.05). |
| **Business Usefulness** | The multiple regression model is highly useful for decision-making. It tells leadership exactly how much return they get for every marginal dollar of marketing spend ($1.18), assuming inventory and footfall remain steady. It also proves that Residential stores structurally underperform Malls, prompting a strategic review of retail locations. |
| **Limitations** | The model does not capture external macro-economic factors (like inflation or competitor discounting). It also relies heavily on linear relationships, meaning it assumes that $1 in marketing always yields the same return regardless of how much we've already spent, which ignores the economic law of diminishing returns. |
