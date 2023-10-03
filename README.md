# Predicting Heart Disease

Assuming that we are working for an R&D company that focuses on providing healthcare solutions. The company has collected anonymized data from multiple hospitals on several patients. The [dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction) with 918 records and 15 features include relevant information for each patient, such as their personal information and some medical data, including whether or not they have had heart disease before.

# Goal
To find the best performing classification model to accurately predict the likelihood of a new patient having heart disease in the future 

# Results
- We have maintained 93% (854 out of 918 rows) of our data after removing outliers using modified Z-score and imputating incorrect values.
- **Support Vector Machine (SVM)performed best with accuracy score of 84.3%**  when cross validating with 10 Stratified Kfolds.
- Using `train_test_split` with 90% training and 10% test split, **SVM's accuracy score increase to 88.3%**
- Through Principal Component Analysis, **SVM score improved to 89.5%** with an added benefit of reducing computation cost by summarising features to 5 components.
- Learning Curves also show training score and validation score converging, suggesting that we have balanced model.
