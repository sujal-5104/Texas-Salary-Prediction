# Texas-Salary-Prediction
Machine learning project to analyze Texas public-sector payroll data and predict annual salaries using regression models. Copy description
## Model Evaluation Results

Five regression algorithms were evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), R² score, and training time.

| Model | MAE | RMSE | R² Score | Training Time (s) |
|---|---:|---:|---:|---:|
| Linear Regression | 0.10 | 0.23 | 1.00 | 4.43 |
| Random Forest | 9.51 | 996.70 | 1.00 | 626.19 |
| Decision Tree | 11.17 | 1,056.76 | 1.00 | 50.21 |
| Ridge Regression | 20.97 | 30.97 | 1.00 | 2.27 |
| Extra Trees | 85.31 | 1,241.86 | 1.00 | 171.01 |

**Best model reported:** Linear Regression

Linear Regression produced the lowest reported MAE and RMSE and had the shortest training time among the tree-based models. However, the near-perfect R² scores and extremely low Linear Regression errors require further validation before these results can be considered reliable.

The metrics should be confirmed against the original annual salary values, with particular attention to target leakage, preprocessing, and the units of the target variable.

