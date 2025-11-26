# Lesson Summary

Congratulations! You have completed this lesson. At this point in the course, you know: 

- Tools like the 'describe' function in pandas can quickly calculate key statistical measures like mean, standard deviation, and quartiles for all numerical variables in your data frame. 

- Use the 'value_counts' function to summarize data into different categories for categorical data. 
Value counts is a good way of understanding how many units of each characteristic/variable we have. We can apply the "value_counts" method on the column "drive-wheels". Don’t forget the method "value_counts" only works on pandas series, not pandas dataframes. As a result, we only include one bracket df['drive-wheels'], not two brackets df[['drive-wheels']]

```
df['drive-wheels'].value_counts()
```

- Box plots offer a more visual representation of the data's distribution for numerical data, indicating features like the median, quartiles, and outliers.
```
sns.boxplot(x="body-style", y="price", data=df)
```

- Scatter plots are excellent for exploring relationships between continuous variables, like engine size and price, in a car data set.
```
sns.regplot(x="stroke", y="price", data=df)
```

- Use Pandas' 'groupby' method to explore relationships between categorical variables.
```
df['drive-wheels'].unique()
df_group_one = df[['drive-wheels','body-style','price']]
df_grouped = df_group_one.groupby(['drive-wheels'], as_index=False).agg({'price': 'mean'})
df_grouped
```

- Use pivot tables and heat maps for better data visualizations.
```
grouped_pivot = grouped_test1.pivot(index='drive-wheels',columns='body-style')
```

- Correlation between variables is a statistical measure that indicates how the changes in one variable might be associated with changes in another variable.

- When exploring correlation, use scatter plots combined with a regression line to visualize relationships between variables.

- Visualization functions like regplot, from the seaborn library, are especially useful for exploring correlation.

- The Pearson correlation, a key method for assessing the correlation between continuous numerical variables, provides two critical values—the coefficient, which indicates the strength and direction of the correlation, and the P-value, which assesses the certainty of the correlation.
The Pearson Correlation measures the linear dependence between two variables X and Y.
The resulting coefficient is a value between -1 and 1 inclusive, where:
1: Perfect positive linear correlation.
0: No linear correlation, the two variables most likely do not affect each other.
-1: Perfect negative linear correlation.
  
```
df.select_dtypes(include=['number']).corr()
```

- For P-values, values less than .001 indicate strong certainty in the correlation, while larger values indicate less certainty. Both the coefficient and P-value are important for confirming a strong correlation.
The P-value is the probability value that the correlation between these two variables is statistically significant. Normally, we choose a significance level of 0.05, which means that we are 95% confident that the correlation between the variables is significant.

By convention, when the

p-value is 
 0.001: we say there is strong evidence that the correlation is significant.
the p-value is 
 0.05: there is moderate evidence that the correlation is significant.
the p-value is 
 0.1: there is weak evidence that the correlation is significant.
the p-value is 
 0.1: there is no evidence that the correlation is significant.

```
 pearson_coef, p_value = stats.pearsonr(df['wheel-base'], df['price'])
 ```

- Heatmaps provide a comprehensive visual summary of the strength and direction of correlations among multiple variables.
```
fig, ax = plt.subplots()
im = ax.pcolor(grouped_pivot, cmap='RdBu')

#label names
row_labels = grouped_pivot.columns.levels[1]
col_labels = grouped_pivot.index

#move ticks and labels to the center
ax.set_xticks(np.arange(grouped_pivot.shape[1]) + 0.5, minor=False)
ax.set_yticks(np.arange(grouped_pivot.shape[0]) + 0.5, minor=False)

#insert labels
ax.set_xticklabels(row_labels, minor=False)
ax.set_yticklabels(col_labels, minor=False)

#rotate label if too long
plt.xticks(rotation=90)

fig.colorbar(im)
plt.show()
```

[Data Visualization commands in Python](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREEwMTAxRU4tQ291cnNlcmEvbGFicy92NC9QbG90dGluZ19mdW5jdGlvbnMubWQ_dD0xNzQ2MTE4OTU3IiwidG9vbF90eXBlIjoiaW5zdHJ1Y3Rpb25hbC1sYWIiLCJhdGxhc19maWxlX2lkIjoxMTU3OSwiYWRtaW4iOmZhbHNlLCJpYXQiOjE3NTc0NDgzNDB9.NLggFfb-7UjlY3Ey1S4d0rZ_CmNFU2MakCVPqbvoTRA)

[Chi-Square Test for Categorical Variables](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL09FalYxZlpCcTV0U2tRbi1DbzktNWcvY2hpLXNxYXVyZS10ZXN0LXYxLm1kP3Q9MTc1MDIzMTIxMSIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6NjExNTQsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3Njk1NzkwfQ.gxQudjESyrIpQjfQJAQ27szszrWWW6IVRxMlQkYNanE)

[Cheat Sheet: Exploratory Data Analysis](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstREEwMTAxRU4tQ291cnNlcmEvbGFicy8yMDA1NDIuMDQ5X00zX0NoZWF0X1NoZWV0Lm1kP3Q9MTc0NjExODg2OCIsInRvb2xfdHlwZSI6Imluc3RydWN0aW9uYWwtbGFiIiwiYXRsYXNfZmlsZV9pZCI6MTE1NzEsImFkbWluIjpmYWxzZSwiaWF0IjoxNzU3NDQ4MzM3fQ.S9fjj2MgSrkyPhCz8o8Ve8wi9TPQfiYTaBpopOQ1EYI)

