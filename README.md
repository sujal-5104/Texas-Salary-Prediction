# Texas Employee Salary Prediction

## Project Overview

The **Texas Employee Salary Prediction** project uses machine learning to predict annual employee salaries based on selected employment-related features. The project explores salary data, performs data preprocessing and exploratory data analysis (EDA), trains multiple regression models, and compares their performance to identify the best-performing model.

## Objectives

- Analyze Texas employee salary data.
- Perform data cleaning and exploratory data analysis.
- Prepare numerical and categorical features for machine learning.
- Train and compare multiple regression algorithms.
- Evaluate models using MAE, RMSE, and R².
- Save the best-performing model for future predictions.

## Dataset

The project uses a dataset containing approximately **149,481 records and 21 original columns**.

**Target variable**
- `annual` — annual employee salary.

**Selected features**
- `agency`
- `agency_name`
- `class_title`
- `class_code`
- `ethnicity`
- `gender`
- `status`
- `hrs_per_wk`

Salary-related variables that could leak information about the target were excluded from the selected input features.

**Note:** The original `salary.csv` dataset is not included in this repository because of its file size. You must obtain the dataset separately and place it in the appropriate project directory before running the notebook.

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Pickle

## Machine Learning Workflow

1. Load and inspect the dataset.
2. Clean and prepare the data.
3. Perform exploratory data analysis.
4. Select input features and the target variable.
5. Split the data into training and testing sets using `GroupShuffleSplit`.
6. Preprocess numerical and categorical features.
7. Train and compare regression models.
8. Evaluate model performance.
9. Select the best-performing model.
10. Save the trained model for future use.

## Models Compared

- Linear Regression
- Ridge Regression
- Decision Tree Regressor
- Random Forest Regressor
- Extra Trees Regressor

## Model Performance

The following results were obtained during model evaluation:

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Linear Regression | 3,164.20 | 6,285.51 | 0.9303 |
| Ridge Regression | 3,223.53 | 6,443.48 | 0.9268 |
| Decision Tree | 9,804.80 | 17,020.37 | 0.4892 |
| Random Forest | 9,981.32 | 16,441.75 | 0.5233 |
| Extra Trees | 10,102.83 | 17,075.93 | 0.4858 |

**Best-performing model: Linear Regression**

- MAE: approximately $3,164.20
- RMSE: approximately $6,285.51
- R² Score: approximately 0.9303

Based on these evaluation results, Linear Regression achieved the lowest MAE and RMSE and the highest R² score among the compared models.

## Saved Model

The selected model is saved as:

`texas_salary_model.pkl`

The model can be loaded using Python's `pickle` module, provided that the required dependencies and compatible preprocessing pipeline are available.

**Important:** Only load pickle files from trusted sources.

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

The dataset file `salary.csv` is excluded from the repository.

## Installation and Usage

### 1. Clone the repository

```bash
git clone https://github.com/sujal-5104/Texas-Salary-Prediction.git
cd Texas-Salary-Prediction
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the dataset

Obtain the original `salary.csv` dataset and place it in the location expected by the notebook. Update the file path in the notebook if necessary.

### 5. Run the notebook

```bash
jupyter notebook Texas_Employee_Salary_Prediction.ipynb
```

Run the notebook cells in order to reproduce the analysis and model evaluation.

## Limitations

- The dataset is not included in the repository.
- Predictions may contain substantial errors for individual employees.
- A high R² score does not guarantee accurate predictions for every record.
- Salary patterns may change over time and across agencies or job classifications.
- Demographic relationships in the data should not be interpreted as causal explanations or used alone for employment decisions.
- The model is intended for educational and analytical purposes, not as the sole basis for real-world compensation decisions.

## Future Improvements

- Test additional regression algorithms and hyperparameter tuning.
- Perform more detailed residual and error analysis.
- Validate performance on newer or independent data.
- Develop a user-friendly web application for predictions.
- Improve model monitoring and reproducibility.

## Author

**Sujal Padhiyar**

GitHub: [@sujal-5104](https://github.com/sujal-5104)

## Disclaimer

This project is developed for learning and demonstration purposes. Predictions are estimates based on historical data and should not be treated as guaranteed salary values or professional compensation advice.
