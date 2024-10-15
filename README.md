# Loan-Default-Prediction
## Summary
Machine learning using `sklearn` models used for loan repayment prediciton for the next month given the (defaulter) status of the previous 12 months. The best model found using `sklearn` predicition and metrics was found to be the `RandomForestCLassifier()` model.

I completed this project independantly over a week with the guidance of the supervisor, during which we would break off into groups and also discuss our different solutions. I really enjoyed these sessions, and although it was challenging for me, I enjoyed the learning process!

## The Problem
Loan default prediction is one of the most critical and crucial problems faced by financial institutions and organizations as it has a noteworthy effect on the profitability of these institutions. In recent years, there is a tremendous increase in the volume of non–performing loans which results in a jeopardizing effect on the growth of these institutions.

Therefore, to maintain a healthy portfolio, banks put stringent monitoring and evaluation measures in place to ensure the timely repayment of loans by borrowers. Despite these measures, a major proportion of loans become delinquent. Delinquency occurs when a borrower misses a payment against his/her loan.

Given the information like mortgage details, borrowers-related details, and payment details, your objective is to build a system that can predict the defaulter status of loans for the next month given the defaulter status for the previous 12 months (in the number of months).

## Loading and Exploring the data set
First the data is loaded in using `pandas`. Missing value analysis is undertaken where columns with over 30% missing data was either dropped or impouted (using `sklearn.impute.KNNImputer` and `knn.fit_transform`)

## Exploratory Data Analysis
- Categorical and continuous columns were differentiated such that appropriate visualiastions could be made. 
- Visualisations were made using `plotly` and `matplotlib`. 
- Boxplots were used to identify outliers.

## Feature selection, encoding and scaling
- `scipy.stats.chi2_contingency` was used to evaluate and remove highly correlated categorical features; using `pandas.DataFrame.corr()` continuous features were visualised using `plotly.express.imshow` to create a heatmap such that highly correlated continous variables could be identified and removed.

- One-hot encoding was used for nominal variables using `pandas.get_dummies()` 

- Normalisation was used for feature scaling using `sklearn.preprocessing.MinMaxScaler()` and fit_transform functions.

## Train Test Split and model training
The data was split into different sets: training set, testing set, and valuation set.
`sklearn` models were trained on the data set including:
- `ensemble`
  - `RandomForestClassifier`, 
  - `GradientBoostingClassifier`, 
  - `ExtraTreesClassifier`
- `linear_model.LogisticRegression`
- `svm.SVC`
- `neighbours.KNeighborsClassifier`

## Model evaluation
Functions from `sklearn.metrics` such as `accuracy_score`, `precision_recall_fscore_support`. 
The scores between the models were compared, and the model with the "best_score" (which in this case was the RandomForestCLassifier) was chosen as the "best_model".


