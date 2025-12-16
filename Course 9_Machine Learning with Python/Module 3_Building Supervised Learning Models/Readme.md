# Module 3 Summary and Highlights

Congratulations! You have completed this lesson. At this point in the course, you know: 

- Classification is a SUPERVISED machine learning method used to predict labels on new data with applications in churn prediction, customer segmentation, loan default prediction, and multiclass drug prescriptions.

- Binary classifiers can be extended to multiclass classification using one-versus-all or one-versus-one strategies.

## Logistic Regression with One-vs-All(OvA)
- The algorithm trains a single binary classifier for each class.
- Each classifier learns to distinguish a single class from all the others combined.
- If there are k classes, k classifiers are trained.
- During prediction, the algorithm evaluates all classifiers on each input, and selects the class with the highest confidence score as the predicted class.

- Advantages:
   - Simpler and more efficient in terms of the number of classifiers (k)
   - Easier to implement for algorithms that naturally provide confidence scores (e.g., logistic regression, SVM).

- Disadvantages:
   - Classifiers may struggle with class imbalance since each binary classifier must distinguish between one class and the rest.
   - Requires the classifier to perform well even with highly imbalanced datasets, as the "all" group typically contains more samples than the "one" class.
     
![One-versus-all](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/One-versus-all.png)

- What is the purpose of using a one-versus-all classification strategy?<br/>
To EXTEND binary classifiers to handle multiple classes

## Logistic Regression with One-versus-one(OvO)
- The algorithm trains a binary classifier for every pair of classes in the dataset.
- If there are k classes, this results in classifiers.
- Each classifier is trained to distinguish between two specific classes, ignoring the rest.
- During prediction, all classifiers are used, and a "voting" mechanism decides the final class by selecting the class that wins the majority of pairwise comparisons.

- Advantages:
   - Suitable for algorithms that are computationally expensive to train on many samples because each binary classifier deals with a smaller dataset (only samples from two classes).
   - Can be more accurate in some cases since classifiers focus on distinguishing between two specific classes at a time.

- Disadvantages:
   - Computationally expensive for datasets with a large number of classes due to the large number of classifiers required.
   - May lead to ambiguous predictions if voting results in a tie.
![One-versus-one](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/One-versus-one.png)


- In a one-versus-one classification approach, how can the final class label be decided in case of a tie?
Probability weighing

- In a one-versus-one classification strategy, which method is typically used to determine the final predicted class?
Popularity vote

 

## Decision Tree
- A decision tree classifies data by testing features at each node, branching based on test results, and assigning CLASSES at LEAF nodes.
![Decision Tree](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Decision%20tree.png)

- In a decision tree, what does each leaf node represent?<br/>
A class label

- Decision tree training involves selecting features that best split the data and PRUNING the tree to AVOID OVERFITTING.

- Which feature split would likely provide the HIGHEST INFORMATION GAIN in a decision tree?
A feature that DECREASES ENTROPY in the resulting nodes

- Alice is building a decision tree and wants to evaluate how mixed data is mixed at each node. What does this measure represent in terms of entropy in a decision tree?
The LEVEL of disorder or RANDOMNESS in a node

- You want to determine the best feature to split the data at each node while building a decision tree. Which of the following criteria will you use?
Information gain
(Information Gain is a measure used in decision trees to determine how well a feature splits the data, by quantifying the reduction in uncertainty (entropy) after the split.)

![Pruning Decision tree](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Pruning%20Decision%20tree.png)

- Information gain and Gini impurity are used to measure the quality of splits in decision trees.
![Entropy and Information gain ](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Entropy%20and%20Information%20gain.png)

- Regression trees are similar to decision trees but predict continuous values by recursively splitting data to maximize information gain.

- What is the primary goal of a regression tree?<br/>
To predict continuous values based on features

- Sini is training a regression tree on a large e-commerce dataset with continuous features and wants to find the best split. Which method should she use to identify all possible threshold values that may NOT scale well with large datasets?<br/>
Exhaustive search method. Exhaustive search methods can be computationally expensive and may not scale efficiently with large datasets.

- You want to evaluate the quality of each split while building a regression tree. Which criterion is commonly used in this task?<br/>
Mean squared error (MSE) method

![Regression tree](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Regression%20tree.png)

- Mean Squared Error (MSE) is used to measure split quality in regression trees.

## SUPPORT VECTOR MACHINES (SVM)

- Support Vector Machines (SVM) build classifiers by finding a hyperplane that maximizes the margin between two classes, effective in high-dimensional spaces but sensitive to noise and large datasets.

![SVM](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/SVM.png)

- What is the primary GOAL of an SVM CLASSIFIER in a binary classification task?<br/>
SVM finds a HYPERPLANCE that MAXIMIZES the MARGIN between classes to improve separation.

- What is the role of the C parameter in SVM?<br/>
It controls the width of the margin by allowing some misclassifications

- Rommy is using support vector regression (SVR) to predict housing prices. He adjusts the epsilon (ε) value and notices that more data points are falling outside the shaded prediction band. What does this change in epsilon represent?<br/>
It changes the width of the margin around the predicted curve.

- Jammy is adjusting the epsilon (ɛ) parameter while tuning the support vector regression (SVR) model to predict housing prices. What aspect of the model is Jammy controlling by changing the "ɛ"?
The maximum allowed error for points within the margin

- Mark increases the epsilon (ε) value while tuning a support vector regression (SVR) model on noisy temperature data. As a result, fewer data points are marked as errors. Why does this happen? <br/>
A larger epsilon creates a wider margin where small errors are ignored.
![Support Vector Regression](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Support%20Vector%20Regression%20(SVR).png)


### ROC (Receiver Operating Characteristic curve)
- A plot that shows the trade-off between the True Positive Rate (TPR) and the False Positive Rate (FPR) across all possible classification thresholds.
   - TPR = proportion of actual positives correctly identified (also called Recall).
   - FPR = proportion of actual negatives incorrectly classified as positives

### AUC (Area Under the Curve)
- The area under the ROC curve. It summarizes the ROC curve into a single number.
- Interpretation:
   - 1.0 → Perfect classifier (separates classes flawlessly).
   - 0.5 → No better than random guessing.
   - <0.5 → Worse than random (model is misleading).

![ROC and AUC](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/ROC%20and%20AUC.png)


- Comparison between SVM (Support Vector Machine) and Decision Trees
   - With a larger set of features, SVM performed relatively better in comparison to the Decision Trees.
   - Decision Trees benefited from feature selection and performed better.
   - SVMs may require higher feature dimensionality to create an efficient decision hyperplane.

- What is the function of a hyperplane in SVM?<br/>
A decision boundary that separates data into two parts.

- What are some advantages of using SVM?<br/>
Effective in high-dimensional spaces and robust to overfitting.

- What types of kernel functions are used in SVM?<br/>
Linear, polynomial, radial basis functions (RBF), and sigmoid.

- Why is kerneling used in SVM?<br/>
To make non-linearly separable data linearly separable.

- What does the margin represent in SVM?<br/>
The distance from the hyperplane to the closest points from each class.

- What are support vectors in SVM?<br/>
Nearest-point representatives from each class to the hyperplane.

- What is a Support Vector Machine (SVM)?<br/>
A supervised learning technique for classification and regression.

- What is the purpose of the epsilon tube in SVR?<br/>
Defines a margin around the prediction curve.

- How does the parameter C influence an SVM model?<br/>
It balances margin maximization and misclassification minimization.


##  K-NEAREST NEIGHBORS (k-NN)

- K-Nearest Neighbors (k-NN) is a supervised algorithm used for classification and regression by assigning labels based on the closest labeled data points.
![K-NEAREST NEIGHBORS](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/K-NEAREST%20NEIGHBORS.png)

- What does the k parameter in k-NN represent? <br/>
k is the COUNT of NEAREST NEIGHORS considered when making a prediction.

- What is the primary PURPOSE of SCALING FEATURES before applying k-NN?<br/>
Scaling ensures that NO single feature unfairly INFLUENCE  the DISTANCE METRIC.

- What impact does the value of K have on K-NN's performance?<br/>
SMALL K can cause OVERfitting; LARGE K can cause UNDERfitting (reduces sensitivity).

- To optimize k-NN, test various k values and measure accuracy, considering class distribution and feature relevance.
  
-A retail store wants to classify customers based on their past purchases for marketing purposes. Which of the following is a suitable model for this scenario?<br/>
K-nearest neighbors

- Why is feature scaling crucial in K-NN?<br/>
To prevent features with large values from dominating the distance measure.

- How does K-NN perform regression?<br/>
By averaging or taking the median of the target values of k nearest neighbors.

- How does K-NN classify a data point?<br/>
By predicting the class based on the most popular class among the k nearest neighbors.

- What is a decision boundary in K-NN?<br/>
A line or surface separating different classes in the feature space.

- Why is K-NN called a lazy learner?<br/>
It stores training data and makes predictions based on distances without building a model.

- How does skewed class distribution affect K-NN classification?<br/>
It can make majority voting unreliable due to class prevalence.

- How can you determine the optimal K value in K-NN?<br/>
By testing a range of K values and choosing the one with the best accuracy.

```
#Train Model and Predict  
knn_classifier = KNeighborsClassifier(n_neighbors=k) # Create a KNN classifier with k neighbors
knn_model_6 = knn_classifier.fit(X_train,y_train) # Train the classifier
yhat6 = knn_model.predict(X_test) # Predict on new data
print("Test set Accuracy: ", accuracy_score(y_test, yhat6))
```

##BAGGING- BOOSTING and RANDOM FORESTS

- The bias-variance tradeoff affects model accuracy, and methods such as bagging, boosting, and random forests help manage bias and variance to improve model performance.

- What does bias indicate in model predictions?<br/>
Average difference between predictions and actual values.

- What does variance measure in a model's predictions?<br/>
Spread of predictions and fluctuation with different data subsets.

- How do random forests reduce prediction variance?<br/>
By aggregating predictions from multiple decision trees.
![Random Forests](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Random%20Forests.png)

- What is the purpose of BAGGING in ensemble methods?<br/>
To REDUCE prediction VARIANCE by averaging multiple models.

- What is the main goal of BOOSTING in ensemble modeling?<br/>
To REDUCE prediction ERROR and BIAS by correcting previous errors.

![Bagging and Boosting](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Bagging%20and%20Boosting.png)

- Random forests use bagging to train multiple decision trees on bootstrapped data, improving accuracy by reducing variance.

- Paula is using the AdaBoost algorithm for her machine learning project. She observes that her model improves progressively by focusing on correcting past errors. What is the primary goal of the AdaBoost algorithm?
To create a single strong learner from a series of weak learners by reducing bias



[Lab_Multi-class Classification](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%203_Building%20Supervised%20Learning%20Models/Lesson%201_Classification%20and%20Regression/Lab_Multi-class%20Classification.ipynb)

[Lab_Decision Trees](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%203_Building%20Supervised%20Learning%20Models/Lesson%201_Classification%20and%20Regression/Lab_Decision%20Trees.ipynb)

[Lab_Regression Trees](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%203_Building%20Supervised%20Learning%20Models/Lesson%201_Classification%20and%20Regression/Lab_Regression%20Trees.ipynb)

[Lab_Credit Card Fraud Detection with Decision Trees and SVM.](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%203_Building%20Supervised%20Learning%20Models/Lesson%202_Other%20Supervised%20Learning%20Models/Lab_Credit%20Card%20Fraud%20Detection%20with%20Decision%20Trees%20and%20SVM.ipynb)

[Lab_K-Nearest Neighbors Classifier](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%203_Building%20Supervised%20Learning%20Models/Lesson%202_Other%20Supervised%20Learning%20Models/Lab_K-Nearest%20Neighbors%20Classifier.ipynb)

[Lab_Random Forests and XGBoost](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%203_Building%20Supervised%20Learning%20Models/Lesson%202_Other%20Supervised%20Learning%20Models/Lab_Random%20Forests%20and%20XGBoost.ipynb)


