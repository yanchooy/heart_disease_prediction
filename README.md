# Predicting Heart Disease

Assuming that we are working for an R&D company that focuses on providing healthcare solutions. The company has collected anonymized data from multiple hospitals on several patients. The [dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction) with 918 records and 12 features include relevant information for each patient, such as their personal information and some medical data, including whether or not they have had heart disease before.

# Goal
To find the best performing classification model to accurately predict the likelihood of a new patient having heart disease in the future 

# Results
There were **14 features used with 854 entries** after data cleaning and data-preprocessing.

### Best Performing
- We see that `K Nearest Neighbours` consistently performed well (based on best score) in various types of train-test splits and cross-validation, including optimising with PCA.
- The highest score attained by `K Nearest Neighbors` is **91.8%** through train_test_split with PCA optimisation.
- `Train_test_split` method generally gives a higher score than cross-validation

### Worst Performing
- `Random Forest` appears to be the least performing model when it comes to PCA optimisation, although the highest score attained at 88.3% is still a good score.
- `Logistic Regression` which is the simplest model here, is on par with `SVM`'s performance and both are close seconds to `KNeighbors` across all training exercises.
- **Data Linearity & Complexity**: This suggests that the underlying pattern of the dataset although non-linear, may not be complex enough for Random forest to introduce unnecessary intricate relationships.
- **Data Size**: The dataset is also relatively small with only 800+ entries (after data cleaning), which means an ensemble model like Random Forest may overfit whereas a simpler model like `KNeighbors` performs better. 

# Steps taken
1) Numerical columns EDA, checking data distribution, detecting null and outlier data
2) Numerical columns data cleaning - imputing null values with median (for `Cholesterol`) and removing outliers using modified z-score
3) Categorical columns EDA, initial descriptive observations for likelihood of heart disease.
4) Categorical columns - data preprocessing to convert to numerics using dummy variables, resulting in 15 features
5) Correlation check for highly correlated features that may not be necessary in the training.
6) Data distribution study to find obvious linearity if any
7) Data preprocessing with min max scaling for numerical columns
8) Checking for feature importances through
   - sklearn feature_importances_ attribute for Random Forest Classifier
   - sklearn coef_ (coefficients) comparison for SVM and Logistic Regression
   - sklearn SelectKBest method for KNearestNeighbours
9) Dropped one feature to reduce dimensionality - 14 features left and 854 entries.
7) GridSearchCV for 4 above models, selects best score parameters
8) PCA optimisation for 4 models on GridSearchCV parameters, using for loop through various number of PCA components for optimum number of 8 components
9) Using train_test_split method for training 4 models, using for loop through various test size for optimum test size number
10) PCA optimisation for train_test_split method, using for loop through various number of PCA components for optimum number of 4 components
11) Results comparison using best scores across all 4 training exercises using table highlighting max and min values.
