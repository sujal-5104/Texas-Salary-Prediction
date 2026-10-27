# Texas Employee Salary Prediction

## Project Overview

The **Texas Employee Salary Prediction** project analyzes Texas public-sector employee salary data using Python, data visualization, and machine learning. It explores salary distributions, differences across government agencies and job classifications, demographic patterns, and employment-related information.

The project also trains and compares multiple regression models to predict annual salaries using selected job-related and employment features.

## Objectives

- Perform data cleaning and preprocessing.
- Conduct Exploratory Data Analysis (EDA).
- Analyze salary distributions and identify potential outliers.
- Compare salary patterns across agencies, job titles, gender, ethnicity, and employment status.
- Train and evaluate multiple machine learning regression models.
- Select, save, and test the best-performing model.
- Document findings, limitations, and possible improvements.

## Technologies Used

- **Programming Language:** Python
- **Environment:** Jupyter Notebook
- **Data Analysis:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn
- **Model Serialization:** Pickle

## Dataset Information

The dataset contains **149,481 employee salary records** and 21 original columns. It includes information such as agency, job classification, employment status, working hours, monthly salary, annual salary, and demographic attributes.

The target variable is `annual`, representing annual salary.

The `salary.csv` dataset is not included in this repository because of its file size. You must obtain the dataset separately and place it in the project directory to run the notebook from the beginning.

## Project Structure

```text
Texas-Salary-Prediction/
│
├── Texas_Employee_Salary_Prediction.ipynb
├── texas_salary_model.pkl
├── texas_salary_model_comparison.csv
├── requirements.txt
├── README.md
└── .gitignore
```

## Exploratory Data Analysis

The notebook explores:

- Annual salary statistics, including mean, median, minimum, and maximum.
- Salary distributions using histograms and boxplots.
- Salary comparisons across agencies and job titles.
- Descriptive salary comparisons by gender and ethnicity.
- Employment status and working hours.
- Potential salary outliers using the Interquartile Range (IQR) method.
- Employee hire-year patterns, where the available employment-date data permits analysis.

The IQR method identified **9,031 potential salary outliers**. These observations were flagged for investigation and were not automatically classified as errors.

## Machine Learning Workflow

The machine learning pipeline includes:

1. Feature selection and target preparation.
2. Group-based train-test splitting using an 80:20 ratio.
3. Missing-value imputation.
4. Numerical feature scaling.
5. One-hot encoding of categorical features.
6. Training and comparison of five regression models.
7. Evaluation using MAE, RMSE, and R².
8. Saving and testing the selected model.

The input features include agency, agency name, job title, class code, ethnicity, gender, employment status, and hours worked per week.

Monthly salary and hourly rate were excluded from the selected features to reduce the risk of target leakage when predicting annual salary.

## Model Performance

Five regression models were evaluated on the held-out test set.

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Linear Regression | $3,164.20 | $6,285.51 | 0.93 |
| Ridge Regression | $3,223.53 | $6,443.48 | 0.93 |
| Decision Tree | $9,804.80 | $17,020.37 | 0.49 |
| Random Forest | $9,981.32 | $16,441.75 | 0.52 |
| Extra Trees | $10,102.83 | $17,075.93 | 0.49 |

### Best Model: Linear Regression

Linear Regression achieved the lowest Mean Absolute Error and Root Mean Squared Error among the five evaluated models. Its R² score was approximately **0.9303**.

- **MAE:** $3,164.20
- **RMSE:** $6,285.51
- **R² Score:** 0.9303

MAE represents the average absolute prediction error. RMSE penalizes larger errors more heavily, while R² measures the proportion of target variation explained by the model on the test set.

These results describe performance on this particular test split and do not guarantee the same accuracy on new data.

## Model Saving

The selected model was saved using Python's Pickle module.

- `texas_salary_model.pkl` — trained preprocessing and prediction pipeline.
- `texas_salary_model_comparison.csv` — comparison results for the evaluated models.

The saved pipeline can be loaded to generate predictions from input data containing the expected feature columns.

## Key Findings

- The dataset contains a wide range of annual salary values across agencies and job classifications.
- Average salary and employee counts vary across agencies.
- Descriptive salary differences appear across demographic groups; these comparisons do not establish their causes.
- The IQR method identifies records that may require additional review.
- Linear Regression performed better than the other tested models according to MAE and RMSE.

## Limitations

- Individual salary predictions can have substantial errors.
- The model produced some negative salary predictions, which are not realistic and indicate a limitation of the current approach.
- The group-based split prevents identical input-feature combinations from crossing between training and test sets, but it does not measure performance on future years.
- Employment dates indicate hire dates and cannot independently establish year-over-year salary changes.
- The available fields may not support reliable manager-versus-employee or total-compensation comparisons.
- Demographic salary comparisons are descriptive and should not be interpreted as causal conclusions.
- Model performance may change with new data, different employee groups, or changes in salary structures.

## Installation and Usage

### 1. Clone the repository

```bash
git clone https://github.com/sujal-5104/Texas-Salary-Prediction.git
cd Texas-Salary-Prediction
```

### 2. Install dependencies

Make sure Python is installed, then run:

```bash
pip install -r requirements.txt
```

### 3. Add the dataset

Place the required `salary.csv` file in the project directory.

### 4. Open the notebook

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open `Texas_Employee_Salary_Prediction.ipynb` and run the cells in order.

## Future Improvements

- Evaluate the model on newer payroll records.
- Investigate negative predictions and large individual prediction errors.
- Explore additional regression algorithms and hyperparameter tuning.
- Obtain reliable historical payroll data for time-based analysis.
- Include validated management-level and total-compensation fields if available.
- Monitor model performance and retrain when representative new data becomes available.

## Disclaimer

This project is intended for educational and analytical purposes. The predictions and findings should not be used as the sole basis for employment, compensation, or other consequential decisions.
