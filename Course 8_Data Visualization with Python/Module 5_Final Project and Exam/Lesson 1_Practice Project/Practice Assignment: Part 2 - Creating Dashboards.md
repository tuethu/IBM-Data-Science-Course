```
import pandas as pd
import dash
from dash import html, dcc
from dash.dependencies import Input, Output, State
import plotly.graph_objects as go
import plotly.express as px
from dash import no_update
import datetime as dt
```

- Create app
```
app = dash.Dash(__name__)
```

- Clear the layout and do not display exception till callback gets executed
```
app.config.suppress_callback_exceptions = True
```

- Read the wildfire data into pandas dataframe
```
df =  pd.read_csv('https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork/Data%20Files/Historical_Wildfires.csv')
```

- Extract year and month from the date column
```
df['Month'] = pd.to_datetime(df['Date']).dt.month_name() #used for the names of the months
df['Year'] = pd.to_datetime(df['Date']).dt.year
```

# Layout Section of Dash
## Task 2.1 Add the Title to the Dashboard
- Application title is Australia Wildfire Dashboard
- Use style parameter provided below to make the title center aligned, with color code #503D36, and font-size as 26

```
app.layout = html.Div(children=[html.H1('Australia Wildfire Dashboard', 
                                style={'textAlign': 'center', 'color': '#503D36',
                                'font-size': 26}),
```

## Task 2.2 Add the radio items and a dropdown right below the first inner division

- Radio items to choose the Region
- The radio items work similar to the dropdown, you need to call dcc.RadioItems and pass the list of items. Make use of <ins>inline=True</ins> property to display the radio items in a HORIZONTAL line

   - You can extract the regions from the dataframe using df.Region.unque() or pass the list of all regions directly as ['NSW','QL','SA','TA','VI','WA','NT'] .
   - Assign radioitems id as region
   - Label as Select Region
   - value as NSW
     
For your reference below are the abrivations used in the dataset for regions
     - NSW - New South Wales
     - NT - Northern Territory
     - QL - Queensland
     - SA - South Australia
     - TA - Tasmania
     - VI - Victoria
     - WA - Western Australia

- outer division starts
(dcc stands for Dash Core Components, part of the Dash framework. These components are essential for building dynamic and responsive web applications in Python. They include elements like dropdowns, sliders, graphs, checklists, and more, enabling developers to create feature-rich dashboards with minimal effort.)
  
```
     html.Div([
                   # First inner divsion for  adding dropdown helper text for Selected Drive wheels
                    html.Div([
                            html.H2('Select Region:', style={'margin-right': '2em'}),

                    #Radio items to select the region
                    #dcc.RadioItems(['NSW','QL','SA','TA','VI','WA'], 'NSW', id='region',inline=True)]),
                    dcc.RadioItems([{"label":"New South Wales","value": "NSW"},
                                    {"label":"Northern Territory","value": "NT"},
                                    {"label":"Queensland","value": "QL"},
                                    {"label":"South Australia","value": "SA"},
                                    {"label":"Tasmania","value": "TA"},
                                    {"label":"Victoria","value": "VI"},
                                    {"label":"Western Australia","value": "WA"}],"NSW", id='region',inline=True)]),
```

                    #Dropdown to select year
- The dropdown has an id as year.
- The label as Select Year
- The values allowed in the dropdown are years from 2005 to 2020
- The default value when the dropdown is displayed is 2005.
              
```
                    html.Div([
                            html.H2('Select Year:', style={'margin-right': '2em'}),
                        dcc.Dropdown(df.Year.unique(), value = 2005,id='year')
                    ]),

```

## Task 2.3 Add two empty divisions for output inside the next inner division. 
- Second Inner division for adding 2 inner divisions for 2 output graphs
- Use 2 html.Div() tags .
- Provide division ids as plot1 and plot2
  
```
                    html.Div([
                
                        html.Div([ ], id='plot1'),
                        html.Div([ ], id='plot2')
                    ], style={'display': 'flex'}),

    ])
    #outer division ends

])
#layout ends
```


## TASK 2.4 Add the Ouput and input components inside the app.callback decorator.

- The inputs and outputs of our application’s interface are described declaratively as the arguments of @app.callback decorator.
  -In Dash, the inputs and outputs of our application are simply the properties of a particular component.

- In this example, we have two inputs:-
  - input for Region is the value property of the component that has the ID region
  - input for Year is the value property of the component that has the ID year

- Our layout has 2 outputs so we need to create 2 output components.
It is a list with 2 output parameters with component id and property.
Here, the component property will be children as we have created empty division and passing in dcc.Graph (figure) after computation.

Component ids will be plot1 , plot2.

- Place to add @app.callback Decorator

```
@app.callback([Output(component_id='plot1', component_property='children'),
               Output(component_id='plot2', component_property='children')],
               [Input(component_id='region', component_property='value'),
                Input(component_id='year', component_property='value')])
```


## TASK 2.5 Add the callback function.   
- Place to define the callback function .

- Whenever an input property changes, the function that the callback decorator wraps will get called automatically.
- In this case let us define a function reg_year_display() which will be wrapped by our decorator.
  
- The function first filters our dataframe df by the selected value of the region from the radio items and year from the dropdown as follows
  - region_data = df[df['Region'] == input_region]
  - y_r_data = region_data[region_data['Year']==input_year]
    
- For pie chart on Monthly Average Estimated Fire Area: 
  - Next we will group by the Month and calculate the mean Estimated_fire_area of the dataframe.
  - Use the px.pie() function to plot the pie chart
    
- For bar chart on Monthly Average Count of Pixels for Presumed Vegetation Fires: 
  - Next we will group by the Month and calculate the mean Count of the dataframe.
  - Use the px.bar() function to plot the bar chart
 
- Finally we return the 2 figure objects fig1 and fig2 in dcc.Graph method.
- Once you have finished coding save your code.

```
def reg_year_display(input_region,input_year):  
    #data
   region_data = df[df['Region'] == input_region]
   y_r_data = region_data[region_data['Year']==input_year]

    #Plot one - Monthly Average Estimated Fire Area   
   est_data = y_r_data.groupby('Month')['Estimated_fire_area'].mean().reset_index()
   fig1 = px.pie(est_data, values='Estimated_fire_area', names='Month', title="{} : Monthly Average Estimated Fire Area in year {}".format(input_region,input_year))

     #Plot two - Monthly Average Count of Pixels for Presumed Vegetation Fires
   veg_data = y_r_data.groupby('Month')['Count'].mean().reset_index()
   fig2 = px.bar(veg_data, x='Month', y='Count', title='{} : Average Count of Pixels for Presumed Vegetation Fires in year {}'.format(input_region,input_year))    
   return [dcc.Graph(figure=fig1),
            dcc.Graph(figure=fig2) ]

if __name__ == '__main__':
    app.run()
```


![Expected Layout](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%205_Final%20Project%20and%20Exam/Lesson%201_Practice%20Project/Practice%20Assignment_Part%202_Expected%20Layout.png)
