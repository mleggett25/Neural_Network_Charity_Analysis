# Neural Network Charity Analysis Using TensorFlow in Python

## Overview

### Purpose
The purpose of this analysis was to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup, a non-profit philanthropic foundation.

## Results

### Data Preprocessing

- The variable that is considered the target for this model is the IS_SUCCESSFUL variable which shows whether or not an applicant organization was successful or not. This is our target variable, or dependent variable, because we want to gain a deeper understanding of what makes an applicant organization successful.
- The variables that are considered to be the features for the model are the APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT. These are our independent variables that act as inputs in helping make the prediction.
- There are two variables that are neither a target nor feature and were removed from the dataset - EIN and NAME. These variables were removed because they would not be helpful in making predictions as there can be no reasonable conclusions drawn from an ID number or simply the name of the organization itself.

### Compiling, Training, and Evaluating the Model

- 
