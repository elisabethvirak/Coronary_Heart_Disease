# Coronary Heart Disease

![](https://www.mddionline.com/sites/mddionline.com/files/styles/article_featured_retina/public/images/mddi/heart-coronary-artery_YODIYIM_FREEDIGITALPHOTOS.jpg?itok=Z1smz2p2)

### Why Coronary Heart Disease?
About 1 in every 4 deaths each year are caused by heart disease. Coronary Heart Disease is the most common type of heart disease, causing over half the heart disease deaths in 2017.
Looking for comorbid factors and being able to predict heart disease in patients could help doctors prevent its occurrence and could lower these statistics. 

Using a dataset containing 4,000 records from Framingham, Massachusetts, we examined common factors used to predict heart disease to create a machine learning model that would predict the likeliness of developing Coronary Heart Disease in the next 10 years.

We used the following tools:
- Python:
  - SciKit Learn
  - joblib
  - Pandas
  - Matplotlib
  - Numpy
  
### INSTRUCTIONS FOR USE

Python Depedencies:
  - sklearn
  - joblib
  - pandas
  - matplotlib.pyplot
  - numpy
  - os
  
### METHODS

1. Exploration
> Data was explored to find correlations between factors provided. While systolic and diastolic blood pressure were correlated, no other factors provided showed strong correlations.
> We found that the dataset was imbalanced in favor of those who were not at risk for heart disease.

2. Models
> Logistic Regression:
  - Initially, the logistic regression model was overfit to our training data set. This was adjusted by changing class weight to balanced.
    - Training Data Score: 0.65
    - Testing Data Score: 0.62
  - Grid Search was completed using C and Penalty as parameters:
    - Best fit model used a C of 10 and Penalty l2.
    - Score was 0.63.  
> Random Forest
>> First Random Forest:
   - Original Training Data Score: 0.99
   - Original Testing Data Score: 0.84
   - Recall score was only 3%
   - Completed a Grid Search using max_depth and min_samples_leaf
     - Best fit model used max_depth of 7 and min_samples_leaf of 4
     - Score was 0.85
     - Finding risk, precision was 0.50 and recall was 0.03
>> Second Random Forest
   - For the second random forest, we changed the class_weight to balanced
   - Original Training Score: 0.998
   - Original Testing Score: 0.85
   - For the Grid Search, we changed the max_depth to 5.
     - Best fit model chose min_samples_leaf of 1.
     - Score was 0.71
     - Finding risk, precision was 0.27 and recall was 0.66
   
### FINDINGS
Recall score was the most important, because it is better to over-diagnose risk than under-diagnose, so the best fit model for predicting a risk of Coronary Heart Disease required lowering the overall accuracy score to create a less complex model.

#### CREDIT TO:
Kaggle for the dataset: https://www.kaggle.com/dileep070/heart-disease-prediction-using-logistic-regression
