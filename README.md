# Texas Employee Salary Prediction

## Project Overview

This project analyzes Texas public-sector employee salary data and develops machine learning models to predict annual salary using employment and job-related features.

The notebook includes data cleaning, exploratory data analysis (EDA), salary outlier analysis, demographic comparisons, agency and job-title analysis, model training, evaluation, and model saving.

## Objectives

- Explore salary distributions and workforce patterns.
- Compare salaries across agencies, job titles, gender, ethnicity, and employment status.
- Identify potential salary outliers for further investigation.
- Train and compare multiple regression models.
- Evaluate and save the best-performing model.

## Technologies Used

- Python
- Jupyter Notebook
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Pickle

## Project Structure

```text
Texas-Salary-Prediction/
├── Texas_Employee_Salary_Prediction.ipynb
├── texas_salary_model.pkl
├── texas_salary_model_comparison.csv
├── requirements.txt
├── README.md
└── .gitignore
```

**Dataset:** `salary.csv` is not included in the repository because of its size. Place the dataset in the project directory before running the notebook.

## Model Evaluation Results

Five regression models were compared using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), R² score, and training time.

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Linear Regression | $3,164.20 | $6,285.51 | 0.93 |
| Ridge Regression | $3,223.53 | $6,443.48 | 0.93 |
| Decision Tree | $9,804.80 | $17,020.37 | 0.49 |
| Random Forest | $9,981.32 | $16,441.75 | 0.52 |
| Extra Trees | $10,102.83 | $17,075.93 | 0.49 |

Linear Regression achieved the lowest MAE and RMSE among the tested models and was selected as the final model.

### Evaluation Methodology

A group-based 80:20 train-test split was used to prevent identical combinations of input features from appearing in both training and test sets. The target variable is `annual`.

Features such as `monthly` and `hrly_rate` were excluded to reduce target leakage. Numerical and categorical features were processed using a scikit-learn pipeline with imputation, scaling, and one-hot encoding.

### Limitations

- The reported metrics apply to the held-out test set and do not guarantee accuracy for individual employees.
- The largest observed individual prediction error was substantial.
- Linear Regression produced some negative predictions, which are not realistic salaries and indicate a limitation of the model.
- The group-based split does not establish performance on future years.
- Demographic salary differences are descriptive and do not establish causation.
- Employment dates alone cannot establish historical salary changes.
- The available data may not support reliable manager-versus-employee or total-compensation comparisons.

## Key Findings

- The dataset contains 149,481 salary records used in model preparation.
- Salary patterns vary across agencies, job titles, and employee groups.
- The IQR method flagged 9,031 potential salary outliers. These records should be investigated rather than automatically removed.
- Linear Regression performed better than the other evaluated models on MAE and RMSE.

## How to Run

1. Clone or download this repository.
2. Place `salary.csv` in the project directory.
3. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Open `Texas_Employee_Salary_Prediction.ipynb` in Jupyter Notebook.
5. Run the notebook cells in order.

## Future Improvements

- Validate the model on newer payroll data.
- Investigate negative predictions and large individual errors.
- Tune model hyperparameters and evaluate alternative regression methods.
- Add reliable historical compensation and management-level data if available.
- Monitor model performance as new data becomes available.

## Disclaimer

This project is intended for educational and analytical purposes. Salary predictions should not be used as the sole basis for employment, compensation, or other consequential decisions.
