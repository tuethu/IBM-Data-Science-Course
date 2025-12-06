# Summary: Basic and Specialized Visualization Tools

Congratulations! You have completed this module. At this point in the course, you know: 

## AREA PLOT

- An area plot depicts cumulated totals using PERCENTAGES or NUMBERS over time. 

- Area plots are like a line plot but with the area below the line filled with color to emphasize the cumulative magnitude of the variables.

![Area Plots](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%202_Basic%20and%20Specialized%20Visualization%20Tools/Lesson%201_Basic%20Visualization%20Tools/Area%20Plots.png)

## HISTOGRAM

- A histogram is a way of representing the FREQUENCY distribution of a  NUMERIC dataset

- In a Histogram, the VERTICAL axis is the frequency or the number of data points in each bin.

   - The way it works is it partitions the x-axis into bins, assigns each data point in our dataset to a bin, and then counts the number of data points that have been assigned to each bin.
   - So the y-axis is the frequency or the number of data points in each bin. Note that we can change the bin size and usually one needs to tweak it so that the distribution is displayed nicely.

- The first step when creating a histogram in matplotlib is to import matplotlib as mpl and its scripting interface as plt

![Histograms](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%202_Basic%20and%20Specialized%20Visualization%20Tools/Lesson%201_Basic%20Visualization%20Tools/Histograms.png)

## BAR CHART

- A BAR CHART is a type of plot where the length of each bar is proportional to the value of the item that it represents


## PIE CHART

- A pie chart is a circular statistical graphic, divided into SEGMENTS, to illustrate numerical proportion.
  
- The process of creating a pie chart involves importing Matplotlib to represent a large set of data over a period of time.


[Hands-on Lab_Area Plots, Histograms, and Bar Charts](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%202_Basic%20and%20Specialized%20Visualization%20Tools/Lesson%201_Basic%20Visualization%20Tools/Hands-on%20Lab_Area%20Plots%2C%20Histograms%2C%20and%20Bar%20Charts.ipynb)

[Hands-on Lab_Pie Charts, Box Plots, Scatter Plots, and Bubble Plots](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%202_Basic%20and%20Specialized%20Visualization%20Tools/Lesson%202_Specialized%20Visualization%20Tools/Hands-on%20Lab_Pie%20Charts%2C%20Box%20Plots%2C%20Scatter%20Plots%2C%20and%20Bubble%20Plots.ipynb)

## BOX PLOT
- A box plot is a way of statistically representing given data distribution through FIVE main dimensions. These include Minimum, First quartile, Median, Third quartile, and Maximum.

- The five main dimensions are minimum, first quartile, median, third quartile, and maximum.

- The first step is to import the library. You Import MATPLOTLIB.PYPLOT as plt.

Careful: KIND = 'plot type', not Type = 'plot type'
DataFrame.plot.box()
DataFrame.plot(kind = ‘box’)

- The combination of function and parameter to create a box plot in Matplotlib is:
Function = plot, and Parameter = kind with value = "box" 


## SCATTER PLOT

- A scatter plot displays values pertaining to typically TWO variables against each other.

- The process of creating a scatter plot involves importing MATPLOTLIB to visualize a large set of data.


### MATPLOTLIB

- Matplotlib is a general-purpose comprehensive plotting library. Its PYPLOT module offers a convenient way to create and customize plots quickly.

- Matplotlib’s Pyplot module offers a convenient way to create and customize plots quickly.

[Hands-on Lab_Plotting Directly with Matplotlib](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%202_Basic%20and%20Specialized%20Visualization%20Tools/Lesson%202_Specialized%20Visualization%20Tools/Hands-on%20Lab_Plotting%20Directly%20with%20Matplotlib.ipynb)

### Two types of plotting
There are two styles/options of plotting with matplotlib， plotting using the Artist layer and plotting using the scripting layer.

1. Scripting layer (procedural method) - using matplotlib.pyplot as 'plt'

You can use plt i.e. matplotlib.pyplot and add more elements by calling different methods procedurally; for example, plt.title(...) to add title or plt.xlabel(...) to add label to the x-axis.
```
    # Option 1: This is what we have been using so far
    df_top5.plot(kind='area', alpha=0.35, figsize=(20, 10)) 
    plt.title('Immigration trend of top 5 countries')
    plt.ylabel('Number of immigrants')
    plt.xlabel('Years')
```    
2.  Artist layer (Object oriented method) - using an Axes instance from Matplotlib (preferred)

You can use an Axes instance of your current plot and store it in a variable (eg. ax). You can add more elements by calling methods with a little change in syntax (by adding "set_" to the previous methods). 

For example, use ax.set_title() instead of plt.title() to add title, or ax.set_xlabel() instead of plt.xlabel() to add label to the x-axis.

This option sometimes is more transparent and flexible to use for advanced plots (in particular when having multiple plots, as you will see later).

- Data Storytelling is the ‘art of storytelling’ that involves creating a narrative around the data.

- Data visualization is an important aspect of data storytelling and involves creating engaging visuals.
