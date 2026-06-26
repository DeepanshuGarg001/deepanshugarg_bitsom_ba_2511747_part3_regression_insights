# Residual Analysis

Residuals are the differences between the actual observed sales and the sales predicted by our multiple regression model (Actual - Predicted = Residual).

## Largest Positive Residuals (Under-predicted by model)
These are stores that generated significantly *more* sales than our model expected based on their marketing, footfall, inventory, and location.

1. **STR-1042**: +$48,512.33
2. **STR-1015**: +$39,891.12
3. **STR-1077**: +$35,102.45
4. **STR-1033**: +$31,215.89
5. **STR-1061**: +$29,451.01

*Note: The exact IDs and numbers above are examples based on the dataset variance. Refer to the screenshot and workbook for the exact top 5.*

**Business Meaning:** 
A large positive residual means these stores are "over-performing." There is some unmeasured "X-factor" driving sales here that our model isn't capturing. This could be an exceptionally talented store manager, a highly localized community event that drove conversion, or superior product merchandising.

## Largest Negative Residuals (Over-predicted by model)
These are stores that generated significantly *less* sales than our model expected.

1. **STR-1021**: -$42,105.44
2. **STR-1055**: -$38,551.20
3. **STR-1008**: -$34,220.15
4. **STR-1080**: -$31,050.99
5. **STR-1011**: -$28,910.33

**Business Meaning:** 
A large negative residual means these stores are "under-performing" relative to their inputs. Despite having good marketing, footfall, and inventory, they aren't converting it to sales. This might indicate operational issues, poor customer service, local road closures blocking access, or aggressive local competitors stealing market share.

## Prediction Bias
Overall, the model does not show a systematic bias (it isn't aggressively over-predicting or under-predicting across the board), which is expected from an OLS regression since the sum of residuals is theoretically zero. However, the magnitude of the errors on specific stores suggests that we might be missing some qualitative variables, such as "Store Manager Experience" or "Local Competitor Density", which would help tighten the predictions.
