# Module 5 Summary and Highlights

Congratulations! You have completed this lesson. At this point in the course, you know:

- Supervised learning evaluation assesses a model's ability to predict outcomes for unseen data, often using a train/test split to estimate performance.

- Key metrics for classification evaluation include accuracy, confusion matrix, precision, recall, and the F1 score, which balances precision and recall.

   - How is the F1 SCORE determined?<br/>
HARMONIC mean of PRECISION and RECALL.

![Key metrics for classification evaluation](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Key%20metrics%20for%20classification%20evaluation.png)

   - What does recall measure in machine learning?<br/>
True positives divided by actual positives.
   - How do you calculate precision in a model?<br/>
True positives divided by predicted positives.
   - What is the purpose of supervised learning evaluation?<br/>
To assess model predictions against ground truth labels.
   - What does accuracy represent in machine learning?<br/>
Ratio of correct predictions to total instances.

![KNN and SVM Prediction Sensitivity](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/KNN%20and%20SVM%20Prediction%20Sensitivity.png)


### REGRESSION MODEL EVALUATION METRICS

- Regression model evaluation metrics include MAE(Mean Absolute Error), MSE (Mean Squared Error), RMSE (Root Mean Squared Error), R-squared(coefficient of determination), and explained variance to measure prediction accuracy.

   - What does R-squared measure in a model?<br/>
Variance explained by the independent variable.

   -What does R-squared measure in regression analysis?<br/>
The proportion of variance in the target variable explained by the model<br/>
(For example: An R² of 0.80 means the model explains 80% of the variance in the outcome. The remaining 20% is unexplained (error, noise, missing predictors, etc.).


   -What is the effect of using a mean-value model in regression analysis?<br/>
R-squared will be zero, as the model explains no variance<br/>
(A mean-value model predicts the same constant value (the mean of the target variable) for every observation. It does not use any features to explain variation in the data.
Because of that: The model explains 0% of the variance in the target. All variability remains in the residuals. Therefore, R² = 0.)

![R-squared](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/R-squared.png)

   - Why is Root Mean Squared Error (RMSE) more intuitive than Mean Squared Error (MSE)?<br/>
RMSE has the same units as the target variable.
   - How do you calculate Mean Absolute Error (MAE)?<br/>
Average absolute difference between fitted and observed values.

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

   -How is the Silhouette Score used in clustering evaluation?<br/>
To compare COHESION(united whole)within clusters to separation from other clusters.
![Silhouette Score](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Silhouette%20Score.png)


   -Which of the following clustering evaluation metrics ranges from -1 to 1, with HIGHER values indicating BETTER-DEFINED clusters?<br/>
Silhouette Score
![Silhouette Score2](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Silhouette%20Score2.png)

   -What is the primary goal of clustering in unsupervised learning?<br/>
To group similar data points into clusters.

- Dimensionality reduction evaluation involves Explained Variance Ratio, Reconstruction Error, and Neighborhood Preservation to assess data structure retention.

- Model validation, including dividing data into training, validation, and test sets, helps prevent overfitting by tuning hyperparameters carefully.

- Cross-validation methods, especially K-fold and stratified cross-validation, support robust model validation without overfitting to test data.

- Regularization techniques, such as ridge (L2) and lasso (L1) regression, help prevent overfitting by adding penalty terms to linear regression models.

- Data leakage occurs when training data includes information unavailable in real-world data, which is preventable by separating data properly and mindful feature selection.

- Common modelling pitfalls include misinterpreting feature importance, ignoring class imbalance, and making causal inferences without sufficient evidence.”  

- Feature importance assessments should consider redundancy, scale sensitivity, and avoid misinterpretation, as well as inappropriate assumptions about causation.

[Lab_Evaluating Classification Models](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%205_Evaluating%20and%20Validating%20Machine%20Learning%20Models/Lesson%201_Evaluating%20Machine%20Learning%20Models/Lab_Evaluating%20Classification%20Models.ipynb)

[Evaluating K-means Clustering](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%205_Evaluating%20and%20Validating%20Machine%20Learning%20Models/Lesson%201_Evaluating%20Machine%20Learning%20Models/Lab_Evaluating%20K-means%20Clustering.ipynb)

[Evaluating Random Forest Performance](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%205_Evaluating%20and%20Validating%20Machine%20Learning%20Models/Lesson%201_Evaluating%20Machine%20Learning%20Models/Lab_Evaluating%20Random%20Forest%20Performance.ipynb)

[]()

[]()

[]()

[Cheat Sheet: Evaluating and Validating Machine Learning Models](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkLzloWDBlUk13aXY3RTVwd2Jwc3N0a2cvTW9kdWxlJTIwNSUyMENoZWF0JTIwU2hlZXQtVjIubWQ_dD0xNzQ2MTMwMzI5IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjoyNTI1NzAsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3Njk3MjI5fQ.MRGfNS8jJP7fjDztRX_-mlYSC41jJ6u49ReaXLeLKTk)

