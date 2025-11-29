# Lesson Summary

Congratulations! You have completed this lesson. At this point in the course, you know: 

## Part 1: Training and Testing
- How to split your data using the train_test_split() method into training and test sets. You use the training set to train a model, discover possible predictive relationships, and then use the test set to test your model to evaluate its performance.

```
# Use the function "train_test_split" to split up the dataset such that 40% of the data samples will be utilized for testing
from sklearn.model_selection import train_test_split
x_train1, x_test1, y_train1, y_test1 = train_test_split(x_data, y_data, test_size=0.4, random_state=0)

#x_train1 → training features (used to train the model).
#x_test1 → testing features (used to evaluate the model).
#test_size=0.4 means 40% of the data samples will be utilized for testing; The remaining 60% goes into the training set.
#setting random_state=0 makes sure you get the same split every time you run the code.

print("number of test samples :", x_test1.shape[0])
print("number of training samples:",x_train1.shape[0])
```

- How to use the generalization error to measure how well your data does at predicting previously unseen data.

### Cross-Validation Score

- Without sufficient data, you go for cross validation, which involves <ins>creating different subsets of training and testing data multiple times and evaluating performance across all of them using the R2 value.</ins>
  
```  
from sklearn.model_selection import cross_val_predict
from sklearn.linear_model import LinearRegression 
lre=LinearRegression()
yhat = cross_val_predict(lre,x_data[['attribute_1']], y_data,cv=4)
```

- How to use cross-validation by splitting the data into folds where you use some of the folds as a training set, which we use to train the model, and the remaining parts are used as a test set, which we use to test the model. You iterate through the folds until you use each partition for training and testing. At the end, you average results as the estimate of out-of-sample error.
  
``` 
from sklearn.model_selection import cross_val_predict
from sklearn.linear_model import LinearRegression 
lre=LinearRegression()
yhat = cross_val_predict(lre,x_data[['attribute_1']], y_data,cv=4)
```

## Part 2: Overfitting, Underfitting and Model Selection

![Overfitting Model](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%207_Data%20Analysis%20with%20Python/Module%205_Model%20Evaluation/Overfitting%20Model.png)

- How to pick the best polynomial order and problems that arise when selecting the wrong order polynomial by analyzing models that underfit and overfit your data.

- Select the best order of a polynomial to fit your data by minimizing the test error using a graph comparing the mean square error to the order of the fitted polynomials.

```
x_train, x_test, y_train, y_test = train_test_split(x_data, y_data, test_size=0.45, random_state=0)

# Perform a degree 5 polynomial transformation on the feature 'horsepower'
pr = PolynomialFeatures(degree=5)
x_train_pr = pr.fit_transform(x_train[['horsepower']])
x_test_pr = pr.fit_transform(x_test[['horsepower']])
pr

# Create a Linear Regression model "poly" and train it
poly = LinearRegression()
poly.fit(x_train_pr, y_train)


# Create output of our model using the method "predict
yhat = poly.predict(x_test_pr)
yhat[0:5]

# R^2 of the training data
poly.score(x_train_pr, y_train)

# R^2 of the test data
poly.score(x_test_pr, y_test)

# Let's see how the R^2 changes on the test data for different order polynomials and then plot the results:
Rsqu_test = []

order = [1, 2, 3, 4]
for n in order:
    pr = PolynomialFeatures(degree=n)
    
    x_train_pr = pr.fit_transform(x_train[['horsepower']])
    
    x_test_pr = pr.fit_transform(x_test[['horsepower']])    
    
    lr.fit(x_train_pr, y_train)
    
    Rsqu_test.append(lr.score(x_test_pr, y_test))

plt.plot(order, Rsqu_test)
plt.xlabel('order')
plt.ylabel('R^2')
plt.title('R^2 Using Test Data')
plt.text(3, 0.75, 'Maximum R^2 ')  
```

- The <ins>lower the R^2</ins>, the <ins>worse the model</ins>.
- A <ins>negative R^2 </ins> is a sign of <ins>overfitting</ins>.

## Part 3: Ridge Regression

![Ridge Regression](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%207_Data%20Analysis%20with%20Python/Module%205_Model%20Evaluation/Ridge%20Regression.png)

- You should use ridge regression when there is a strong relationship among the independent variables to <ins>prevent overfitting</ins>

- Ridge regression controls the magnitude of polynomial coefficients by introducing a hyperparameter, alpha. 

- To determine alpha, you divide your data into training  and validation data. Starting with a small value for alpha, you train the model, make a prediction using the validation data, then calculate the R-squared and store the values. You repeat the value for a larger value of alpha. You repeat the process for different alpha values, training the model, and making a prediction. You select the value of alpha that maximizes R-squared.
  
```
from sklearn.linear_model import Ridge
pr=PolynomialFeatures(degree=2) x_train_pr=pr.fit_transform(x_train[['attribute_1', 'attribute_2', ...]])
x_test_pr=pr.fit_transform(x_test[['attribute_1', 'attribute_2',...]])
RigeModel=Ridge(alpha=1)
RigeModel.fit(x_train_pr, y_train)
yhat = RigeModel.predict(x_test_pr)
```

- A model that closely follows every training point but diverges from the actual function that generated the data is overfitting.

<ins>Overfitting</ins> means the model has <ins>low bias</ins> (it matches training data very well) but <ins>high variance/ins> (its predictions swing wildly when applied to new or unseen data).

Because it diverges from the true underlying function, it does not generalize well.


  ## Part 4: Grid Search

- That grid search allows you to scan through multiple hyperparameters using the Scikit-learn library, which iterates over these parameters using cross-validation. Based on the results of the grid search method, you <ins>select optimum hyperparameter values</ins>

- The GridSearchCV() method takes in a dictionary as its argument where the key is the name of the hyperparameter, and the values are the hyperparameter values you wish to iterate over.
```
from sklearn.model_selection import GridSearchCV
from sklearn.linear_model import Ridge
parameters= [{'alpha': [0.001,0.1,1, 10, 100, 1000, 10000, ...]}]
RR=Ridge()
Grid1 = GridSearchCV(RR, parameters1,cv=4) Grid1.fit(x_data[['attribute_1', 'attribute_2', ...]], y_data)
BestRR=Grid1.best_estimator_
BestRR.score(x_test[['attribute_1', 'attribute_2', ...]], y_test)
```
