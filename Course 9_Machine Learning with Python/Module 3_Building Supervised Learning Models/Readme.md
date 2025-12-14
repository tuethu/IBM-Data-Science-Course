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

## Decision Tree
- A decision tree classifies data by testing features at each node, branching based on test results, and assigning CLASSES at LEAF nodes.
![Decision Tree](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Decision%20tree.png)

- In a decision tree, what does each leaf node represent?<br/>
A class label

- Decision tree training involves selecting features that best split the data and PRUNING the tree to AVOID OVERFITTING.

![Pruning Decision tree](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Pruning%20Decision%20tree.png)

- Information gain and Gini impurity are used to measure the quality of splits in decision trees.
![Entropy and Information gain ](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Entropy%20and%20Information%20gain.png)

- Regression trees are similar to decision trees but predict continuous values by recursively splitting data to maximize information gain.

- What is the primary goal of a regression tree?<br/>
To predict continuous values based on features

![Regression tree](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Regression%20tree.png)

- Mean Squared Error (MSE) is used to measure split quality in regression trees.

- K-Nearest Neighbors (k-NN) is a supervised algorithm used for classification and regression by assigning labels based on the closest labeled data points.

- To optimize k-NN, test various k values and measure accuracy, considering class distribution and feature relevance.

- Support Vector Machines (SVM) build classifiers by finding a hyperplane that maximizes the margin between two classes, effective in high-dimensional spaces but sensitive to noise and large datasets.

- The bias-variance tradeoff affects model accuracy, and methods such as bagging, boosting, and random forests help manage bias and variance to improve model performance.

- Random forests use bagging to train multiple decision trees on bootstrapped data, improving accuracy by reducing variance.

[Lab_Multi-class Classification](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%203_Building%20Supervised%20Learning%20Models/Lesson%201_Classification%20and%20Regression/Lab_Multi-class%20Classification.ipynb)

[Lab_Decision Trees](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%203_Building%20Supervised%20Learning%20Models/Lesson%201_Classification%20and%20Regression/Lab_Decision%20Trees.ipynb)

[Lab_Regression Trees](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Module%203_Building%20Supervised%20Learning%20Models/Lesson%201_Classification%20and%20Regression/Lab_Regression%20Trees.ipynb)

