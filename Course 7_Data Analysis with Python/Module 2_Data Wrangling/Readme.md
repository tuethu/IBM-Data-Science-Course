# Lesson Summary

Congratulations! You have completed this lesson. At this point in the course, you know:

- Data formatting is critical for making data from various sources consistent and comparable.
- What is the purpose of data wrangling/ cleaning? to convert data from an initial format to a format that may be better for analysis.

## Deal with missing data

1. Drop data
   - a. Drop the whole row
   - b. Drop the whole column
```   
df.drop("aspiration", axis = 1, inplace=True)
```

2. Replace data
   - a. Replace it by mean
     
```
     #Replace NaN in "stroke" column with the mean value
     avg_horsepower = df['horsepower'].astype('float').mean(axis=0)
     df.replace({"horsepower": {np.nan: avg_horsepower }}, inplace=True)
```

   - b. Replace it by frequency
```
common_screen_size = df['Screen_Size_cm'].value_counts().idxmax()
df.replace({'Screen_Size_cm': {np.nan: common_screen_size}}, inplace=True)
print("Average of Screen Size:", common_screen_size)
```

   - c. Replace it based on other functions

- Master the techniques in Python to convert units of measurement, like transforming "city miles per gallon" to "city-liters per 100 kilometers" for ease of comparison and analysis.
```
# Convert mpg to L/100km by mathematical operation (235 divided by mpg) L/100km = 235 / mpg
df['city-L/100km'] = 235/df["city-mpg"]
```

- Acquire skills to identify and correct data types in Python, ensuring the data is accurately represented for subsequent statistical analyses.

```
#In Pandas, you use:
.dtype() to check the data type
.astype() to change the data type
#Convert data types to proper format
df[["bore", "stroke"]] = df[["bore", "stroke"]].astype("float")
df[["normalized-losses"]] = df[["normalized-losses"]].astype("int")
```

- Data normalization helps make variables comparable and helps eliminate inherent biases in statistical models.
  
```
#Often it is required to normalize a continuous data attribute. Write a code to normalize the "CPU_frequency" attribute with respect to the maximum value available in the dataset.
df['CPU_frequency'] = df['CPU_frequency'] / df['CPU_frequency'].max()
print("CPU_frequency column:\n", df['CPU_frequency'])
```
- You can apply Feature Scaling, Min-Max, and Z-Score to normalize data and apply each technique in Python using pandas’ methods.

- Binning is a method of data pre-processing to improve model accuracy and data visualization. Binning is a process of creating a categorical attribute which splits the values of a continuous data into a specified number of groups. 

- Run binning techniques in Python using numpy's "linspace" and pandas' "cut" methods, particularly for numerical variables like "price."
```
bins = np.linspace(min(df["Price"]), max(df["Price"]), 4)
group_names = ['Low', 'Medium', 'High']
df['Price-binned'] = pd.cut(df['Price'], bins, labels=group_names, include_lowest=True )
```

- Utilize histograms to visualize the distribution of binned data and gain insights into feature distributions.
```
plt.bar(group_names, df["Price-binned"].value_counts())
plt.xlabel("Price")
plt.ylabel("count")
plt.title("Price bins")
```
- Statistical models generally require numerical inputs, making it necessary to convert categorical variables like "fuel type" into numerical formats.

- You can implement the one-hot encoding technique in Python using pandas’ get_dummies method to transform categorical variables into a format suitable for machine learning models.
```
dummy_variable_1 = pd.get_dummies(df["Screen"])
dummy_variable_1.rename(columns={'IPS Panel':'Screen-IPS_panel', 'Full HD':'Screen-Full_HD'}, inplace=True)
df = pd.concat([df, dummy_variable_1], axis=1)
df.drop("Screen", axis = 1, inplace=True)
```

[Cheat Sheet: Data Wrangling](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREEwMTAxRU4tQ291cnNlcmEvbGFicy8yMDA1NDIuMDk0X00yX0NoZWF0X1NoZWV0Lm1kP3Q9MTc0NjExODg1OSIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6MTE1NjksImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3NDQ4MzM2fQ.IQNQVUq6nxLR7CcjQPkQJc2EEgXJy34gTY-nDPJiAVw)
