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

- For the first run of the model, I chose two hidden layers with the first hidden layer having 80 nodes and the second layer having 30 nodes. Both hidden layers had a ReLU activation function and the output layer had a sigmoid activation function. I chose two hidden layers because I did not want to overfit the model and I chose 110 total nodes because the general rule of thumb for a simple model is to use 2-3 times as many nodes as there are inputs. After encoding the string datatypes into numbers which could be passed into the neural network, there were 44 inputs and 110 nodes fits nicely between 2-3 times the 44 inputs. I chose the ReLU activation function for the hidden layers because it identifies nonlinear characteristics from the input values. I chose the sigmoid activation function for the output layer as the sigmoid function is ideal for binary classification since its values are normalized to a probablility between 0 and 1.

![Details](Resources/details.PNG)

- After the first run of the model, I achieved a predictive accuracy of 73%, which is lower than the target predictive accuarcy of 75%.

![Accuracy](Resources/accuracy.PNG)

- I made three attempts to increase the model performance:

#### Attempt 1

In my first attempt, I noticed that the ASK_AMT variable had a lot of unique values so I attempted to bucket the data by creating categorical values and reassigning the data points to new corresponding values. As seen in the screenshot, there were many different values ranging from 5000 to over 8 billion. Based on the median of 5000, I created five buckets which I felt distributed the values as best as possible.

![Attempt 1](Resources/attempt1.PNG)

The first attempt at increasing the model performance was unsuccessful. I achieved a predictive accuracy of 72%, which was even less than the original predictive accuracy of about 73%.

![Attempt 1 Accuracy](Resources/attempt1_accuracy.PNG)

#### Attempt 2

In my second attempt, I added additional hidden layers and additional nodes to those respective layers. I increased the layers from two to four and the total nodes from 110 to 500.

![Attempt 2](Resources/attempt2.PNG)

The second attempt at increasing the model performance was unsuccessful, achieving a predictive accuracy again of about 72%.

![Attempt 2 Accuracy](Resources/attempt2_accuracy.PNG)

#### Attempt 3

In my third attempt, I changed the activation function of the hidden layers from ReLU to Leaky ReLU. I chose Leaky ReLU as it was a good nonlinear alternative to the ReLU function. Also, generally when optimizing models, it is better to select from activation functions that are slightly more complex so the sigmoid or tanh functions may not be the best choices.

![Attempt 3](Resources/attempt3.PNG)

The third attempt at increasing the model performance was unsuccessful, achieving a predictive accuracy of just under 72%.

![Attempt 3 Accuracy](Resources/attempt3_accuracy.PNG)

## Summary

Overall, the model was unsuccessful in achieving the 75% target predictive accuracy. With an initial accuracy of 73%, my three attempts to optimize the model to reach the target predictive accuracy were unsuccessful and actually decreased performance by a percentage to about 72%. Since this model was not able to deliver the necessary predictive accuracy, another model might be better to run this analysis such as a logistic regression, support vector machine, or random forest model. In the case of improving the accuracy of analysis run on this dataset, I believe that a logistic regression model would be the best model to use for this analysis. A logistic regression model is a classification algorithm that can analyze continuous and categorical variables, which this data set has. The main purpose of a logistic regression model is to predict the probability of input data belonging to two groups - in this case, we are trying to predict whether an applicant organization will be successful or not successful. Also, the sigmoid curve is the same curve used in the sigmoid activation function of a neural network, which we used in this model.
