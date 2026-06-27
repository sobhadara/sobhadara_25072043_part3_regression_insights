# Part 3 : Regression-Based Business Insights & Model Interpretation

---

## Task 7: Residual Analysis

### Final Model Used

| Model | Variables |
|---|---|
| Multiple Regression | marketing_spend, footfall, staff_count, holiday_flag |

### Predicted Sales Calculation

#### Formula Used

- Predicted Sales = 387123.6029 + 1.1254(marketing_spend) + 29.3757(footfall) + 2154.8730(staff_count) + 10408.0025(holiday_flag)

#### Purpose

- Calculate expected monthly sales using the final regression model.
- Compare predicted sales with actual sales.

### Residual Calculation

#### Formula Used

- Residual = Actual Sales - Predicted Sales

#### Spreadsheet Formula

- `=A2-F2`

#### Interpretation

| Residual Value | Meaning |
|---|---|
| Positive | Actual sales exceeded predicted sales |
| Negative | Actual sales were lower than predicted sales |
| Near Zero | Prediction was accurate |

### Residual Squared

#### Formula Used

- `=G2^2`

#### Purpose

- Measures error magnitude.
- Prevents positive and negative residuals from cancelling each other.

### Absolute Residual

#### Formula Used

- `=ABS(G2)`

#### Purpose

- Measures the size of prediction error regardless of direction.

### Summary Statistics

| Metric | Purpose |
|---|---|
| Mean Residual | Measures overall prediction bias |
| Maximum Residual | Largest under-prediction |
| Minimum Residual | Largest over-prediction |
| Mean Absolute Residual | Average prediction error |
| Residual Standard Deviation | Variability of prediction errors |

### Top 5 Largest Positive Residuals

| Rank | Row Number | Residual |
|---|---:|---:|
| 1 | 113 | 121902.40 |
| 2 | 105 | 116080.91 |
| 3 | 299 | 110032.02 |
| 4 | 255 | 102336.13 |
| 5 | 108 | 100111.15 |

#### Interpretation

- Actual sales were higher than predicted sales.
- Model under-predicted these observations.
- Additional business factors may be influencing performance.

### Top 5 Largest Negative Residuals

| Rank | Row Number | Residual |
|---|---:|---:|
| 1 | 46 | -135692.98 |
| 2 | 34 | -128938.21 |
| 3 | 68 | -127374.42 |
| 4 | 5 | -118793.46 |
| 5 | 138 | -108561.99 |

#### Interpretation

- Actual sales were lower than predicted sales.
- Model over-predicted these observations.
- Operational or market factors may not be captured by the model.

### Residual Pattern Assessment

#### Under-Prediction Indicators

- Large positive residuals indicate sales higher than predicted.
- Model may not capture all demand drivers.

#### Over-Prediction Indicators

- Large negative residuals indicate sales lower than predicted.
- Model may not capture all operational constraints.

### Business Interpretation

- Most predictions are reasonably close to actual sales.
- The model explains 78.48% of sales variation.
- Some observations perform significantly above or below expectations.
- Additional variables may improve model accuracy.

### Conclusion

- Predicted sales were calculated using the Multiple Regression Model.
- Residuals were calculated as Actual Sales minus Predicted Sales.
- Positive residuals indicate under-prediction.
- Negative residuals indicate over-prediction.
- The model performs well overall but does not explain all sales variation.
- Additional business variables may improve future model performance.