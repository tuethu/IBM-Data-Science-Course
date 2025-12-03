# Summary: Introduction to Data Visualization Tools

Congratulations! You have completed this module. At this point in the course, you know: 

- Data visualization is the process of presenting data in a visual format, such as charts, graphs, and maps, to help people understand and analyze data easily. 

- Data visualization has diverse use cases, such as in business, science, healthcare, and finance. 

- It is important to follow best practices, such as selecting appropriate visualizations for the data being presented, choosing colors and fonts that are easy to read and interpret, and minimizing clutter.

## Python Plot Types 
![Python Charts](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%201_Introduction%20to%20Data%20Visualization%20Tools/Introduction%20to%20Data%20Visualization/Python%20Charts.webp)

- There are various types of plots commonly used in data visualization.

- Line plots capture trends and changes over time, allowing us to see patterns and fluctuations.
  
- Line plot is one of the most basic type of chart and is common in many fields.
  
- A line plot is a plot in the form of a series of data points connected by straight line segments. 

- You can generate a line plot by assigning "line" to 'Kind' parameter in the plot() function.
  
- In order to start creating different types of plots of the data, you will need to import the data into a Pandas DataFrame.
  
```
# Compare the number of immigrants from India and China from 1980 to 2013.
years = list(map(str, range(1980, 2013)))
df_IC = df_can.loc[['India', 'China'], years] # passing in years 1980 - 2013 to exclude the 'total' column
df_IC.head()

df_IC = df_IC.transpose() # swap the row and columns
df_IC.head()

df_IC.index = df_IC .index.map(int) ####### import the data into a Pandas DataFrame to create different types of plots of the data
df_IC.plot(kind='line') ####### generate a line plot

plt.title('Immigration from China and Indiai')
plt.ylabel('Number of immigrants')
plt.xlabel('Years')

plt.show()
```
 
- Bar plots compare categories or groups, providing a visual comparison of their values.

- Scatter plots explore relationships between variables, helping us identify correlations or trends.

- Box plots display the distribution of data, showcasing the median, quartiles, and outliers.

- Histograms illustrate the distribution of data within specific intervals, allowing us to understand its shape and concentration.

- The anatomy of a plot refers to the different components and elements that make up a visual representation of data.
  
- Jupyter Notebook is an open-source web application that allows you to create and share documents.

## Python Data Visualization Libraries
![Python Data Visualization Libraries](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%201_Introduction%20to%20Data%20Visualization%20Tools/Introduction%20to%20Data%20Visualization/Python%20Data%20Visualization%20Libraries.png)

- Pandas is a plotting library that provides Integrated plotting functionalities for data analysis.
  
- Seaborn is a specialized library for statistical visualizations, offering attractive default aesthetics and color palettes.

- Folium is a Python library that allows you to create interactive and customizable maps.

- Plotly is an interactive and dynamic library for data visualization that supports a wide range of plot types and interactive features.

- PyWaffle enables you to visualize proportional representation using squares or rectangles.

### Matplotlib

- Matplotlib is a plotting library that offers a wide range of plotting capabilities.

- Matplotlib is one of the most widely used data visualization libraries in Python.

- You can easily include the label and title to your plot with plt.

```
%matplotlib inline 

import matplotlib as mpl
import matplotlib.pyplot as plt ###  include the label and title to the plot
```

- Matplotlib was initially developed as an EEG/ECoG visualization tool. 

- Matplotlib’s architecture is composed of three main layers: Backend layer, Artist layer, and the Scripting layer.
  

![Matplotlib Architecture](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%201_Introduction%20to%20Data%20Visualization%20Tools/Introduction%20to%20Data%20Visualization/Matplotlib%20Architecture.png)

- Matplotlib is a well-established data visualization library that can be integrated in different environments. 

- Matplotlib has a number of different backends available.

  




[Cheat Sheet: Data Preprocessing Tasks in Pandas & Plot Libraries](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstRFYwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL3Y0L0RWMDEwMUVOLUNoZWF0U2hlZXQtMS5tZD90PTE3NTAzMzEwNTciLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjM1MTU1LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzY5NDU1OH0.CwwmMVofPuex6A4yxMrAikfMdXimYm0AfCWwN-lDWgI)
