# Residual Analysis

## Objective

Residual analysis was performed on the final multiple linear regression model to evaluate prediction errors and identify records where the model significantly under-predicted or over-predicted monthly sales.

## Residual Formula

```
Residual = Actual Sales − Predicted Sales
```

- **Positive Residual:** Actual sales are higher than predicted (model under-predicted).
- **Negative Residual:** Actual sales are lower than predicted (model over-predicted).

---

# Top 5 Positive Residuals (Largest Under-predictions)

| Rank | Store ID | Month | Actual Sales | Predicted Sales | Residual |
|------|----------|--------|-------------:|----------------:|----------:|
| 1 | STR-1064 | 2025-02 | 799,046.94 | 691,616.53 | **107,430.41** |
| 2 | STR-1028 | 2025-04 | 713,611.16 | 609,641.78 | **103,969.38** |
| 3 | STR-1069 | 2025-04 | 686,737.87 | 590,877.08 | **95,860.79** |
| 4 | STR-1051 | 2025-02 | 787,715.51 | 692,756.16 | **94,959.35** |
| 5 | STR-1032 | 2025-01 | 914,544.17 | 821,012.95 | **93,531.22** |

## Business Interpretation

These observations have the largest positive residuals, meaning actual sales exceeded the model's predictions.

Possible business explanations include:

- Successful local marketing campaigns or promotional activities not captured in the dataset.
- Temporary increases in customer demand due to seasonal or local events.
- Exceptional store performance driven by superior customer service or operational efficiency.
- Reduced competition or other external factors that boosted sales unexpectedly.

These records indicate situations where additional business variables could improve prediction accuracy.

---

# Top 5 Negative Residuals (Largest Over-predictions)

| Rank | Store ID | Month | Actual Sales | Predicted Sales | Residual |
|------|----------|--------|-------------:|----------------:|----------:|
| 1 | STR-1017 | 2025-03 | 685,379.08 | 832,694.85 | **-147,315.77** |
| 2 | STR-1023 | 2025-02 | 627,171.90 | 756,210.48 | **-129,038.58** |
| 3 | STR-1012 | 2025-01 | 595,467.60 | 719,266.35 | **-123,798.75** |
| 4 | STR-1009 | 2025-01 | 641,865.03 | 759,314.73 | **-117,449.70** |
| 5 | STR-1001 | 2025-04 | 658,920.30 | 764,668.48 | **-105,748.18** |

## Business Interpretation

These observations have the largest negative residuals, indicating that the model predicted higher sales than were actually achieved.

Possible business explanations include:

- Lower-than-expected customer demand.
- Inventory shortages or stock availability issues.
- Reduced effectiveness of marketing activities.
- Operational disruptions such as staffing shortages, weather conditions, or increased local competition.

These cases highlight factors affecting sales that are not represented in the current model.

---

# Overall Residual Analysis

The residuals contain both positive and negative values, indicating that the model does not consistently over-predict or under-predict monthly sales.

### Key Observations

- The model exhibits both under-predictions and over-predictions.
- The residuals include both positive and negative values, with only a small number of observations exhibiting exceptionally large prediction errors. This suggests that the model generally performs consistently across the dataset while leaving room for improvement through the inclusion of additional business variables.- Only a small number of observations have exceptionally large residuals.
- There is no strong evidence of systematic prediction bias.

Overall, the regression model provides a reasonably good fit to the data. However, prediction accuracy could potentially be improved by including additional business variables such as:

- Local events and festivals
- Weather conditions
- Store-specific promotional campaigns
- Competitor activities
- Customer demographics
- Economic conditions

---

# Conclusion

The final multiple linear regression model provides a reasonable fit for predicting monthly sales across stores. Residual analysis indicates that the model does not consistently over-predict or under-predict sales, suggesting that it is generally unbiased.

The largest residuals likely result from business factors not included in the model. Incorporating additional explanatory variables in future iterations could further improve prediction accuracy and reduce forecasting errors.

