# House Prices Prediction — Model Comparison

This project explores the Kaggle House Prices dataset and builds several regression models to predict house sale prices.

The goal is to practice an end-to-end machine learning workflow, including data cleaning, feature engineering, preprocessing pipelines, and model evaluation.


## Project Workflow

The project follows a typical data science workflow:
	1.	Exploratory Data Analysis (EDA)
	2.	Data Cleaning
	3.	Feature Engineering
	4.	Preprocessing Pipeline
	5.	Model Training
	6.	Model Evaluation
	7.	Kaggle Submission


  ## Dataset

Dataset from Kaggle:

House Prices – Advanced Regression Techniques

The dataset contains 79 explanatory variables describing different aspects of residential homes.

Target variable: `SalePric`


## Exploratory Data Analysis

EDA includes:
	•	Distribution analysis of the target variable
	•	Correlation heatmap of numerical features

Key observation:
	•	SalePrice is right skewed
	•	Several features show moderate correlation with the target variable


## Feature Engineering

Several engineered features were created to improve model performance:

| Feature | Description |
|--------|--------|
| TotalSF | Total finished area |
| HouseAge | Age of the house at sale |
| RemodAge | Years since last remodel |
| Bathrooms | Full baths + 0.5

These features provide additional information for the models.


## Data Preprocessing

A scikit-learn Pipeline is used to ensure reproducible preprocessing.

Numerical features
	•	Median imputation
	•	Standard scaling

Categorical features
	•	Most frequent imputation
	•	One-hot encoding

This preprocessing is implemented using a ColumnTransformer.


## Models Compared

Several regression models were trained and compared.

Models included:
	•	Linear Regression (Baseline)
	•	Ridge Regression
	•	LassoCV
	•	Gradient Boosting Regressor
	•	Random Forest Regressor


 ## Model Evaluation

Models were evaluated using 5 fold Cross Validation.

Metric used:
`RMSE (Root Mean Squared Error)`

| Model | CV RMSE |
|------|------|
| Baseline Linear Regression | very unstable |
| Ridge Regression | ~35,237 |
| LassoCV | ~38,415 |
| Random Forest | ~29,464 |
| Gradient Boosting | ~27,775 |

Gradient Boosting achieved the best cross-validated performance.


## Final Model Performance

Random Forest was additionally evaluated on a hold-out test split.

Metrics:
`R² Score`: 0.887
`RMSE`: 29,427

## Kaggle Submission

The best model (Gradient Boosting) was trained on the full training dataset and used to generate predictions for the test set.

A submission file was created:
`submission.csv`

## Technologies Used
	•	Python
	•	Pandas
	•	NumPy
	•	Scikit-learn
	•	Matplotlib
	•	Seaborn


### Learning Objective
This project was created as part of my data science & AI learning journey to practice building a complete machine learning regression pipeline.
