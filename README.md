# Problem Statement: Insurance Claim Prediction

In this project, the goal is to build a classification model that can accurately predict whether an individual is likely to make an insurance claim based on various demographic and medical factors. The dataset contains information about individuals' age, BMI, number of children, smoking habits, region, and insurance charges. The objective is to develop a model that can help insurance companies assess the risk of potential claims and make informed decisions about coverage and pricing.

# Data Description
This dataset contains information on the insurance claim. each observation is different
policyholder with various features like the age of the person, the gender of the policyholder,
body mass index, providing an understanding of the body, number of children of the
policyholder, smoking state of the policyholder and individual medical costs billed by health
insurance.
|Feature| Description|
|------|--------------|
|age| age of policyholder|
|sex| male(1)/female(0)|
|bmi| body mass index(kg / m2)|
|children |number of children/dependents of policyholder|
|smoker| smoking state nonsmoker(0)/smoker(1)|
|region| residential area northeast(0)/northwest(1)/southeast(2)/southwest(3)|
|charges| medical cost|
|insuranceclaim| yes(1)/no(0)|
---------------------------------
# Model Building Report

### `Introduction`

In this model building project, the goal was to develop a classification model to predict insurance claim outcomes based on various features. We trained and evaluated multiple classification algorithms using training and test datasets. The report provides a comprehensive overview of the model building process, performance evaluation, and the final selected model.

### `Data Overview`

The dataset contains 1338 observations and 8 variables, with no missing values and correct data types. After removing one duplicate observation, the data was ready for further analysis.

### `Exploratory Data Analysis (EDA)`
EDA revealed several insights about the dataset:

* Most people's ages fall between 18 and 51 years.


* About 50% of people have one child, and 25% have two children.


* The majority of people are non-smokers and have claimed insurance.


* The correlation analysis indicated a slightly high positive correlation between 'Charges' and 'Smoker', indicating higher insurance charges for smokers.


* Outliers were detected using the Z-Score method, and 29 outliers were removed, accounting for approximately 2% data loss.


### `Model Selection`

We trained various classification algorithms on the training data and evaluated their performance on both training and test sets. Among the models, the Gradient Boosting Classifier exhibited the best performance without overfitting, making it the final chosen model.

### `Hyperparameter Tuning`

We performed hyperparameter tuning on the selected Gradient Boosting model to optimize its performance. The best model achieved an impressive test accuracy of 0.9924.

### `Model Evaluation`

The final Gradient Boosting Classifier was evaluated on both the training and test datasets:

**Evaluation Metrics on Training & Test Data:**

|Metric|Training Data|Test Data|
|--------|---------|--------|
|Accuracy|0.9924| 0.9771|
|Precision| 0.9943|1.0000|
|Recall| 0.9924|0.9627|
|F1-score| 0.9933|0.9809|
|Balanced Accuracy| 0.9923|0.9813|


The model demonstrated excellent performance on both datasets, with high accuracy, precision, recall, and F1-score. The balanced accuracy showed that the model effectively classified both classes without bias.

### `Threshold Selection`
Default threshold (0.5) was found to be suitable for the model.

### `Confusion Matrix`
The confusion matrix results on the training set and test set:

|Elements|Training Data|Test Data| 
|---------|-------------|----|
|True Positive| 57.05%|59.03%|
|True Negative|42.19%|38.68%|
|False Positive| 0.33%|0.00%|
|False Negative| 0.44%|2.29%|

### `ROC-AUC Curve`

The ROC-AUC curve for both training and test data resulted in an AUC of 1.00, indicating excellent model performance in distinguishing between the classes.

### `Cross-Validation`
Cross-validation was performed, and the model achieved consistent F1 scores of approximately 0.96 on average, indicating robust and reliable performance.

### `Feature Importance`
Feature Importance analysis revealed that 'BMI', 'Children', and 'Charges' are the most significant variables, contributing to around 78.32% of the variance in the target variable.

### `Conclusion`
The Gradient Boosting Classifier proved to be the best model for the insurance claim prediction task, demonstrating outstanding performance on both training and test datasets. Its ability to generalize and handle class imbalances makes it a reliable model for real-world predictions. The feature importance analysis provided valuable insights into the factors influencing insurance claim outcomes. The saved model will be useful for making predictions on new data in the future.
