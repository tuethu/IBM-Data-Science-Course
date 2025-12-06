# Summary: Advanced Visualizations and Geospatial Data

Congratulations! You have completed this module. At this point in the course, you know: 

## WAFFLE CHARTS

- WAFFLE CHARTS are a visualization technique that represents categorical data in the form of square tiles or cells.
  
- The squares on a waffle chart represent  a specific value or category.

![Waffle Charts](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%203_Advanced%20Visualizations%20and%20Geospatial%20Data/Waffle%20Charts.png)
  
- Seaborn is another data visualization library, it is based on MATPLOTLIB.

- Seaborn provides specialized plot types such as regression, distribution, and categorical plots that are particularly useful for analyzing data and modeling relationships.

![Seaborn Regression Plot](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%203_Advanced%20Visualizations%20and%20Geospatial%20Data/Seaborn%20Regression%20Plot.png)

- SEABORN is a visualization library that provides a higher level interface for creating visually appealing and informative statistical graphics and deals with complex visualizations and statistical analysis.
  
- The easiest way to create a waffle chart in Python is using the Python package called PYWAFFLE

```
#install pywaffle
!pip install pywaffle

#import Waffle from pywaffle
from pywaffle import Waffle

#Set up the Waffle chart figure

fig = plt.figure(FigureClass = Waffle,
                 rows = 20, columns = 30, #pass the number of rows and columns for the waffle 
                 values = df_dsn['Total'], #pass the data to be used for display
                 cmap_name = 'tab20', #color scheme
                 legend = {'labels': [f"{k} ({v})" for k, v in zip(df_dsn.index.values,df_dsn.Total)],
                            'loc': 'lower left', 'bbox_to_anchor':(0,-0.1),'ncol': 3}
                 #notice the use of list comprehension for creating labels 
                 #from index and total of the dataset
                )

#Display the waffle chart
plt.show()
```

## WORD CLOUDS

- Word clouds (also known as text clouds or tag clouds) work in a simple way: the more a specific word appears in a source of textual data (such as a speech, blog post, or database), the bigger and bolder it appears in the word cloud.

  ![Word Clouds](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%203_Advanced%20Visualizations%20and%20Geospatial%20Data/Word%20Clouds.png)
  

## FOLIUM

- FOLIUM is a powerful data visualization library in Python that helps people visualize geospatial data.

- With Folium, you can create maps of different styles, such as street-level maps, stamen maps, and more. 

- A feature of Folium is that you can create different map styles using the tiles parameter.

- With Folium, you can easily add markers on maps.
  
- The default map style in Folium is the OPEN STREET MAP.
  
- The STAMEN TERRAIN stamen terrain style is great for visualizing hill shading and natural vegetation colors.
  
- To create a choropleth map of a region of interest, Folium requires a GEO JSON file that includes GEOSPATIAL DATA OF THE REGION.

- The ‘LOCATION’ parameter specifies the latitude and longitude coordinates of the center point of the map.

- Markers play a vital role in enhancing interactivity and adding context to maps. Markers represent specific locations or points of interest, providing additional information when clicked.

- The folium.Marker() function specifies location parameters.

- The popup parameter provides a label upon being clicked.

- Markers can be created using “feature group.”

- The code for setting the initial zoom level in Folium is
ZOOM_START=PARAMETER

### Choropleth map

- A choropleth map is a thematic map in which areas are shaded or patterned in proportion to the measurement of the statistical variable.
  
- First step when converting a world map into a choropleth map is DEFINING THE VARIABLE that points to our Geo JSON file.

- When creating a choropleth map, Folium requires a GeoJson file that includes geospatial data of the region.

- The Mapbox Bright Tileset displays the name of every country when used on a map.

[Cheat Sheet : Maps, Waffles, WordCloud and Seaborn](https://author-ide.skills.network/render?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJtZF9pbnN0cnVjdGlvbnNfdXJsIjoiaHR0cHM6Ly9jZi1jb3Vyc2VzLWRhdGEuczMudXMuY2xvdWQtb2JqZWN0LXN0b3JhZ2UuYXBwZG9tYWluLmNsb3VkL0lCTURldmVsb3BlclNraWxsc05ldHdvcmstRFYwMTAxRU4tU2tpbGxzTmV0d29yay9sYWJzL3Y0L0RWMDEwMUVOLUNoZWF0U2hlZXQtMy5tZD90PTE3NDYxMjMxOTIiLCJ0b29sX3R5cGUiOiJpbnN0cnVjdGlvbmFsLWxhYiIsImF0bGFzX2ZpbGVfaWQiOjM1MTU3LCJhZG1pbiI6ZmFsc2UsImlhdCI6MTc1NzY5NDU1OH0.tELqwbJFsawYfpd7a6ADyhsXIlqqZOb8eGaN4H9Ea3w)
