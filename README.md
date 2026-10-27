# \## Model Evaluation Results

# 

# Five regression algorithms were evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), R² score, and training time.

# 

# | Model | MAE | RMSE | R² Score | Training Time (s) |

# |---|---:|---:|---:|---:|

# | Linear Regression | $3,164.20 | $6,285.51 | 0.93 | 2.86 |

# | Ridge Regression | $3,223.53 | $6,443.48 | 0.93 | 1.35 |

# | Random Forest | $9,981.32 | $16,441.75 | 0.52 | 23.62 |

# | Decision Tree | $9,804.80 | $17,020.37 | 0.49 | 0.99 |

# | Extra Trees | $10,102.83 | $17,075.93 | 0.49 | 24.39 |

# 

# \*\*Best model by RMSE: Linear Regression\*\*

# 

# Linear Regression achieved the lowest MAE and RMSE among the evaluated models, with an R² score of approximately 0.93. It was selected as the final model based on the evaluation results.

# 

# \### Evaluation Methodology

# 

# A group-based 80:20 train-test split was used to keep identical feature combinations from appearing in both sets. The target variable was annual salary (`annual`), and salary-related features that could cause target leakage, such as `hrly\_rate` and `monthly`, were excluded.

# 

# These metrics represent performance on the held-out test set. They do not guarantee accuracy for every employee or for future salary data.

# 

# \### Limitations

# 

# \- Salary predictions may have substantial errors for individual employees.

# \- Performance on future years or unseen employee groups requires further validation.

# \- Results depend on the available features, data quality, and salary distribution.

# 

