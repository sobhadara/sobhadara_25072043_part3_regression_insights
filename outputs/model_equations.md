
# Part 3 : Regression-Based Business Insights & Model Interpretation
---

## Task 3: Create Dummy Variables

### Categorical Variables

The dataset contains the following categorical variables:

| Variable | Categories |
|-----------|-----------|
| `region` | East, North, South, West |
| `store_type` | Airport, High Street, Mall, Residential |

### Dummy Variable Creation

Dummy variables were created to convert categorical variables into numerical variables suitable for regression analysis.

#### Region

| Reference Category | Created Dummy Variables |
|-------------------|-------------------------|
| `East` | `region_North`, `region_South`, `region_West` |

Interpretation:

- `region_North = 1` if the store belongs to the North region, otherwise 0.
- `region_South = 1` if the store belongs to the South region, otherwise 0.
- `region_West = 1` if the store belongs to the West region, otherwise 0.

Stores belonging to the East region have all region dummy variables equal to 0.

#### Store Type

| Reference Category | Created Dummy Variables |
|-------------------|-------------------------|
| `Airport` | `store_type_High_Street`, `store_type_Mall`, `store_type_Residential` |

Interpretation:

- `store_type_High_Street = 1` if the store is a High Street store, otherwise 0.
- `store_type_Mall = 1` if the store is a Mall store, otherwise 0.
- `store_type_Residential = 1` if the store is a Residential store, otherwise 0.

Stores belonging to the Airport category have all store type dummy variables equal to 0.

### Avoiding the Dummy Variable Trap

One category from each categorical variable was excluded and used as the reference category.

| Variable | Reference Category |
|-----------|-------------------|
| `region` | East |
| `store_type` | Airport |

Using all categories simultaneously would create perfect multicollinearity and make regression coefficients impossible to estimate correctly. Therefore, one category from each variable was omitted.

### Validation Checks

- Created dummy variables for all non-reference categories.
- Retained all observations.
- Retained all numerical variables.
- Excluded one category per categorical variable.
- Avoided perfect multicollinearity.
- Prepared dataset for regression analysis.

### Outcome

- Created dummy variables for `region`.
- Created dummy variables for `store_type`.
- Selected `East` as the reference category for `region`.
- Selected `Airport` as the reference category for `store_type`.
- Updated the `Dummy_Variables` worksheet.
- Prepared the dataset for regression analysis.

---



# Part 3 : Regression-Based Business Insights & Model Interpretation

---

## Task 8: Model Equations

### Simple Regression Model 1

#### Model Equation

- monthly_sales = 560774.22 + 2.1296(marketing_spend)

#### Coefficient Explanation

| Component | Statistical Meaning | Business Meaning |
|---|---|---|
| Intercept (560774.22) | Expected sales when marketing spend is zero. | Represents the baseline sales level before any marketing investment. |
| Marketing Spend Coefficient (2.1296) | Sales increase by approximately 2.13 units for every one-unit increase in marketing spend. | Higher marketing investment is associated with higher sales performance. |

#### Business Interpretation

- Marketing spend has a positive relationship with monthly sales.
- Increasing marketing investment is expected to increase revenue.
- Marketing alone explains a limited portion of sales variation.

---

### Simple Regression Model 2

#### Model Equation

- monthly_sales = 375707.53 + 38.6639(footfall)

#### Coefficient Explanation

| Component | Statistical Meaning | Business Meaning |
|---|---|---|
| Intercept (375707.53) | Expected sales when footfall is zero. | Represents baseline sales before customer traffic effects are considered. |
| Footfall Coefficient (38.6639) | Sales increase by approximately 38.66 units for every additional customer visit. | Customer traffic is a major driver of store sales. |

#### Business Interpretation

- Footfall has a strong positive relationship with sales.
- Stores with higher customer traffic tend to generate higher revenue.
- Footfall is a stronger predictor of sales than marketing spend when evaluated individually.

---

### Multiple Regression Model

#### Model Equation

- monthly_sales = 387123.6029 + 1.1254(marketing_spend) + 29.3757(footfall) + 2154.8730(staff_count) + 10408.0025(holiday_flag)

---

### Coefficient Explanation

| Variable | Coefficient | Statistical Meaning | Business Meaning |
|---|---:|---|---|
| marketing_spend | 1.1254 | Sales increase by 1.1254 units for every additional unit of marketing spend while holding other variables constant. | Marketing investment contributes positively to sales growth. |
| footfall | 29.3757 | Sales increase by 29.38 units for every additional customer visit while holding other variables constant. | Customer traffic is one of the strongest drivers of revenue. |
| staff_count | 2154.8730 | Sales increase by approximately 2,154.87 units for each additional staff member while holding other variables constant. | Adequate staffing may improve customer service and sales performance. |
| holiday_flag | 10408.0025 | Holiday periods are associated with approximately 10,408 additional sales units compared with non-holiday periods. | Sales tend to increase during holiday periods due to higher customer demand. |

---

### Intercept Explanation

| Component | Statistical Meaning | Business Meaning |
|---|---|---|
| Intercept (387123.6029) | Predicted sales when all independent variables are zero. | Represents the baseline sales level before considering marketing, traffic, staffing, and holiday effects. |

---

### Dummy Variable Explanation

#### Dummy Variable Used

| Variable | Type |
|---|---|
| holiday_flag | Dummy Variable |

#### Coding Scheme

| Value | Meaning |
|---|---|
| 0 | Non-Holiday Period |
| 1 | Holiday Period |

#### Reference Category

- Non-Holiday Period (`holiday_flag = 0`)

#### Interpretation

- The coefficient of 10408.0025 represents the expected difference in sales between holiday and non-holiday periods.
- Stores are expected to generate approximately 10,408 additional sales units during holiday periods compared with non-holiday periods.

---

### Final Model Selected

| Model | R-Squared |
|---|---:|
| Simple Regression 1 (marketing_spend) | 0.1672 |
| Simple Regression 2 (footfall) | 0.7363 |
| Multiple Regression | 0.7848 |

#### Selected Model

- Multiple Regression Model

---

### Reason for Selecting the Final Model

#### Statistical Reasons

- Highest R-Squared value (0.7848).
- Explains approximately 78.48% of the variation in monthly sales.
- Incorporates multiple business drivers simultaneously.
- Provides better predictive performance than either simple regression model.

#### Business Reasons

- Reflects real-world business conditions more accurately.
- Considers marketing investment, customer traffic, staffing levels, and holiday effects together.
- Supports more informed decision-making.
- Helps management understand the combined impact of multiple operational factors on sales performance.

---

### Final Business Recommendation

- Focus on increasing customer footfall, as it is the strongest sales driver.
- Continue investing in marketing activities that attract customers to stores.
- Maintain appropriate staffing levels to support customer demand.
- Plan inventory and promotional activities around holiday periods.
- Use the Multiple Regression Model for future sales forecasting and business planning.


---