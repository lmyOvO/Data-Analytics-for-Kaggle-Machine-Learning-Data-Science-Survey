# Data-Analytics-for-Kaggle-Machine-Learning-Data-Science-Survey-Part-1

# Background:

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

3. Select “highest level of formal education” (Q4) from the dataset and repeat steps a to e, this time use analysis of variance (ANOVA) instead of t-test for hypothesis testing to compare the means of salary for three groups (Bachelor’s degree, Doctoral degree, and Master’s degree) [0.75pts for a; 0.5 pts for b; 2pts for c; 0.75 pts for d; 1pt for e].

Write a report and an ipynb file
