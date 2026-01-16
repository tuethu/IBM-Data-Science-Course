# Review What You Learned

In this course, you explored generative AI techniques and their applications in data science. You learned about integrating generative AI into data science projects, including data augmentation and feature engineering. You also learned how to use and apply generative models for tasks such as data generation, augmentation, preparation, querying, and more. 

Here are the key takeaways from this course: 

- Generative AI empowers data scientists to generate entirely new data, unlocking a universe of possibilities and tackling previously insurmountable challenges.

- There are four standard generative AI models: Generative adversarial networks (GANs), variational autoencoders (VAEs), autoregressive, and flow-based models.  

- While GANs are great at data augmentation, VAEs are good at anomaly detection, data compression, collaborative filtering, and style transfer. 

- Autoregressive models are good at text generation, speech synthesis, time series forecasting, and machine translation, and flow-based models are suitable for image and data generation and density estimation.  

- Generative AI can tackle complex problems across various industries. 

- Generative AI models are instrumental in tackling several data preparation and querying challenges, such as inputting missing values, detecting outliers, reducing “noise,” and translating natural language queries into equivalent SQL statements. 

- Generative AI can help in exploratory data analysis or EDA using various techniques, such as statistical data description, univariate, bivariate, multivariate analysis, feature engineering, and hypothesis generation. 

- Generative AI plays a significant role in developing a predictive model using various techniques, such as selecting model architecture and essential features, generating ensemble models, improving model interpretability and generalization, and preventing overfitting.

- While using generative AI models, data scientists need to look into data, models, and ethical considerations.

- Data professionals face various technical, organizational, and cultural challenges when using Generative AI in multiple industries. 

- Being a successful data scientist requires several skills, such as mathematical and statistical skills, knowledge of programming languages, and an understanding of machine learning principles.

- What is the purpose of generative adversarial networks (GANs)?<br/>
Creating realistic data SAMPLES

- Which of the following would be one of the ways generative AI can help data science professionals?<br/>
Augment their data sets using generative AI to create synthetic data.

- Which tool can be used for IMAGE DATA AUGMENTATION ?<br/>
CycleGAN<br/>
![CycleGAN](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/CycleGAN.png)

- During problem definition phase of data science lifecycle, how does generative AI help in idea generation?<br/>
By mimicking existing product descriptions, marketing campaigns, or successful solutions in other industries 

- Which generative AI model excels in handling SEQUENTIAL data?<br/>
AUTOGRESSIVE models

- Which generative AI model can generate coherent and grammatically correct poetry, scripts, and email?<br/>
Autoregressive models<br/>
![Autoregressive model](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/Autoregressive%20model%201.png)

- Which generative AI model generates new data that adheres to the original probability distribution?<br/>
Flow-based models

- Which of the following is a data consideration while using generative AI in industries?<br/>
Adhering to data privacy regulations, employing encryption techniques, and establishing clear data access protocols

- Which generative AI tool can augment semi-structured data sets by generating realistic text descriptions and code snippets?<br/>
Copilot

- Which prompt can you use for the following query: <br/>
UPDATE Boston_house_price SET ZN = NULL WHERE ZN = 0?<br/>
Replace the zero values in the ZN column with NULL. 

- How do generative AI models address the issue of inaccurate results produced by traditional imputation methods?<br/>
Learning intricate (complex) patterns within the data and generating plausible values

- Which of the following is a cultural challenge when using generative AI?<br/>
Trust and transparency

- How can you use visualization in a generative AI tool to verify outliers?<br/>
Generate box plots.

- Which generative AI tool is an open-source automated machine learning (AutoML) library that SIMPLIFIES the development and deployment of machine learning models?<br/>
AutoGluon<br/>
![AutoGluon](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/AutoGluon.png)

- Which generative AI analysis identifies potential patterns and relationships in the data that may warrant further investigation?<br/>
Hypothesis generation

- Which technique of model consideration is used to improve interpretability?<br/>
Feature attribution

- Which of the following is an organizational challenge while using generative AI?<br/>
Change management

- Which of the following is a SIMULATION and data augmentation generative AI tool?<br/>
Unity ML-Agents<br/>
![Unity ML-Agents](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/Unity%20ML-Agents.png)

- Which of the following is an ANOMALY DETECTION generative AI tool? <br/>
Isolation Forest<br/>
![Isolation Forest](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/Isolation%20Forest.png)

- How do generative AI tools help data scientists in data exploration and preparation? <br/>
Can detect and remove anomalies, fill in missing values, and handle outliers


[Final Project Overview](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQUkwMjcxRU4tU2tpbGxzTmV0d29yay9sYWJzL3JlYWRpbmcvdjEvbTMvZ3VpZGVkX3ByYWN0aWNlX3Byb2plY3Rfb3ZlcnZpZXcubWQ_dD0xNzQ2MTIzNDQwIiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjozNjAwNCwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc2OTQ1NjR9.WsQAibvL0erEPdJu2xx0knXFkqd4-ftCie7kqeSBOAM)

```
Importing the Dataset
Write a Python code that can perform the following tasks.
1. Read the CSV file, located on a given file path, into a pandas data frame, assuming that the first row of the file can be used as the headers for the data.
2. Print the first 5 rows of the dataframe to verify correct loading.
----------------------------------------------------------------------------------------------------
Data Cleaning
Write a Python code that performs the following tasks:
1. Identify the columns of a data frame with missing values.
2. Replace the missing values thus identified with mean value of the column.
3. Deletes the duplicate entries from the data frame.
----------------------------------------------------------------------------------------------------
Data Insights and Visualization
Write a Python code that identifies the top 5 attributes with highest correlation with the target attribute in a data frame.
Write a Python code that counts the number of entries in a dataframe with each unique value of a specific attribute.
Write a Python code that creates a Seaborn box plot between a source and target attributes of a dataframe.
Write a Python code that creates a regression plot between a source attribute and a target attribute.
----------------------------------------------------------------------------------------------------
Model Development and Evaluation
Write a Python code to fit a linear regression model on a target variable on basis of a source variable. Calculate the R^2 values and MSE values for this model.
Write a Python code to fit a linear regression model on a target variable on basis of a set of source variables. Calculate the R^2 values and MSE values for this model.

Write a Python code that can perform the following tasks.
1. Create a pipeline with standard scalar, second degree polynomial features and linear regression model.
2. Fit this pipeline for a target variable using a set of source attributes from a dataframe.
3. Evaluate the R^2 and MSE values for the trained model.

Write a Python code that can perform the following tasks.
1. Assuming that a subset of the attributes of a data frame are source attributes and one of the attributes is a target attribute, split the data into training and testing data assuming the testing data to be 20%.
2. Create and fit a Ridge regression model using the training data, setting the regularization parameter to 0.1.
3. Calculate the MSE and R^2 values for the Ridge Regression model using the testing data.

Write a Python code that can perform the following tasks.
1. Assuming that a subset of the attributes of a data frame are source attributes and one of the attributes is a target attribute, split the data into training and testing data assuming the testing data to be 20%.
2. Apply second degree polynomial scaling to the training and testing data.
3. Create and fit a Ridge regression model using the training data, setting the regularization parameter to 0.1.
4. Calculate the MSE and R^2 values for the Ridge Regression model using the testing data.

Write a Python code that can perform the following tasks.
1. Assuming that a subset of the attributes of a data frame are source attributes and one of the attributes is a target attribute, split the data into training and testing data assuming the testing data to be 20%.
2. Apply second degree polynomial scaling to the training and testing data.
3. Create and fit a Ridge regression model using the training data, setting the regularization parameter to 0.1.
4. Calculate the MSE and R^2 values for the Ridge Regression model using the testing data.

Write a Python code that can perform the following tasks.
1. Assuming that a subset of the attributes of a data frame are source attributes and one of the attributes is a target attribute, split the data into training and testing data assuming the testing data to be 20%.
2. Apply second degree polynomial scaling to the training and testing data.
3. Create and fit a Grid search on Ridge regression with cross validation using the training data, for a set of values of the parameter alpha.
4. Calculate the MSE and R^2 values for the Ridge Regression model using the testing data.

```

By the end of this project, you are now capable of using Generative AI for the tasks of:
- Data preparation: cleaning, transforming and augmentation
- Data analysis: drawing insight, creating visualizations
- Model development: creating simple as well as complex prediction models
- Model refinement: found the optimum model using Grid Search



