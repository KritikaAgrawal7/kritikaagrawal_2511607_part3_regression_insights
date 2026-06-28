# AI Business Analytics Capstone – Part 3

## Project Overview

This project builds predictive regression models to identify the key business factors associated with monthly sales across retail stores. The objective is to determine which operational and business variables have the strongest relationship with sales and provide evidence-based recommendations for business decision-making.

The project follows a complete analytics workflow, including data preparation, exploratory analysis, simple regression, multiple regression, dummy variable creation, model comparison, residual analysis, and business interpretation.

---

# Business Problem

Retail leadership wants to understand which operational factors are most strongly associated with monthly sales so they can prioritize investments and improve store performance.

The analysis answers questions such as:

- Which variables have the strongest relationship with sales?
- How much does each variable contribute?
- Does store type influence sales?
- Which regression model provides the most reliable predictions?

---

# Dataset Description

The dataset contains **320 retail stores** with operational, customer, and financial information.

**Target Variable (Dependent Variable)**

- Monthly Sales

**Independent Variables**

- Marketing Spend
- Footfall
- Inventory Availability (%)
- Customer Rating
- Store Type (Residential / Mall)

---

# Regression Approach

Three regression models were developed and compared.

## 1. Simple Regression – Marketing Spend

**Equation**

Monthly Sales = 56,077.35 + 2.13 × Marketing Spend

### Results

| Metric | Value |
|---------|------:|
| R² | 0.167 |
| Adjusted R² | 0.165 |
| F Statistic | 63.865 |
| Significance F | 2.48 × 10⁻¹⁴ |

### Interpretation

Marketing spend has a statistically significant positive relationship with monthly sales. However, it explains only about **16.7%** of the variation in sales and is therefore insufficient as a standalone predictor.

---

## 2. Simple Regression – Footfall

**Equation**

Monthly Sales = 44,610.58 + 35.68 × Footfall

### Results

| Metric | Value |
|---------|------:|
| R² | 0.736 |
| Adjusted R² | 0.735 |
| F Statistic | 887.849 |
| Significance F | 4.75 × 10⁻⁹⁴ |

### Interpretation

Footfall is a very strong predictor of monthly sales, explaining nearly **74%** of the variation in sales.

---

## 3. Multiple Regression (Final Model)

The final model includes all statistically significant business variables.

### Model Performance

| Metric | Value |
|---------|------:|
| R² | **0.8115** |
| Adjusted R² | **0.8085** |
| Standard Error | **45,415** |
| F Statistic | **270.30** |
| Significance F | **1.885 × 10⁻¹¹¹** |

The model explains approximately **81% of the variation** in monthly sales, making it substantially more accurate than either simple regression model.

---

# Dummy Variable Approach

Store Type is a categorical variable.

To include it in the regression model, dummy variable encoding was used.

| Original Variable | Dummy Variable |
|------------------|---------------|
| Residential | Reference Category (0) |
| Mall | Store_Mall = 1 |

Residential stores were selected as the reference category.

The coefficient for **Store_Mall** therefore measures the expected difference in sales between Mall stores and Residential stores while holding all other variables constant.

---

# Model Equations

## Simple Regression (Marketing Spend)

Monthly Sales = 56,077.35 + 2.13 × Marketing Spend

---

## Simple Regression (Footfall)

Monthly Sales = 44,610.58 + 35.68 × Footfall

---

## Final Multiple Regression Model

Monthly Sales =
79,514.81
+ 1.186 × Marketing Spend
+ 33.729 × Footfall
+ 3,039.89 × Inventory Availability (%)
+ 10,421.67 × Customer Rating
+ 15,257.57 × Store_Mall

---

# Interpretation of Coefficients

## Marketing Spend

Holding all other variables constant, every additional ₹1 spent on marketing is associated with approximately **₹1.19 higher monthly sales**.

**p-value:** 1.95 × 10⁻¹⁷

---

## Footfall

Holding all other variables constant, every additional customer visiting the store is associated with approximately **₹33.73 higher monthly sales**.

**p-value:** 3.53 × 10⁻¹⁰¹

This is the strongest predictor in the model.

---

## Inventory Availability

Holding all other variables constant, a **1 percentage point increase** in inventory availability is associated with approximately **₹3,040 higher monthly sales**.

**p-value:** 6.34 × 10⁻¹⁰

Maintaining product availability has a meaningful positive association with sales.

---

## Customer Rating

Holding all other variables constant, a **1-point increase** in customer rating is associated with approximately **₹10,422 higher monthly sales**.

**p-value:** 0.0354

Although its effect is smaller than footfall, customer rating remains a statistically significant driver of sales.

---

## Store Type (Mall)

Holding all other variables constant, Mall stores are expected to generate approximately **₹15,258 higher monthly sales** than Residential stores.

**p-value:** 0.0113

---

# Model Comparison

| Model | R² | Selected |
|------|------:|:---------:|
| Marketing Spend | 0.167 | ❌ |
| Footfall | 0.736 | Good Benchmark |
| Multiple Regression | **0.811** | ✅ Final Model |

The multiple regression model achieved the highest explanatory power and included all statistically significant business drivers.

---

# Residual Analysis

Predicted sales values and residuals were calculated using the final regression model.

Residuals were computed as:

> Residual = Actual Sales − Predicted Sales

The largest positive residuals indicate stores that performed substantially better than predicted, suggesting the influence of additional factors not included in the model.

The largest negative residuals indicate stores that underperformed relative to expectations.

Residual analysis showed no obvious systematic pattern of under-prediction or over-prediction, suggesting that the final regression model provides reasonably balanced predictions across the dataset.

---

# Business Recommendations

Based on the regression analysis:

- Increase store footfall through targeted marketing campaigns and promotional activities, as footfall is the strongest predictor of monthly sales.
- Continue investing in marketing initiatives, as marketing spend has a statistically significant positive association with sales.
- Improve inventory availability to reduce stock-outs and maximize sales opportunities.
- Focus on improving customer experience and service quality, as higher customer ratings are associated with increased sales.
- Study the operational practices of Mall stores to identify strategies that can be replicated in Residential stores.

---

# Assumptions and Limitations

This analysis assumes:

- Linear relationships between predictors and sales.
- Independent observations.
- Constant error variance.
- Approximately normally distributed residuals.

Limitations include:

- Regression identifies associations but does not establish causation.
- External factors such as seasonality, promotions, competitor actions, macroeconomic conditions, and local demographics were not included.
- Approximately 19% of the variation in sales remains unexplained by the model.

---

# Screenshots Included

The repository contains the following evidence files:

- `screenshots/simple_regression_output.png`
- `screenshots/multiple_regression_output.png`
- `screenshots/residuals_preview.png`
- `screenshots/model_comparison_preview.png`

---

# Final Conclusion

The multiple regression model was selected as the final predictive model because it provides the highest explanatory power (**R² = 0.8115**) while including multiple statistically significant business drivers.

Among all variables, **Footfall** has the strongest association with monthly sales, followed by **Inventory Availability**, **Marketing Spend**, **Customer Rating**, and **Store Type**.

The findings suggest that improving customer traffic, maintaining product availability, investing in marketing, enhancing customer experience, and leveraging the advantages of Mall locations can collectively contribute to higher monthly sales. While the model offers strong predictive capability, business decisions should also consider operational knowledge and external market conditions since regression analysis demonstrates association rather than causation.
