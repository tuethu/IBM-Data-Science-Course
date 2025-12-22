- A finance company has designed a model differentiating fraud, non-fraud, and suspicious categories for real-time transaction alerts. How does the one-versus-all classification strategy help them to construct a multi-class model using binary classifiers?<br/>
o To extend binary classifiers to handle multiple classes<br/>
(The one-versus-all strategy is a method to adapt binary classifiers for multi-class classification by training each classifier to recognize a single class against all others.)

- You want to predict used car prices in your model. Your dataset includes a few expensive cars that bias the price distribution. Why should you leverage the median rather than the mean at the leaf nodes to gain accurate predictions?<br/>
o The median is robust to outliers and skewed data.<br/>
(The median is less sensitive to the influence of outliers and skewed data, making it a better choice for this scenario.)

- You want to build a stock price prediction model and shift from linear regression to more complex models such as polynomial regression and random forests. How do bias and variance change as model complexity increases?<br/>
o Bias decreases, and variance increases<br/>
(As you make the model more complex, it can capture more details (decreasing bias), but it also becomes more sensitive to small changes in the data (increasing variance).)

- You are managing a network security system and want to enhance monitoring by identifying activity that doesn’t match usual patterns. Machine learning can assist with this goal. Which machine learning task is the most relevant?<br/>
o Spotting traffic patterns that deviate from the norm<br/>
(Anomaly detection is commonly used to identify unexpected behavior in network activity.)

- Which regression model should investors use to analyze their portfolio's rapid growth?<br/>
o Exponential regression<br/>
(Exponential regression models, such as compound growth, increase the growth rate over time.)

- Which of the following models is best suited for binary classification when the decision boundary is based on the proximity of a data point to its neighbors?<br/>
o K-nearest neighbors (KNN)<br/>
(K-nearest neighbors (KNN) is particularly useful when classification depends on proximity. The model classifies a data point based on its closest neighbors, making it an effective choice for tasks where decision boundaries are influenced by local similarity.)

- A machine learning engineer wants to reduce the dimensions of a feature-rich gene expression dataset before applying clustering. Why would they apply PCA first?<br/>
o To transform correlated features into principal components<br/>
(PCA utilizes orthogonal primary components, making it suitable for preprocessing clustering.)

- A machine learning engineer uses large datasets to train a logistic regression model. They want an algorithm that scales well and is faster than standard gradient descent to reduce the cost function efficiently. Which method should they choose in this scenario?<br/>
o Stochastic gradient descent<br/>
(Stochastic gradient descent is a scalable variation of the gradient descent algorithm, which uses a random subset of training data.)

- The healthcare industry wants to predict which patients need urgent treatment using a logistic regression model. However, many low-risk patients are flagged as high-risk, leading to low manpower. How can the healthcare industry reduce the false positives in the model?<br/>
o Fine-tune the decision boundary<br/>
(Tailoring the decision boundary can adjust the sensitivity in the model, reducing false positives while maintaining overall performance.)

- An ecologist studies animal movement data to identify regions where certain animals cluster. They need a clustering method to find irregularly shaped clusters based on areas with a high density of points, representing areas the animals frequently visit. Which method would be most suitable?<br/>
o Density-based clustering<br/>
(Density-based clustering identifies clusters based on high point density areas, making it suitable for irregular shapes.)

- Why is DBSCAN well-suited for marketing teams seeking to cluster customers and uncover irregular spending patterns? <br/>
o To identify outliers <br/>
( DBSCAN is a density-based clustering algorithm that forms clusters based on dense regions of data and marks low-density points as outliers. ) 

- Which dimensionality reduction algorithm is commonly used for visualizing nonlinear high-dimensional data because it preserves both local and global structure?  <br/>
o Uniform Manifold Approximation and Projection (UMAP)<br/>
( UMAP is a non-linear dimensionality reduction technique that reduces high-dimensional data into 2-D or 3-D space while preserving both local and global structure of the data. It is widely used for visualization, clustering, and feature exploration.  )

- Neo is creating an interactive dashboard to help stakeholders visualize key machine learning insights from model results and performance metrics. Which tool will help him in this scenario?<br/>
o Matplotlib<br/>
(Matplotlib is ideal for visualizations, such as creating custom plots to understand model behavior and data trends.)

- What are the primary benefits of using machine learning instead of rule-based systems?<br/>
o It learns patterns from data without explicit programming.<br/>
(Machine learning teaches computers to learn from data, identify patterns, and make decisions without receiving explicit instructions from a human.)

- Taniya is designing a machine learning pipeline and wants a tool to preprocess data, build models, validate performance, and export results for deployment within a Python ecosystem. Which tool best supports this end-to-end functionality?<br/>
o Scikit-learn<br/>
(Scikit-learn provides integrated functions for preprocessing, training, evaluation, validation, and export in Python-based machine learning workflows.)

