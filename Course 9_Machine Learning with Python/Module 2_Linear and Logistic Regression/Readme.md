# Module 2 Summary and Highlights
Congratulations! You have completed this lesson. At this point in the course, you know: 

## LINEAR REGRESSION

- Regression models relationships between a continuous target variable and explanatory features, covering simple and multiple regression types.

- Simple regression uses a single independent variable to estimate a dependent variable, while multiple regression involves more than one independent variable.

- In which of the following scenarios would simple regression be an appropriate analysis method?<br/>
Predicting annual rainfall based on average temperature.

- A multinational company is trying to predict employee productivity based on several factors, including hours of training, years of experience, and the number of completed projects. What regression technique would allow them to consider all these variables in their model?<br/>
Multiple linear regression

- What type of regression would be most appropriate for predicting carbon dioxide emissions when the independent variables considered are engine size and number of cylinders?<br/>
Multiple linear regression is suited for situations where more than one independent variable is utilized to predict a dependent variable. It is the most appropriate choice as both engine size and number of cylinders are being considered.

- Why is ordinary least squares (OLS) regression's accuracy for complex data sets limited?<br/>
OLS regression may inaccurately weigh outliers, resulting in skewed outputs.

- What multiple linear regression model estimates the values of coefficients by minimizing the Mean Squared Error (MSE)?<br/>
Ordinary least squares (OLS) is a popular method for estimating coefficients by <ins>minimizing the MSE</ins>.

- A real estate company wants to forecast housing prices based on factors like location, square footage, and number of bedrooms. Which type of analysis would best help predict prices as a continuous variable?<br/>
Multiple regression

- In which of the following cases would multiple linear regression be the most suitable analysis method?<br/>
Estimating sales based on budget, reach, and frequency.
Predicting future sales based on last year's sales data.

- Regression is widely applicable, from forecasting sales and estimating maintenance costs to predicting rainfall and disease spread.

- In simple linear regression, a best-fit line minimizes errors, measured by Mean Squared Error (MSE); this approach is known as Ordinary Least Squares (OLS).

- OLS regression is easy to interpret but sensitive to outliers, which can impact accuracy.

- Multiple linear regression extends simple linear regression by using multiple variables to predict outcomes and analyze variable relationships.

- Adding too many variables can lead to overfitting, so careful variable selection is necessary to build a balanced model.

- Nonlinear regression models complex relationships using polynomial, exponential, or logarithmic functions when data does not fit a straight line.

## RANDOM FOREST REGRESSION
- Which of the following regression methods is a MODERN machine learning technique?<br/>
RANDOM FOREST regression

## POLYNOMIAL REGRESSION
- Polynomial regression can fit data but may overfit by capturing random noise rather than the underlying patterns.

- What type of issue occurs when a high-degree polynomial regression model <ins>memorizes random noise</ins> in the data?<br/>
Overfitting
  
- A researcher wants to model a non-linear growth in CO2 emissions as engine size increases, showing a smooth curve. Which regression technique is suitable in this scenario?<br/>
Polynomial regression. <br/>
For modeling a non-linear single-variable relationship, polynomial regression is the right choice.


## LOGISTIC REGRESSION

- Logistic regression is a probability predictor and binary classifier, suitable for binary targets and assessing feature impact.

- Logistic regression minimizes errors using log-loss and optimizes with gradient descent or stochastic gradient descent for efficiency.

- Gradient descent is an iterative process to minimize the cost function, which is crucial for training logistic regression models.

- The primary purpose of logistic regression in machine learning?<br/>
Logistic regression predicts the probability of an observation belonging to one of two classes, 
such as true or false, and assigns the class using a threshold probability

-What kind of outcomes does logistic regression predict?<br/>
BINARY classification. 
Logistic regression predicts the probability that observations belong to one of two classes, such as true or false, and classifies it using a threshold

-Which parameter is used in logistic regression to determine the class of an observation?<br/>
THRESHOLD probability.
Logistic regression assigns classes based on a threshold probability to differentiate between the two classes.

- A healthcare provider uses logistic regression to predict whether a patient will develop a certain condition based on features like age, weight, and medical history. The model correctly identifies most high-risk patients but often misclassifies low-risk patients as high-risk. What method could help the provider reduce false positives?<br/>
Tune the decision threshold of a logistic regression model.

- An e-commerce company uses logistic regression to predict whether a product will be returned based on order details (like delivery time and product rating). What does a predicted probability of 0.8 mean in this case?<br/>
The model predicts an 80% likelihood of product return.

- A data scientist is using logistic regression to predict customer churn. After evaluating the model, they notice a high log-loss value. What is the most appropriate first step to improve the model?<br/>
Parameter Tuning.<br/>
Adjusting the model's parameters can directly address the high log-loss value and improve performance.

-What is the primary objective of the logistic regression TRAINING process?<br/>
MINIMIZE the cost function (log-loss) to improve class predictions.

### LOG-LOSS

- You are evaluating a binary classification model using log loss. Which of the following scenarios would result in the HIGHEST LOG LOSS?<br/>
The model predicts a probability of 0.1 for the correct class and 0.9 for the INCORRECT class.

- In a multi-class classification problem, log loss is used to measure model performance. Which of the following statements is true about log loss in this context?<br/>
A LOWER log loss indicates BETTER model performance, predicting models are close to the true labels. 


- Use StandardScalar function in the Scikit-Learn library to standardize or normalize the dataset in order to have all the features at the same scale. This helps the model learn faster and improves the model performance<br/>
```
X_norm = StandardScaler().fit(X).transform(X)
X_norm[0:5] #print the first five rows of the standardized dataset; Useful for quickly checking the transformed values
```

## LOGARITHMIC REGRESSION

- Which scenario best demonstrates the appropriate use of LOGARITHMIC regression?<br/>
Estimating decrease in productivity gains with each additional hour of employee training.
This pattern matches a logarithmic curve: rapid increase initially, then flattening out.

- A company is analyzing its production costs against the number of workers it employs. It observes diminishing returns in its cost savings as it hires more workers. 
Which type of regression would be most appropriate for modeling this relationship?<br/>
Logarithmic regression<br/>
This pattern matches a logarithmic curve, where growth (or savings) increases quickly at first and then levels off.


###  Model evaluation
You can compare the actual values and predicted values to calculate the accuracy of a regression model. Evaluation metrics play a key role in the development of a model, as they provide insight into areas that require improvement.

There are different model evaluation metrics, let's use MSE here to calculate the accuracy of our model based on the test set:

- Mean Absolute Error (MAD): It is the mean of the absolute value of the errors. This is the easiest of the metrics to understand since it’s just an average error.

- Mean Squared Error (MSE): MSE is the mean of the squared error. In fact, it's the metric used by the model to find the best fit line, and for that reason, it is also called the residual sum of squares.

- Root Mean Squared Error (RMSE). RMSE simply transforms the MSE into the same units as the variables being compared, which can make it easier to interpret.

- R2-Score is not an error but rather a popular metric used to estimate the performance of your regression model. It represents how close the data points are to the fitted regression line. The higher the R2-Score value, the better the model fits your data. The best possible score is 1.0 and it can be negative (because the model can be arbitrarily worse).


[Cheat Sheet: Linear and Logistic Regression](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL3BWam5EcGZuOFN5ZVZuZmV1QTAzSlEvTTJMMyUyMENoZWF0c2hlZXQtVjIubWQ_dD0xNzQ2MTI3NDI5IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjoyNTI0NjcsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3Njk3MjI3fQ.EZycV2hoZEIcAE6y0dy6h-Cf899Ixw3kxYpla3LKbgc)<br/>
[Simple Linear Regressio](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%201_Introduction%20to%20Machine%20Learning/Lab_Simple%20Linear%20Regression.ipynb)<br/>
[Multiple Linear Regression](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%201_Introduction%20to%20Machine%20Learning/Lab_Multiple%20Linear%20Regression.ipynb)<br/>
[Logistic Regression](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%202_Linear%20and%20Logistic%20Regression/Lesson%202_Logistic%20Regression/Lab_Logistic%20Regression.ipynb)
