# Module 1 Summary: Data Science and Generative AI   

Congratulations! You have completed this module. At this point, you know that: 

- The four common AI models are generative adversarial networks (GANs), variational autoencoders (VAEs), autoregressive, and flow-based models.
- 
- While GANs are great at data augmentation, VAEs are good at anomaly detection, data compression, collaborative filtering, and style transfer. 

## 1. Generative adversarial networks (GANs)
- Which tool is used for synthetic tabular data generation? <br/>
GAN

- Which generative AI model consists of two neural networks, generator, and discriminator?<br/>
GANs
- Which type of generative AI models consist of two neural networks, which give them the ability to generate remarkably realistic and diverse data?<br/>
Generative adversarial networks (GANs)<br/>
GANs consist of two neural networks, a generator that produces increasingly realistic data and a discriminator that distinguishes between real and fake samples.

- Which of the following tools is used to augment the unstructured data set?<br/>
BigGAN
Unstructured data includes images and audio. BigGAN has remarkable capabilities in augmenting image data sets by generating high-resolution, realistic images.
![Generative adversarial networks (GANs)](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/Generative%20adversarial%20networks%20(GANs).png)

## 2. Variational autoencoders (VAEs)
- Which generative AI models are good at COMPRESSING the size of data sets without compromising on information content?<br/>
Variational autoencoders (VAEs) <br/>
VAEs can compress the size of data sets, making them suitable for handling large data sets.
![Variational autoencoders (VAEs)](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/Variational%20autoencoders%20(VAEs).png)

- Autoregressive models are good at text generation, speech synthesis, time series forecasting, and machine translation, and flow-based models are suitable for image and data generation and density estimation.  

## 3. Autoregressive model
- Which type of generative AI models are known as SEQUENTIAL data champions?<br/>
Autoregressive models<br/>
They excel in generating data one element at a time.
![Autoregressive model](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/Autoregressive%20model.png)

## 4. Flow-based model
- What makes flow-based models efficient in SAMPLING?<br/>
They can perform direct modeling of the probability distribution of data.<br/>
Flow-based models are efficient in sampling because they can directly model the probability distribution of data.
![Flow-based model](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/Flow-based%20model.png)

- Generative AI can tackle complex problems across various industries. 

- Generative AI models are instrumental in tackling several data preparation and querying challenges, such as imputation of missing values, detecting outliers, reducing “noise,” and translating natural language queries into equivalent SQL statements.


## Example of Generative AI for Data Preparation

```
Building the prompt: Importing the data set
Write a Python code that can perform the following tasks.
Read the CSV file, located on a given file path, into a Pandas data frame, assuming that the first rows of the file are the headers for the data.
```

```
Building the prompt: Handle missing data
Write a Python code that identifies the columns with missing values in a pandas data frame and gives missing value counts per column.
```

```
Write a Python code to replace the missing values in a pandas data frame, per the following guidelines.
1. For a categorical attribute "Screen_Size_cm", replace the missing values with the most frequent value in the column.
2. For a continuous value attribute "Weight_kg", replace the missing values with the mean value of the entries in the column.

```

```
Building the prompt: Modify data type
Write a Python code snippet to change the data type of the attributes "Screen_Size_cm" and "Weight_kg" of a data frame to float.
```

```
Building the prompt: Standardization and Normalization
Write a Python code to modify the contents under the following attributes of the data frame as required.
1. Data under 'Screen_Size_cm' is assumed to be in centimeters. Convert this data into inches. Modify the name of the attribute to 'Screen_Size_inch'.
2. Data under 'Weight_kg' is assumed to be in kilograms. Convert this data into pounds. Modify the name of the attribute to 'Weight_pounds'.
```

```
Write a Python code to normalize the content under the attribute "CPU_frequency" in a data frame df concerning its maximum value. Make changes to the original data, and do not create a new attribute.
```

```
Building the prompt: Categorical to numerical
Write a Python code to perform the following tasks.
1. Convert a data frame df attribute "Screen", into indicator variables, saved as df1, with the naming convention "Screen_<unique value of the attribute>".
2. Append df1 into the original data frame df.
3. Drop the original attribute from the data frame df.
```

## Example of Generative AI for Querying Databases

```
We have a Heart Disease prediction dataset with a single table which has the following attributes.
1. age - age in years
2. gender- gender (1 = male; 0 = female)
3. cp - chest pain type
        -- Value 1: typical angina
        -- Value 2: atypical angina
        -- Value 3: non-anginal pain
        -- Value 4: asymptomatic
4. trestbps - resting blood pressure (in mm Hg on admission to the hospital)
5. chol - serum cholestoral in mg/dl
6. fbs - (fasting blood sugar > 120 mg/dl)  (1 = true; 0 = false)
7. restecg - resting electrocardiographic results
        -- Value 0: normal
        -- Value 1: having ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV)
        -- Value 2: showing probable or definite left ventricular hypertrophy by Estes' criteria
8. thalach - maximum heart rate achieved
9. exang - exercise induced angina (1 = yes; 0 = no)
10. oldpeak - ST depression induced by exercise relative to rest
11. slope - the slope of the peak exercise ST segment
        -- Value 1: upsloping
        -- Value 2: flat
        -- Value 3: downsloping
12. ca - number of major vessels (0-3) colored by flourosopy
13. thal - 3 = normal; 6 = fixed defect; 7 = reversable defect
14. num (the predicted attribute) - diagnosis of heart disease (angiographic disease status)
        -- Value 0: < 50% diameter narrowing
        -- Value 1: > 50% diameter narrowing

```

```
Write an SQL query to find the minimum, maximum, and average age of patients in the dataset.
Write and SQL query to count the number of male and female patients in the dataset.
Write an SQL query to determine the frequency of each type of chest pain (typical angina, atypical angina, non-anginal pain, asymptomatic) among patients.
Write an SQL query to investigate the distribution of the target variable (presence or absence of heart disease) within different age groups (e.g., 20-30, 30-40, etc.).
```

![Generative AI for Data Preparation and Data Querying ](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/Generative%20AI%20for%20Data%20Preparation%20and%20Data%20Querying%20.png)

- Which tool is used for image data augmentation?<br/>
Neural style transfer
![Data Generation and Augmentation](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%2011_Generative%20AI_Elevate%20Your%20Data%20Science%20Career/Media/Data%20Generation%20and%20Augmentation.png)

- In which phase of the data science lifecycle will you extract patterns and insights from the data by selecting and training appropriate machine learning algorithms?<br/>
Modeling and feature engineering

- Which generative AI tool enables human-like interactions through chatbots, assistants, and avatars?<br/>
Dialogflow

- How does Synthetic Data Vault (SDV) augment structured data set?<br/>
By generating synthetic data


- How does generative AI make it easier to query databases?<br/>
Enables users to query databases in natural language

- Which of the following SQL queries will generate if you type “What is the count of rows in the Boston_house_price data set” in the prompt box of a generative AI SQL query tool?<br/>
SELECT COUNT * FROM Boston_house_price

- What do you mean by data preparation?<br/>
Cleaning, transforming, and organizing raw data

- How do generative AI models help discover new drugs?<br/>
By analyzing the molecular structures of known medications and their impact on biological targets<br/>
Generative AI models can analyze the molecular structures of known medications and their impact to predict new drug candidates with the required properties.

- Generative AI models that can create synthetic images and modify visual attributes are best suited for which task?<br/> 
Creating unique designs and enhancing creative workflows in the fashion industry<br/>
These models can create synthetic images and modify visual attributes, tasks unique to the fashion industry.

- How do generative AI models help manage financial risks? <br/>
By simulating scenarios such as market crashes or economic downturns<br/>
Generative AI models can simulate various financial scenarios to assess financial risks and develop strategies to minimize losses.

- How does generative AI help data scientists augment their data?<br/>
It allows them to create synthetic data that mimics the real data.<br/>
Data scientists use synthetic and real data for model training and testing.

- How do generative AI models tackle the challenge of detecting outliers?<br/>
By learning the boundaries of the standard data distribution.<br/>
Generative AI models have two competing neural networks: one produces synthetic data, and the other distinguishes between natural and synthetic data. This adversarial process enables them to identify outliers.

- How do generative AI models tackle the challenge of missing values in a data set?<br/>
By learning the underlying data patterns and generating plausible values that align with them.<br/>
Generative AI models learn the intricate patterns within the data and generate plausible values.

[Cheatsheet: Data Science and Generative AI](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQUkwMjcxRU4tU2tpbGxzTmV0d29yay9sYWJzL3JlYWRpbmcvdjEvbTEvY2hlYXRzaGVldF9tb2QxLm1kP3Q9MTc0NjEyMzQzMiIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6MzYwMTAsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3Njk0NTY0fQ.eGdl5fAQ7iLfVwmv-G8TsjB2fyNX_8zfgnubskq4o_o)

[Generative AI Tools for Data Scientists](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQUkwMjcxRU4tU2tpbGxzTmV0d29yay9sYWJzL3JlYWRpbmcvdjEvbTEvR2VuX0FJX1Rvb2xzX2Zvcl9EYXRhX1NjaWVudGlzdHMubWQ_dD0xNzQ2MTIzNDc5IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjozNTk4NCwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc2OTQ1NjN9.eQ6bpNrolVV23DqVIqyy13Z0I33HB8sN6Kremf_UQ50)

[Reading: Guide to Choosing a Generative AI Model Type](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQUkwMjcxRU4tU2tpbGxzTmV0d29yay9sYWJzL3JlYWRpbmcvdjEvbTEvR3VpZGVfZ2VuQUlfdG9vbHMubWQ_dD0xNzQ2MTIzNDc0IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjozNjAxNCwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc2OTQ1NjR9.fLupL4X32fJ0kbu9zPGoAAvgfsBuH_aqv8CmCskvVqA)

[Case Study: Successful Implementation of Generative AI](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQUkwMjcxRU4tU2tpbGxzTmV0d29yay9sYWJzL3JlYWRpbmcvdjEvbTEvQ2FzZV9zdHVkeV9TdWNjZXNzZnVsX0ltcGxlbWVudGF0aW9uc19vZl9HZW5fQS5tZD90PTE3NDYxMjM0ODgiLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjM1OTg2LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzY5NDU2M30.ylF-JxZDzoTDOGaV6dweUSRr9NHykkLH9F6BF4kNAnY)

[Lab: Explore a Simple Generative Tool-DataRobot](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQUkwMjcyRU4tU2tpbGxzTmV0d29yay9sYWJzL0hhbmRzLU9uX0xhYiUzQV9HZXR0aW5nX0hhbmRzLW9uX3dpdGhfYV9TaW1wbGVfR2VuZXJhdGl2ZV9Nb2RlLm1kP3Q9MTc0NjEyMjIyOCIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6Mjk5NzcsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3Njk0NDE2fQ.eFmNMVw_9FmY828VslYvm5opctrK1a2nq4xSxJq-piA)

[Hands-on Lab: Generative AI for Data Generation and Augmentation- Mostly.ai](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQUkwMjcxRU4tU2tpbGxzTmV0d29yay9sYWJzL3YxL20xL0dlbkFJX2RhdGFfYXVnbWVudC5tZD90PTE3NTY3MjYyODMiLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjM1OTk2LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzY5NDU2M30.smxew-1QR1DC-bLCZxt5RIdYvAokFAJvD8bGHBOZIxI)

[Hands-on Lab: Generative AI for Data Preparation](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQUkwMjcxRU4tU2tpbGxzTmV0d29yay9sYWJzL20xL2wyL0dlbkFJX0RhdGFfUHJlcC5tZD90PTE3NTk3NDUxNzMiLCJ0b29sX3R5cGUiOiJhaS1jbGFzc3Jvb20iLCJhdGxhc19maWxlX2lkIjozNTk3NiwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTk3NDUxNzR9.xBTVP8yzbEJ2lOld2E1nawVCeZ8MP1yARMK8tK2UAI4)

[Hands-on Lab: Generative AI for Querying Databases](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTVNraWxsc05ldHdvcmstQUkwMjcxRU4tU2tpbGxzTmV0d29yay9sYWJzL3YxL20yL2RhdGFfcXVlcnlpbmcubWQ_dD0xNzU4NzkwMjgxIiwidG9vbF90eXBlIjoiYWktY2xhc3Nyb29tIiwiYXRsYXNfZmlsZV9pZCI6MjgyMDMsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU4NzkwMjgxfQ.W6D99QlSIODYwyWjHPEszapc-CTKYzrIH7ndQ0HIsPc)





