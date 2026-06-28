# Model Comparison

## Overview

Three regression models were developed to identify the factors associated with Monthly Sales.

- Model 1: Simple Regression using Marketing Spend
- Model 2: Simple Regression using Footfall
- Model 3: Multiple Regression using Marketing Spend, Footfall, Inventory Availability, Customer Rating, and Store Type (Dummy Variable)

---

## Model Comparison

| Model | Dependent Variable | Independent Variable(s) | R² | Significant Variables |
|------|--------------------|-------------------------|------:|-----------------------|
| Model 1 | Monthly Sales | Marketing Spend | 0.167 | Marketing Spend |
| Model 2 | Monthly Sales | Footfall | 0.736 | Footfall |
| Model 3 | Monthly Sales | Marketing Spend, Footfall, Inventory Availability, Customer Rating, Store_Mall | 0.811 | All variables |

---

## Variables Used

### Model 1

**Dependent Variable**

- Monthly Sales

**Independent Variable**

- Marketing Spend

---

### Model 2

**Dependent Variable**

- Monthly Sales

**Independent Variable**

- Footfall

---

### Model 3

**Dependent Variable**

- Monthly Sales

**Independent Variables**

- Marketing Spend
- Footfall
- Inventory Availability (%)
- Customer Rating
- Store_Mall (Dummy Variable)

Reference Category:

- Residential = 0
- Mall = 1

---

## R-squared Comparison

Model 1 explains only **16.7%** of the variation in Monthly Sales.

Model 2 explains **73.6%** of the variation, making Footfall a much stronger predictor than Marketing Spend alone.

The Multiple Regression Model explains **81.15%** of the variation in Monthly Sales, demonstrating the strongest explanatory power among all three models.

---

## Significant Variables

### Model 1

Marketing Spend is statistically significant (p < 0.001).

### Model 2

Footfall is statistically significant (p < 0.001).

### Model 3


All predictor variables are statistically significant at the 5% significance level:

| Variable | p-value |
|-----------|---------:|
| Marketing Spend | 1.95 × 10⁻¹⁷ |
| Footfall | 3.53 × 10⁻¹⁰¹ |
| Inventory Availability | 6.34 × 10⁻¹⁰ |
| Customer Rating | 0.0354 |
| Store_Mall | 0.0113 |

- Marketing Spend
- Footfall
- Inventory Availability
- Customer Rating
- Store_Mall

---

## Business Usefulness

### Model 1

Useful for understanding the impact of marketing expenditure on sales but ignores other important business drivers.

### Model 2

Provides a much better explanation of Monthly Sales and highlights the importance of customer traffic.

### Model 3

Provides the most comprehensive business insights by considering marketing, customer traffic, inventory availability, customer satisfaction, and store location simultaneously.

This model is the most suitable for supporting business decisions.

---

## Limitations

Although the Multiple Regression Model performs well, it does not include all possible factors affecting Monthly Sales.

Examples include:

- Seasonality
- Pricing strategy
- Promotions
- Local competition
- Economic conditions
- Store size

Regression also identifies associations between variables but does not prove causation.

---

## Final Model Selected

All three regression models are statistically significant because their overall Significance F values are far below 0.05.

However, the Multiple Regression model was selected because:

- Highest R² (0.8115)
- Highest Adjusted R² (0.8085)
- All predictor variables are statistically significant
- Overall model significance F = 1.885 × 10⁻¹¹¹
- Explains over 81% of variation in Monthly Sales
- Most useful for business decision making

