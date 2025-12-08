------------------------------------------------------------------
# TASK 1 - Read the data
------------------------------------------------------------------
# Import required libraries
import pandas as pd
import dash
from dash import dcc
from dash import html
from dash.dependencies import Input, Output
import plotly.express as px

# Read the airline data into pandas dataframe
airline_data =  pd.read_csv('https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DV0101EN-SkillsNetwork/Data%20Files/airline_data.csv', 
                            encoding = "ISO-8859-1",
                            dtype={'Div1Airport': str, 'Div1TailNum': str, 
                                   'Div2Airport': str, 'Div2TailNum': str})

# Create a dash application
app = dash.Dash(__name__)

# Build dash app layout

------------------------------------------------------------------
# TASK 2 - Create dash application and get the layout skeleton
------------------------------------------------------------------
# TASK 3 - Update layout components
------------------------------------------------------------------

# Application title: Title as Flight Delay Time Statistics, align text as center, color as #503D36, and font size as 30

app.layout = html.Div(children=[ html.H1('Flight Delay Time Statistics', 
                                style={'textAlign': 'center', 'color': '#503D36',
                                'font-size': 30}),


# Input component: Update dcc.Input component id as input-year, default value as 2010, and type as number. Use style parameter and assign height of the input box to be 35px and font-size to be 30

                                html.Div(["Input Year: ", dcc.Input(id='input-year', value='2010', 
                                type='number', style={'height':'35px', 'font-size': 30}),], 
                                style={'font-size': 30}),
                                html.Br(),
                                html.Br(), 


# Output component - Segment 1
# First inner division: Add dcc.Graph() component.Update dcc.Graph component id as carrier-plot
# Second inner division: Add dcc.Graph() component.Update dcc.Graph component id as weather-plot
                              
                                html.Div([
                                        html.Div(dcc.Graph(id='carrier-plot')),
                                        html.Div(dcc.Graph(id='weather-plot'))
                                ], style={'display': 'flex'}),


# Output component - Segment 2
# First inner division: Add dcc.Graph() component.Update dcc.Graph component id as nas-plot.
# Second inner division: Add dcc.Graph() component. Update dcc.Graph component id as security-plot
                                
                                html.Div([
                                        html.Div(dcc.Graph(id='nas-plot')),
                                        html.Div(dcc.Graph(id='security-plot'))
                                ], style={'display': 'flex'}),


# Output component - Segment 3
# Add dcc.Graph() component to the first inner division. Update dcc.Graph component id as late-plot.
                               
                                html.Div(dcc.Graph(id='late-plot'), style={'width':'65%'})
                                ])
------------------------------------------------------------------
# TASK 4 - Review and add supporting function
------------------------------------------------------------------

""" Compute_info function description

This function takes in airline data and selected year as an input and performs computation for creating charts and plots.

Arguments:
    airline_data: Input airline data.
    entered_year: Input year for which computation needs to be performed.
    
Returns:
    Computed average dataframes for carrier delay, weather delay, NAS delay, security delay, and late aircraft delay.

"""
def compute_info(airline_data, entered_year):
    # Select data
    df =  airline_data[airline_data['Year']==int(entered_year)]
    # Compute delay averages
    avg_car = df.groupby(['Month','Reporting_Airline'])['CarrierDelay'].mean().reset_index()
    avg_weather = df.groupby(['Month','Reporting_Airline'])['WeatherDelay'].mean().reset_index()
    avg_NAS = df.groupby(['Month','Reporting_Airline'])['NASDelay'].mean().reset_index()
    avg_sec = df.groupby(['Month','Reporting_Airline'])['SecurityDelay'].mean().reset_index()
    avg_late = df.groupby(['Month','Reporting_Airline'])['LateAircraftDelay'].mean().reset_index()
    return avg_car, avg_weather, avg_NAS, avg_sec, avg_late

"""Callback Function

Function that returns fugures using the provided input year.

Arguments:

    entered_year: Input year provided by the user.
    
Returns:

    List of figures computed using the provided helper function `compute_info`.
"""

------------------------------------------------------------------
# TASK 5 - Add the application callback function
------------------------------------------------------------------
# TASK 6 - Update the callback function
------------------------------------------------------------------

# Callback decorator
# We have 5 output components added in a list. Update output component id parameter with the ids provided in the dcc.Graph() component and set the component property as figure. One sample has been added to the skeleton.


@app.callback( [
               Output(component_id='carrier-plot', component_property='figure'),
               Output(component_id='weather-plot', component_property='figure'),
               Output(component_id='nas-plot', component_property='figure'),
               Output(component_id='security-plot', component_property='figure'),
               Output(component_id='late-plot', component_property='figure')
               ],

#Update input component id parameter with the id provided in the dcc.Input() component and component property as value
               Input(component_id='input-year', component_property='value'))

# Callback function
# Next is to update the get_graph function. We have already added a function compute_info that will perform computation on the data using the input.

# Mapping the returned value from the function compute_info to graph:
# avg_car - input for carrier delay
# avg_weather - input for weather delay
# avg_NAS - input for NAS delay
# avg_sec - input for security delay
# avg_late - input for late aircraft delay


# Computation to callback function and return graph
def get_graph(entered_year):
    
    # Compute required information for creating graph from the data
    avg_car, avg_weather, avg_NAS, avg_sec, avg_late = compute_info(airline_data, entered_year)
            
    # Line plot for carrier delay
    carrier_fig = px.line(avg_car, x='Month', y='CarrierDelay', color='Reporting_Airline', title='Average carrrier delay time (minutes) by airline')
    # Line plot for weather delay
    weather_fig = px.line(avg_weather, x='Month', y='WeatherDelay', color='Reporting_Airline', title='Average weather delay time (minutes) by airline')
    # Line plot for nas delay
    nas_fig = px.line(avg_NAS, x='Month', y='NASDelay', color='Reporting_Airline', title='Average NAS delay time (minutes) by airline')
    # Line plot for security delay
    sec_fig = px.line(avg_sec, x='Month', y='SecurityDelay', color='Reporting_Airline', title='Average security delay time (minutes) by airline')
    # Line plot for late aircraft delay
    late_fig = px.line(avg_late, x='Month', y='LateAircraftDelay', color='Reporting_Airline', title='Average late aircraft delay time (minutes) by airline')
            
    return[carrier_fig, weather_fig, nas_fig, sec_fig, late_fig]

# Run the app
if __name__ == '__main__':
    app.run()



![Lab3_output_Add Interactivity_User Input and Callback](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%208_Data%20Visualization%20with%20Python/Module%204_Creating%20Dashboards%20with%20Plotly%20and%20Dash/Lab3_output_Add%20Interactivity_User%20Input%20and%20Callbacks.png)
