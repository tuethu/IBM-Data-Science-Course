# Lesson Summary
Congratulations! You have completed this lesson. At this point in the course, you know: 

## 1. Single Linear Regression

- Linear regression refers to using one independent variable to make a prediction.
- Simple linear regression, or SLR, is a method used to understand the relationship between two variables, the predictor independent variable x and the target dependent variable y.

![Linear Regression and Multiple Linear Regression](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%207_Data%20Analysis%20with%20Python/Module%204_Model%20Development/Linear%20Regression%20and%20Multiple%20Linear%20Regression.png)
  
```  
lm = LinearRegression()
lm
X = df[['highway-mpg']]
Y = df['price']
lm.fit(X,Y)
Yhat=lm.predict(X)
Yhat[0:5]
```

## 2. Multiple Linear Regression

- You can use multiple linear regression to explain the relationship between one continuous target y variable and two or more predictor x variables.

![](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%207_Data%20Analysis%20with%20Python/Module%204_Model%20Development/Multiple%20Linear%20Regression.png)

``` 
Z = df[['horsepower', 'curb-weight', 'engine-size', 'highway-mpg']]
lm.fit(Z, df['price'])
```

- Use the regplot and residplot functions in the Seaborn library to create regression and residual plots, which help you identify the strength, direction, and linearity of the relationship between your independent and dependent variables.

### Residual plot: 
A residual plot is a graph that shows the residuals (e) (The difference between the observed value (y) and the predicted value (Yhat))
on the vertical y-axis and the independent variable on the horizontal x-axis.

- When using residual plots for model evaluation, residuals should ideally have <ins>zero mean</ins>, appear <ins>evenly distributed</ins> around the x-axis, and have consistent variance. 
Why is that? Randomly spread out residuals means that the variance is constant, and thus the linear model is a good fit for this data.

![Residual plot](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%207_Data%20Analysis%20with%20Python/Module%204_Model%20Development/Residual%20plot.png)

### Distribution plots for models with multiple features:
We can look at the distribution of the fitted values that result from the model and compare it to the distribution of the actual values.
Learn to construct distribution plots to compare predicted and actual values, particularly when your model includes more than one independent variable. Know that this can offer deeper insights into the accuracy of your model across different ranges of values.

plt.figure(figsize=(width, height))

```
ax1 = sns.distplot(df['price'], hist=False, color="r", label="Actual Value")
sns.distplot(Y_hat, hist=False, color="b", label="Fitted Values" , ax=ax1)


plt.title('Actual vs Fitted Values for Price')
plt.xlabel('Price (in dollars)')
plt.ylabel('Proportion of Cars')

plt.show()
plt.close()
```
![Distribution plot](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%207_Data%20Analysis%20with%20Python/Module%204_Model%20Development/Distribution%20plot.png)

## 3. Polynomial Regression

![Polynomial Regression Definition](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%207_Data%20Analysis%20with%20Python/Module%204_Model%20Development/Polynomial%20Regression%20Definition.png)

- The order of the polynomials affects the fit of the model to your data. Apply Python's polyfit function to develop polynomial regression models that suit your specific dataset.

- To prepare your data for more accurate modeling, use feature transformation techniques, particularly using the preprocessing library in scikit-learn, transform your data using polynomial features, and use the modules like StandardScaler to normalize the data.

```
def PlotPolly(model, independent_variable, dependent_variabble, Name):
    x_new = np.linspace(independent_variable.min(),independent_variable.max(),100)
    y_new = model(x_new)

    plt.plot(independent_variable, dependent_variabble, '.', x_new, y_new, '-')
    plt.title(f'Polynomial Fit for Price ~ {Name}')
    ax = plt.gca()
    ax.set_facecolor((0.898, 0.898, 0.898))
    fig = plt.gcf()
    plt.xlabel(Name)
    plt.ylabel('Price of laptops')
PlotPolly(p5, X, Y, 'CPU_frequency')   #Call for function of degree 5
```

![Polynomial Regression](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%207_Data%20Analysis%20with%20Python/Module%204_Model%20Development/Polynomial%20Regression.png)
    
## 4. Pipeline

- Pipelines allow you to simplify how you perform transformations and predictions sequentially, and you can use pipelines in scikit-learn to streamline your modeling process.

- You can construct and train a pipeline to automate tasks such as normalization, polynomial transformation, and making predictions.

- To determine the fit of your model, you can perform sample evaluations by using the Mean Square Error (MSE), using Python’s mean_squared_error function from scikit-learn, and using the score method to obtain the R-squared value.

- A model with a high R-squared value close to 1 and a low MSE is generally a good fit, whereas a model with a low R-squared and a high MSE may not be useful.

- Be alert to situations where your R-squared value might be negative, which can indicate overfitting. 

- When evaluating models, use visualization and numerical measures and compare different models.

- The mean square error is perhaps the most intuitive numerical measure for determining whether a model is good.

- A distribution plot is a suitable method for multiple linear regression.

- An acceptable r-squared value depends on what you are studying and your use case.

- To evaluate your model’s fit, apply visualization, methods like regression and residual plots, and numerical measures such as the model's coefficients for sensibility: 

- Use Mean Square Error (MSE) to measure the average of the squares of the errors between actual and predicted values and examine R-squared to understand the proportion of the variance in the dependent variable that is predictable from the independent variables.

- When analyzing residual plots, residuals should be randomly distributed around zero for a good model. In contrast, a residual plot curve or inaccuracies in certain ranges suggest non-linear behavior or the need for more data.
