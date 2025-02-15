# Credit Card Customer Churn Prediction

## Technologies Used

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.0%2B-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.18%2B-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-0.24%2B-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.3%2B-11557c?style=for-the-badge&logo=python&logoColor=white)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.11%2B-76b900?style=for-the-badge&logo=python&logoColor=white)](https://seaborn.pydata.org/)
[![LightGBM](https://img.shields.io/badge/LightGBM-3.2%2B-2980b9?style=for-the-badge&logo=microsoft&logoColor=white)](https://lightgbm.readthedocs.io/)
[![Jupyter](https://img.shields.io/badge/Jupyter-6.1%2B-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)


## Project Overview
This project implements a machine learning-based system to predict customer churn for a financial institution's credit card business. Customer churn, or attrition, is a critical challenge faced by financial companies. The ability to predict and understand factors contributing to customer attrition can significantly impact the profitability and success of a financial entity.

## Problem Statement
The main objectives of this project are:
1. Analyze and understand the factors contributing to customer churn in credit card services.
2. Develop predictive models to identify customers at risk of churning.
3. Provide insights and recommendations for customer retention strategies.

## Dataset
The dataset contains demographic attributes of customers, as well as information related to their credit cards, including:
- Customer age, gender, and dependent count
- Education level and marital status
- Income category
- Card category and credit limit
- Transaction history and account activity

## Technologies Used
- **Python**: Primary programming language
- **Data Manipulation**: Pandas, NumPy
- **Machine Learning**: Scikit-learn, LightGBM
- **Data Visualization**: Matplotlib, Seaborn
- **Development Environment**: Jupyter Notebooks

## Project Structure
The project follows a structured data science approach:

1. **Data Acquisition**: Extraction and importation of the dataset
2. **Data Preprocessing and Cleaning**
3. **Exploratory Data Analysis (EDA)**
4. **Feature Engineering**
5. **Data Preparation for Modeling**
6. **Model Selection and Training**
7. **Model Evaluation**
8. **Insights and Visualization**

## Data Preprocessing and Cleaning

### Handling Missing Values
- Identified and counted null values and 'Unknown' entries
- Filled missing values in `Income_Category` with mode
- Replaced 'Unknown' in `Education_Level` with a separate category

### Encoding Categorical Variables
- Used **Label Encoding** for `Card_Category` and `Education_Level`
- Applied **One-Hot Encoding** for `Gender`

### Removing Unnecessary Columns
- Dropped `CLIENTNUM`, `Marital_Status`, and other non-predictive columns

### Handling Outliers
- Used **Interquartile Range (IQR)** method to detect and remove outliers in:
  - `Contacts_Count_12_mon`
  - `Total_Trans_Ct`
  - `Months_on_book`
- Applied custom threshold for `Total_Ct_Chng_Q4_Q1`

### Feature Scaling
- Applied `StandardScaler` to normalize numerical features

### Dimensionality Reduction
- Used **Principal Component Analysis (PCA)** for exploratory analysis and potential feature reduction

## Key Features
1. **Comprehensive EDA**: Thorough analysis of customer attributes and their relationship with churn.
2. **Multiple Model Comparison**: Implementation and comparison of various machine learning algorithms.
3. **Advanced Model Tuning**: Utilization of `GridSearchCV` for optimal hyperparameter selection.
4. **Robust Evaluation**: Implementation of 5-fold cross-validation for reliable model assessment.
5. **Feature Importance Analysis**: Identification of key factors influencing customer churn.
6. **Actionable Insights**: Generation of insights to inform customer retention strategies.

## Machine Learning Highlights

### Cross-Validation
- **Stratified K-Fold** was implemented to ensure robustness and validate overfitting models.

### Hyperparameter Tuning
- Utilized `GridSearchCV` to find the optimal combination of hyperparameters for the LightGBM model.

### Model Optimization
- Employed `force_col_wise=True` in LightGBM to optimize processing time without compromising performance.

### Performance Metrics
- Achieved high accuracy (97.01%) with low standard deviation (0.25%) across cross-validation folds, indicating stable and consistent model performance.

## Model Performance
The **LightGBM model**, after hyperparameter tuning and cross-validation, demonstrated excellent performance:
- **Average Accuracy**: 97.01%
- **Standard Deviation**: 0.25%
- High precision, recall, F1-score, and ROC AUC for both churn and non-churn classes

## Contributing
Contributions to this project are welcome. Please fork the repository and submit a pull request with your proposed changes.

## License
This project is open-source and available under the MIT License.
