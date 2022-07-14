# Data-Analytics-for-Kaggle-Machine-Learning-Data-Science-Survey

# PART 1

## Background:

Kaggle has hosted an open data scientist competition in 2021 titled “Kaggle ML & DS Survey Challenge.” The purpose of this challenge was to “tell a data story about a subset of the data science community represented in this survey, through a combination of both narrative text and data exploration.” More information on the competition, data, and prizes can be found on: https://www.kaggle.com/c/kaggle-survey-2021/data

The dataset used (kaggle_survey_2021_responses.csv) contains the survey results provided by Kaggle. The survey results from 25973 participants are shown in 369 columns, representing survey questions. Not all questions are answered by each participant, and responses contain various data types.

In the dataset for , column Q25 “What is your current yearly compensation (approximate $USD)?” contains a numerical target variable. Rows with null salaries have been dropped. (Please refer to clean_kaggle_data.csv). 

## Questions:
The objective of this part of the project is to explore the survey data to understand (1) the nature of women’s representation in Data Science and Machine Learning and (2) the effects of education on income level. 

## Steps to perform:
1. Perform exploratory data analysis to analyze the survey dataset and to summarize its main characteristics. Present 3 graphical figures that represent different trends in the data. For explanatory data analysis, consider Country, Age, Education, Professional Experience, and Salary.

2. Estimating the difference between average salary (Q24) of men vs. women (Q2).

a. Compute and report descriptive statistics for each group (remove missing data, if
necessary).

b. If suitable, perform a two-sample t-test with a 0.05 threshold. Explain the rationale.

c. Bootstrap data for comparing the mean of salary (Q24) for the two groups. Note that the number of instances sample from each group should be relative to its size. Use 1000 replications. Plot two bootstrapped distributions (for men and women) and the distribution of the difference in means.

d. If suitable, perform a two-sample t-test with a 0.05 threshold on the bootstrapped data. Explain the rationale.

e. Comment on findings.

3. Select “highest level of formal education” (Q4) from the dataset and repeat steps a to e, this time use analysis of variance (ANOVA) instead of t-test for hypothesis testing to compare the means of salary for three groups (Bachelor’s degree, Doctoral degree, and Master’s degree)

Write a report and an ipynb file

# PART 2

In this part, we will continue to work on the “2021 Kaggle Machine Learning & Data Science
Survey” dataset.

## Background
The purpose of this challenge was to “tell a data story about a subset of the data science community represented in this survey, through a combination of both narrative text and data exploration.” More information on this competition can be found on: https://www.kaggle.com/c/kaggle-survey-2021

The dataset provided (kaggle_survey_2021_responses.csv) contains the survey results provided by Kaggle. The survey results from 25973 participants are shown in 369 columns, representing survey questions. Not all questions are answered by each participant, and responses contain various data types. In the dataset, column ‘Q25’ “What is your current yearly compensation (approximate $USD)?” contains the ordinary categorical target variable. The original data (kaggle_survey_2021_responses.csv) has been transformed to clean_kaggle_data_2021.csv as per the code given in KaggleSalary_DataSet.ipynb. In the dataset to be used for Part 2 (clean_kaggle_data_2021.csv), rows with the null values of salaries have been dropped. In addition, two columns (‘Q25_Encoded’ and ‘Q25_buckets’) have been added at the end. Column ‘Q25_buckets’ (Target Variable for Part 2) has been obtained by combining some salary buckets in the column ‘Q25’. Column ‘Q25_Encoded’ has been obtained by label encoding the column ‘Q25_buckets’.

The purpose of this part of the project is to train, validate, and tune multi-class ordinary classification models that can classify, given a set of survey responses by a data scientist, what a survey respondent’s current yearly compensation bucket is.
Classification is a supervised machine learning approach used to assign a discrete value of one variable when given the values of others. Many types of machine learning models can be used for training classification problems, such as logistic regression, decision trees, kNN, SVM, random forest, gradient- boosted decision trees, and neural networks. In this part of the project, it is required to use the ordinal logistic regression algorithm, but feel free to experiment with other algorithms.

For the purposes of this assignment, any subset of data can be used for data exploration and for classification purposes. For example, it is possible to focus only on one country, exclude features, or engineer new features. If a subset of data is chosen, it must contain at least 5000 training examples. Justification and explanation are needed on why a subset of the data are selected, and how it may affect the model.

Data is often split into training and testing data. The training data is typically further divided to create validation sets, either by just splitting, if enough data exists, or by using cross-validation within the training set. The model can be iteratively improved by tuning the hyperparameters or by feature selection.

## S

1. Data cleaning:
While the data is made ready for analysis, several values are missing, and some features are categorical. Note that some values that appear “null” indicate that a survey respondent did not select that given option from a multiple-choice list. For example – “Which of the following hosted notebook products do you use on a regular basis? (Select all that apply) - Selected Choice - Binder / JupyterHub”.

For the data cleaning step, handle missing values however you see fit and justify your approach. Provide some insight on why you think the values are missing and how your approach might impact the overall analysis. Suggestions include filling the missing values with a certain value (e.g. mode for categorical data) and completely removing the features with missing values. Another method could be filling them with a separate value showing missingness, e.g., “unknown”. Secondly, convert categorical data into numerical data by encoding and explain why used this particular encoding method.

These tasks can be done interchangeably, e.g., encoding can be done first.

2. Exploratory data analysis and feature selection:
For the exploratory data analysis step, visualize the order of feature importance. Some possible methods include correlation plot, or a similar method. Given the data, which of the original attributes in the data are most related to a survey respondent’s yearly compensation?

Explain how feature engineering is a useful tool in machine learning in the context of the tasks in this assignment. Apply feature engineering and then select the features to be used for analysis either manually or through some feature selection algorithm (e.g. regularized regression).

Not all features need to be used; features can be removed or added as desired. If the resulting number of features is very high, dimensionality reduction can also be used (e.g. PCA). Use at least one feature selection technique – describe the technique and provide justification on why selected that set of features.

3. Model implementation:
Implement ordinal logistic regression algorithm on the training data using 10-fold cross- validation. How does the model accuracy compare across the folds? What is the average and variance of accuracy for folds? Treating each value of hyperparameter(s) as a new model, which model performed best? Give the reason based on bias-variance trade-off. An output of the algorithm should be a probability of belonging to each of the salary buckets. Apply scaling/normalization of features, if necessary, and justify the reason why scaling/normalization is (not) needed.

4. Model tuning:
Identify all hyperparameters in your model. Select two hyperparameters for model tuning and justify your selection. Improve the performance of the models from the previous step with hyperparameter tuning and select a final optimal model using grid search based on a metric (or metrics) that you choose. Choosing an optimal model for a given task (comparing multiple classifiers on a specific domain) requires selecting performance measures, for example accuracy, precision, recall and/or F1-score to compare the model performance. Justify the metric you selected. There is no minimum model accuracy, as long as the methodology is reasonable and well explained.

Create the feature importance graph of the model to see which features were the most determining in model predictions. Compare this graph with the feature importance graph obtained in Section 2.

5. Testing & Discussion:
Use the optimal model to make classifications on the test set. How does the model perform on the test set vs. the training set? The overall fit of the model, how to increase the accuracy (test, training)? Is it overfitting or underfitting? Why? Plot the distribution of true target variable values and their predictions on both the training set and test set. What are the insights gained from the dataset and the trained classification model?

Write a report and an ipynb file.
