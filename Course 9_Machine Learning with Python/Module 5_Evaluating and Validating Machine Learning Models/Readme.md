# Module 5 Summary and Highlights

Congratulations! You have completed this lesson. At this point in the course, you know:

- Supervised learning evaluation assesses a model's ability to predict outcomes for unseen data, often using a train/test split to estimate performance.

## KEY METRICS FOR CLASSIFICATION EVALUATION
- Key metrics for classification evaluation include accuracy, confusion matrix, precision, recall, and the F1 score, which balances precision and recall.
   - What is the purpose of supervised learning evaluation?<br/>
To assess model predictions against ground truth labels.

### F1 SCORE
   - How is the F1 SCORE determined?<br/>
HARMONIC mean of PRECISION and RECALL.

### RECALL- PRECISION
   - How do you calculate precision in a model?<br/>
True positives divided by predicted positives.
   - What does accuracy represent in machine learning?<br/>
Ratio of correct predictions to total instances.

   - What does RECALL measure in machine learning?<br/>
TRUE positives divided by ACTUAL positives.
   - In the context of model evaluation, which metric would be particularly useful when the COST of FALSE NEGATIVES is high?<br/>
Recall<br/>
( Recall measures how many of the actual positive cases your model successfully identifies. When the cost of false negatives is high—meaning missing a positive case is dangerous or expensive—recall becomes the priority.
Examples where recall matters:
Detecting diseases
Fraud detection
Identifying safety hazards
In these situations, you want to catch as many true positives as possible, even if it means tolerating more false positives.)

   - In a medical diagnosis scenario, where it is crucial to AVOID MISSING any TRUE POSITIVE cases, which metric is most important?<br/>
Recall

![Key metrics for classification evaluation](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Key%20metrics%20for%20classification%20evaluation.png)

![KNN and SVM Prediction Sensitivity](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/KNN%20and%20SVM%20Prediction%20Sensitivity.png)


## REGRESSION MODEL EVALUATION METRICS

- Regression model evaluation metrics include MAE(Mean Absolute Error), MSE (Mean Squared Error), RMSE (Root Mean Squared Error), R-squared(coefficient of determination), and explained variance to measure prediction accuracy.

### R-SQUARED 
   - What does R-SQUARED measure in a model?<br/>
VARIANCE explained by the independent variable.

   -What does R-squared measure in regression analysis?<br/>
The proportion of variance in the target variable explained by the model<br/>
(For example: An R² of 0.80 means the model explains 80% of the variance in the outcome. The remaining 20% is unexplained (error, noise, missing predictors, etc.).

   -Which regression evaluation metric measures the proportion of variance in the target variable explained by the input variables?<br/>
R-squared<br/>
(R-squared measures the proportion of variance in the target variable explained by the input variables, indicating the model’s goodness of fit.)

   -What is the effect of using a mean-value model in regression analysis?<br/>
R-squared will be zero, as the model explains no variance<br/>
(A mean-value model predicts the same constant value (the mean of the target variable) for every observation. It does not use any features to explain variation in the data.
Because of that: The model explains 0% of the variance in the target. All variability remains in the residuals. Therefore, R² = 0.)

![R-squared](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/R-squared.png)

### ROOT MEAN SQUARED ERROR (RMSE) & MEAN ABSOLUTE ERROR (MAE)
   - Why is Root Mean Squared Error (RMSE) more intuitive than Mean Squared Error (MSE)?<br/>
RMSE has the SAME UNITS as the TARGET variable.<br/>
   -Which regression metric is the square root of Mean Squared Error (MSE)?<br/>
Root Mean Squared Error (RMSE)

   - How do you calculate Mean Absolute Error (MAE)?<br/>
Average absolute DIFFERENCE between FITTED and OBSERVED values.<br/>

![Regression model evaluation metrics](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Regression%20model%20evaluation%20metrics.png)

```
mae = mean_absolute_error(y_test, y_pred_test)
mse = mean_squared_error(y_test, y_pred_test)
rmse = root_mean_squared_error(y_test, y_pred_test)
r2 = r2_score(y_test, y_pred_test)
print(f"Mean Absolute Error (MAE): {mae:.4f}")
print(f"Mean Squared Error (MSE): {mse:.4f}")
print(f"Root Mean Squared Error (RMSE): {rmse:.4f}")
print(f"R² Score: {r2:.4f}")
```
   -Mean Absolute Error (MAE): 0.3276 <br/>
-> The mean absolute error is $33,220. So, on average, predicted median house prices are off by $33k.<br/>

   -Mean Squared Error (MSE): 0.2556<br/>
-> Mean squared error is less intuitive to interpret, but is usually what is being minimized by the model fit.<br/>
                                                                                                               
   -Root Mean Squared Error (RMSE): 0.5055<br/>
-> On the other hand, taking the square root of MSE yields a dollar value, here RMSE = $50,630.<br/>

   -R² Score: 0.8050<br/>
->An R-squared score of 0.80 is not considered very high. It means the model explains about %80 of the variance in median house prices, although this interpretation can be misleading for compex data with nonlinear relationships, skewed values, and outliers. R-square can still be useful for comparing models though.

### EVALUATION OF UNSUPERVISED LEARNING MODELS

- Unsupervised learning models are evaluated for pattern quality and consistency using metrics like Silhouette Score, Davies-Bouldin Index, and Adjusted Rand Index.
![Internal Clustering Evaluation Metrics](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Internal%20Clustering%20Evaluation%20Metrics.png)

   -What does a lower Davies-Bouldin index indicate about a clustering result?<br/>
More distinct and compact clusters.
![Davies-Bouldin index](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Davies-Bouldin%20index.png)

![External Clustering Evaluation Metrics](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/External%20Clustering%20Evaluation%20Metrics.png)
   
   -How do external clustering evaluation metrics differ from internal metrics?<br/>
They use labeled data to evaluate clustering quality.

   -What does a higher Fowlkes-Mallows index score indicate?<br/>
Better clustering performance.

   -What does an adjusted Rand index score of 1 signify?<br/>
Perfect alignment between true labels and clustering outcomes.

   -How does the explained variance ratio in PCA help in dimensionality reduction?<br/>
It measures variance captured by each component.

![Explained variance ratio for PCA](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Explained%20variance%20ratio%20for%20PCA.png)

   -What is the purpose of evaluating dimensionality reduction techniques?<br/>
To assess how well-reduced data retains important information.

   -In k-means clustering, what does a LOWER INERTIA (remain unchanged) value suggest?<br/>
More COMPACT clusters.It is defined as the sum of squared distances between each data point and its cluster centroid. <br/>
LOWER inertia values indicate MORE COMPACT clusters and a potentially BETTER clustering outcome. <br/>
However, inertia tends to decrease as the number of clusters increases, so it's important to interpret it alongside other metrics.<br/>
![Cluster Stability](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Cluster%20Stability.png)

   -What is the significance of a normalized mutual information score of 1?<br/>
Perfect agreement between predicted clusters and true labels.

### SILHOUETTE SCORE
   -How is the Silhouette Score used in clustering evaluation?<br/>
To compare COHESION(united whole)within clusters to separation from other clusters.
![Silhouette Score](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Silhouette%20Score.png)


   -Which of the following clustering evaluation metrics ranges from -1 to 1, with HIGHER values indicating BETTER-DEFINED clusters?<br/>
Silhouette Score
![Silhouette Score2](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Silhouette%20Score2.png)

   -You are using a clustering algorithm to group customers based on purchasing behavior and assessing the quality of the clusters to determine how well-separated the clusters are. Which of the following metrics is most suitable for this task?<br/>
Silhouette score <br/>
(The Silhouette score measures how similar each point is to its cluster compared to others, evaluating the quality and separation of clusters. This makes it most suitable for assessing how well the clusters are formed regarding separation and cohesion.)

   -A company uses a clustering algorithm to segment customers based on purchasing patterns. They want to evaluate the compactness and separation of the resulting clusters. Which of the following metrics is most appropriate for this evaluation?<br/>
Silhouette score<br/>
(The Silhouette score evaluates the compactness (how close points are within the same cluster) and separation (how distinct clusters are from each other), making it ideal for assessing the overall quality of the clusters.)

   -You are using a clustering algorithm to group customers based on purchasing behavior and assessing the quality of the clusters to determine how well-separated the clusters are. Which of the following metrics is most suitable for this task?<br/>
Silhouette score<br/>
(The silhouette score measures how well each data point fits within its assigned cluster compared to other clusters. It directly evaluates:
Cluster cohesion (how close points are within the same cluster)
Cluster separation (how far clusters are from each other)
This makes it ideal when you want to know how well-separated and meaningful your clusters are.)


   -What is the primary goal of clustering in unsupervised learning?<br/>
To group similar data points into clusters.

- Dimensionality reduction evaluation involves Explained Variance Ratio, Reconstruction Error, and Neighborhood Preservation to assess data structure retention.

- Model validation, including dividing data into training, validation, and test sets, helps prevent overfitting by tuning hyperparameters carefully.

### CROSS-VALIDATION

- Cross-validation methods, especially K-fold and stratified cross-validation, support robust model validation without overfitting to test data.

   -A data scientist wants to build a fraud detection model that works well on unseen financial transactions. Which technique should a data scientist use to VALIDATE a model and AVOID OBERFITTING?<br/>
Cross-validation<br/>
(Cross-validation splits the data into multiple folds for training and validation, helping the model generalize better to unseen data.)

   -A data analyst has interpreted a model’s feature importance without considering its relationship with input variables. What mistake could this lead to?<br/>
Overlooking correlated features in importance scores<br/>
(Correlations between features can cause the model to assign a shared importance to those features. Ignoring their redundancy may lead to incomplete or incorrect conclusions about their significance.
  
![Cross-validation algorithm](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Cross-validation%20algorithm.png)

![K-fold Cross-validation](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/K-fold%20Cross-validation.png)

### LASSO REGRESSION (L1 REGULARIZATION)

- Regularization techniques, such as Lasso (L1) and Ridge (L2) regression , help <ins>prevent overfitting</ins> by <ins>adding penalty</ins> terms to linear regression models.
![Ridge and Lasso Regression](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Ridge%20and%20Lasso%20Regression.png)

   -Lasso (Least Absolute Shrinkage and Selection Operator; or L1 regularization) is a regression analysis method that performs both variable selection and regularization in order to enhance the prediction accuracy and interpretability of the resulting statistical model. The lasso method assumes that the coefficients of the linear model are sparse, meaning that few of them are non-zero.

   -A researcher wants to simplify a predictive model by retaining the most relevant features. Which type of regularization can often be used for feature selection?<br/>
Lasso regression<br/>
(Lasso regression applied to the features can shrink some of their coefficients to zero, so those features can optionally be left out in subsequent modeling.)

   -During a model performance review, a machine learning engineer compares two regularization techniques and observes that one shrinks coefficients to zero while the other reduces their size. What is the key difference between Lasso and Ridge regression?<br/>
Lasso uses an L-1 penalty, and Ridge uses an L-2 penalty.<br/>
(The primary difference between Lasso and Ridge regression lies in the penalty term used: Lasso uses an L-1 penalty (sum of absolute values), while Ridge uses an L-2 penalty (sum of squares of coefficients).)


### RIDGE REGRESSION (L2 REGULARIZATION)
   -Ridge regression, also called L2 regularization, is a linear regression technique designed to handle multicollinearity and overfitting by adding a penalty term to the Ordinary Least Squares (OLS) loss function.

-In which scenario is Lasso regression most beneficial?
When the data is sparse and has many irrelevant features

-In the context of regularization, what does the lambda parameter control?
The penalty term's influence on the cost function

![Model Comparision 1](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Model%20Comparision%201.png)

![Model Comparision 2](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Model%20Comparision%202.png)

- Data leakage occurs when training data includes information UNAVAILABLE in REAL-WORLD data, which is preventable by separating data properly and mindful feature selection.

-Jimmy wants to develop a model that predicts the overall average approval rate as a feature in the loan approval process. How can he mitigate the risk of data leakage in machine learning?<br/>
Avoid including features derived from the entire dataset<br/>
(Features like global averages, which use data from the entire dataset, can cause data leakage by introducing information that wouldn’t be available in production.)


- Common modelling pitfalls include misinterpreting feature importance, ignoring class imbalance, and making causal inferences without sufficient evidence.”  
![Common modelling pitfalls](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Common%20modelling%20pitfalls.png)

![Machine Learning Pipelines and GridSearchCV](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Machine%20Learning%20Pipelines%20and%20GridSearchCV.png)

- Feature importance assessments should consider redundancy, scale sensitivity, and avoid misinterpretation, as well as inappropriate assumptions about causation.

### SKEWNESS
-What is the benefit of transforming a skewed target variable, such as using a Box-Cox or logarithmic transformation?
It makes the model fit the target variable more easily by reducing skewness (Độ lệch- là sự biến dạng sự bất đối xứng trong một phân phối hình chuông đối xứng hay phân phối chuẩn trong một tập dữ liệu.)

![Skewness](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Skewness.png)

-Which of the following best describes the role of the test set in model validation?
The test set is used to evaluate the model after it has been trained and validated.

   -A machine learning engineer selected hyperparameters based on performance on the test set. What risk does this introduce?<br/>
Data snooping<br/>
(When you choose hyperparameters based on test‑set performance, the test set is no longer a true “unseen” dataset. You’ve indirectly learned from it, even if you didn’t retrain on it.
This contaminates the evaluation process and leads to:
Data snooping (data leakage) → the model has indirectly “peeked” at the test set
Overly optimistic performance estimates
A test set that no longer reflects real‑world generalization)

   -A developer adds a feature to a model that relies on future data that will remain unavailable during predictions. Which approach would best mitigate this issue?<br/>
Ensuring that no information is included in the training data

   -When assessing feature importance, what can cause misleading results?<br/>
Overlooking the combined effect of correlated features

   -Thomas noticed that his model performs very well on the training data but poorly on unseen test data. Which problem is his model likely suffering from?<br/>
Overfitting





[Lab_Evaluating Classification Models](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%205_Evaluating%20and%20Validating%20Machine%20Learning%20Models/Lesson%201_Evaluating%20Machine%20Learning%20Models/Lab_Evaluating%20Classification%20Models.ipynb)

[Lab_Evaluating K-means Clustering](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%205_Evaluating%20and%20Validating%20Machine%20Learning%20Models/Lesson%201_Evaluating%20Machine%20Learning%20Models/Lab_Evaluating%20K-means%20Clustering.ipynb)

[Lab_Evaluating Random Forest Performance](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%205_Evaluating%20and%20Validating%20Machine%20Learning%20Models/Lesson%201_Evaluating%20Machine%20Learning%20Models/Lab_Evaluating%20Random%20Forest%20Performance.ipynb)

[Lab_Regularization in Linear Regression](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%205_Evaluating%20and%20Validating%20Machine%20Learning%20Models/Lesson%202_Best%20Practices%20for%20Ensuring%20Model%20Generalizability/Lab_Regularization%20in%20Linear%20Regression.ipynb)

[Lab_Machine Learning Pipelines and GridSearchCV](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%205_Evaluating%20and%20Validating%20Machine%20Learning%20Models/Lesson%202_Best%20Practices%20for%20Ensuring%20Model%20Generalizability/Lab_Machine%20Learning%20Pipelines%20and%20GridSearchCV.ipynb)

[]()

![]()

![]()

[Cheat Sheet: Evaluating and Validating Machine Learning Models](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkLzloWDBlUk13aXY3RTVwd2Jwc3N0a2cvTW9kdWxlJTIwNSUyMENoZWF0JTIwU2hlZXQtVjIubWQ_dD0xNzQ2MTMwMzI5IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjoyNTI1NzAsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3Njk3MjI5fQ.MRGfNS8jJP7fjDztRX_-mlYSC41jJ6u49ReaXLeLKTk)

