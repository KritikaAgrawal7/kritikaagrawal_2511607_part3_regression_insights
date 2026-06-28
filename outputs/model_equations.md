# Model Equations

## Project
**AI Business Analytics Capstone – Part 3**

This document supports **two deliverables** in the capstone project:

- **Task 3:** Documentation of dummy variable creation and encoding methodology.
- **Task 8:** Documentation of the regression equations, model coefficients, and interpretation of the final predictive model.

---

# Task 3 – Dummy Variable Encoding

## Why Dummy Variables Were Created

The dataset contains categorical variables such as **Region** and **Store Type**. Since linear regression models require numerical inputs, these categorical variables were converted into binary (dummy) variables.

Each dummy variable takes one of two values:

- **1** → Observation belongs to that category
- **0** → Observation does not belong to that category

---

## Region Encoding

The original **Region** variable contains four categories:

- North
- South
- East
- West

To avoid the **Dummy Variable Trap** (perfect multicollinearity), one category must be used as the reference category.

### Reference Category

**West**

Dummy variables created:

| Original Category | Dummy Variable |
|-------------------|---------------|
| North | Region_North |
| South | Region_South |
| East | Region_East |

West is represented when:

```
Region_North = 0
Region_South = 0
Region_East = 0
```

---

## Store Type Encoding

The original Store Type variable contains four categories:

- Residential
- Mall
- High Street
- Airport

For the final regression model, only the **Mall** category was included as a dummy variable.

### Reference Category

**Residential**

Dummy variable:

| Original Category | Dummy Variable |
|-------------------|---------------|
| Mall | Store_Mall |

Residential stores are represented when:

```
Store_Mall = 0
```

---

## Why Reference Categories Are Required

Including dummy variables for every category causes perfect multicollinearity because one dummy can always be predicted from the others.

This issue is known as the **Dummy Variable Trap**.

By omitting one category and treating it as the reference category, the regression coefficients measure the effect of each included category relative to that reference.

---

# Task 8 – Regression Model Equations

## Simple Linear Regression Models

### Model 1 – Marketing Spend

$begin:math:display$
Monthly\\ Sales \= 589\,285\.77 \+ 2\.13 \\times Marketing\\ Spend
$end:math:display$

Purpose:
- Measures the relationship between marketing spend and monthly sales.

---

### Model 2 – Footfall

$begin:math:display$
Monthly\\ Sales \= 384\,238\.83 \+ 40\.07 \\times Footfall
$end:math:display$

Purpose:
- Measures the relationship between customer footfall and monthly sales.

---

# Multiple Linear Regression Model (Final Model)

The final selected model is:

$begin:math:display$
\\hat\{Sales\} \=
79\,514\.81
\+ 1\.1865\(Marketing\\ Spend\)
\+ 33\.7286\(Footfall\)
\+ 3039\.8855\(Inventory\\ Availability\)
\+ 10421\.6659\(Customer\\ Rating\)
\+ 15257\.5678\(Store\\ Mall\)
$end:math:display$

Where:

- **Sales** = Predicted Monthly Sales
- **Marketing Spend** = Monthly marketing expenditure
- **Footfall** = Number of customer visits
- **Inventory Availability** = Inventory availability percentage (0–100)
- **Customer Rating** = Average customer rating
- **Store_Mall**
  - 1 = Mall store
  - 0 = Residential store (reference category)

---

# Interpretation of Model Coefficients

## Marketing Spend

Coefficient = **1.1865**

Holding all other variables constant, every additional ₹1 spent on marketing is associated with approximately **₹1.19 higher monthly sales**.

---

## Footfall

Coefficient = **33.73**

Each additional customer visiting the store is associated with approximately **₹33.73 higher monthly sales**, holding all other variables constant.

---

## Inventory Availability

Coefficient = **3039.89**

Inventory Availability is measured as a percentage (0–100).

Holding other variables constant, a **1 percentage point increase** in inventory availability is associated with approximately **₹3,040 higher monthly sales**.

---

## Customer Rating

Coefficient = **10421.67**

A one-point increase in customer rating is associated with approximately **₹10,422 higher monthly sales**, while keeping all other variables constant.

---

## Store Type (Mall)

Coefficient = **15257.57**

Mall stores are predicted to generate approximately **₹15,258 higher monthly sales** than Residential stores, after controlling for all other variables.

---

# Final Model Performance

| Metric | Value |
|---------|------:|
| Multiple R | 0.9008 |
| R² | 0.8115 |
| Adjusted R² | 0.8085 |
| Standard Error | 45,415 |
| F-statistic | 270.30 |
| Significance F | 1.885 × 10⁻¹¹¹ |

---

---

# Reference Category Used

The categorical variable **Store Type** was encoded using dummy variables before regression analysis.

- **Reference Category:** Residential
- **Dummy Variable Included:** Store_Mall

Interpretation:

- `Store_Mall = 1` → Mall store
- `Store_Mall = 0` → Residential store (baseline/reference)

The coefficient for **Store_Mall** therefore measures the expected difference in monthly sales between Mall stores and Residential stores, after controlling for all other variables in the model.

---

# Final Model Selected

The **Multiple Linear Regression Model** was selected as the final predictive model.

### Final Model Equation

$begin:math:display$
\\hat\{Sales\} \=
79\,514\.81
\+ 1\.1865\(Marketing\\ Spend\)
\+ 33\.7286\(Footfall\)
\+ 3039\.8855\(Inventory\\ Availability\)
\+ 10421\.6659\(Customer\\ Rating\)
\+ 15257\.5678\(Store\\ Mall\)
$end:math:display$

This model includes:

- Marketing Spend
- Footfall
- Inventory Availability (%)
- Customer Rating
- Store_Mall (Residential as the reference category)

---

# Reason for Selecting the Final Model

The Multiple Linear Regression model was selected because it provided the best balance of predictive accuracy and business relevance.

### Statistical Evidence

| Metric | Value |
|---------|------:|
| R² | **0.8115** |
| Adjusted R² | **0.8085** |
| F-statistic | **270.30** |
| Significance F | **1.885 × 10⁻¹¹¹** |
| Standard Error | **45,415** |

### Why This Model Was Selected

- Explains approximately **81.15%** of the variation in monthly sales.
- All predictor variables included in the model are statistically significant (p-value < 0.05).
- Evaluates multiple business drivers simultaneously instead of considering one factor at a time.
- Produces substantially better predictive performance than either simple regression model.
- Provides practical business insights that can directly support marketing, operations, inventory management and customer experience decisions.

Therefore, this model was selected as the **final regression model** for the project.


