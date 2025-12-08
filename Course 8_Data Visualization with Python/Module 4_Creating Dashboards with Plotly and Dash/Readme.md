# Summary: Creating Dashboards with Plotly and Dash

Congratulations! You have completed this module. At this point in the course, you know: 

- MATPLOTLIB is a comprehensive library for creating static, animated, and interactive VISUALIZATIONS in Python.

- Web-based visualizations created using PLOTLY Python can be displayed in Jupyter Notebook, saved to standalone HTML files, or served as part of pure Python-built web applications using Dash.

- The PLOTLY graph objects module provides an automatically generated hierarchy of classes.

- Dash is an OPEN-Source User Interface Python library for creating reactive, web-based applications.

- It is easy to build Graphical User Interfaces using Dash as it abstracts all technologies required to make the applications.

- Plotly express is a HIGH-LEVEL wrapper.

- There are two components of Dash: Core and HTML components.

- The dash_core_components describe higher-level interactive components generated with JavaScript, HTML, and CSS through the React.js library.

- The dash_html_components library has a component for every HTML tag.

- A callback function is DECORATOR_a python function that is automatically called by DASH whenever an input component's property changes.

- The @app.callback decorator decorates the callback function in order to tell Dash to call it whenever there is a change in the input component value.

- The callback function takes input and output components as PARAMETERS  and performs operations to return the desired result for the output component.

- The correct way of adding a callback decorator is the following:<br/>
  @app.callback( Output(component_id='bar-plot’, component_property='figure’), Input(component_id='input-yr,’ component_property='value’)).<br/>
(All are  Parenthesis, not Curly brackets)

- VISUAL is the feature that dashboards offer in real-time

- JSON is a Plotly.graph object that has a dictionary structure
  
- Additional Resources for Dashboards
[Dashboarding tools](https://pyviz.org/dashboarding/)
[John Snow's data journalism](https://www.theguardian.com/news/datablog/2013/mar/15/john-snow-cholera-map)

- Additional Resources for Plotly
   - [Getting Started with Plotly in Python](https://plotly.com/python/getting-started/)
   - [Graph Objects in Python](https://plotly.com/python/graph-objects/)
   - [Plotly Express in Python](https://plotly.com/python/plotly-express/)
   - [Python API reference for plotly](https://plotly.com/python-api-reference/)


   - [Plotly cheatsheet](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://images.plot.ly/plotly-documentation/images/plotly_js_cheat_sheet.pdf)
   - [Plotly community](https://community.plotly.com/c/plotly-python/5)
   - [Related blogs](https://plotlygraphs.medium.com/)
   - [Open-source datasets](https://www.transtats.bts.gov/DataIndex.asp)

