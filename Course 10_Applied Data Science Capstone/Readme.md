# Coursera Quiz Answers for Applied Data Science Capstone 

### Week 1 Quiz 1 >>Graded Quiz: Data Collection API with Webscraping 

Q1. After you performed a GET request on the Space X API and convert the response to a dataframe using pd.json_normalize. 
What year is located in the first row in the column static_fire_date_utc? <br/>
Answr: 2006 

Q2. Using the API, how many Falcon 9 launches are thereafter we remove Falcon 1 launches? <br/>
Answer: 90 

Q3. At the end of the API data collection process, how many missing values are there for the column landing pad? <br/>
Answer: 26 

Q4. After making a request to the Falcon9 Launch Wiki page and creating a BeautifulSoup object what is the output of: soup. title <br/>
Answer: <title> List of Falcon 9 and Falcon Heavy launches - Wikipedia </title>


### Week 1 Quiz 2 >>Graded Quiz: Data Wrangling Quiz 

Q5. How many launches came from CCAFS SLC 40? <br/>
Answer: 55 

Q6. What was the success rate? <br/>
Answer: 67%

Q7. How many launches went to geosynchronous orbit? <br/>
Answer: 1 

Q8. How many mission outcome was successfully landed to a drone ship? <br/>
Answer: 41


### Week 2 Quiz 1 >>Exploratory Data Analysis using SQL Answers 

Q9. Which of the following will retrieve  upto 20 records  from the spacex table?<br/>

Answer: SELECT *  from SPACEXTBL LIMIT 20


Q10. Which of the following queries display the minimum payload mass?<br/>

Answer: select min(payload_mass__kg_) from SPACEXTBL 


Q11. You are writing a query that will give you the total payload_mass_kg carried by the booster versions. The mass  should be  stored in the mass column. You want the result column to be called “Total_Payload_Mass”. Which of the following SQL queries is correct?<br/>

Answer: SELECT sum(PAYLOAD_MASS__KG_) as Total_Payload_Mass from SPACEXTBL 


Q12. Which of the following query is used to display the mission outcome counts for each launch site?<br/>

Answer: select  count("Mission_Outcome") as MISSION_OUTCOME_COUNT,Launch_Site  from SPACEXTBL group by "Launch_Site";


Q13. What are the unique launch sites mentioned in the Spacex table?<br/>

Answer: CCAFS LC-40,KSC LC-39A, VAFB SLC-4E , CCAFS SLC-40   



### Week 2 Quiz 2 >>Exploratory Data Analysis (EDA) for Data Visualization 

Q14. What type of data does a Bar Chart best represent?<br/>
Answer: Categorical

Q15. What are the total number of columns in the features dataframe after applying one hot encoding to columns Orbits, 
LaunchSite, LandingPad and Serial . 
Here the features  dataframe consists of the following columns FlightNumber', 'PayloadMass', 'Orbit', 'LaunchSite', 'Flights', 'GridFins', 'Reused', 'Legs', 'LandingPad', 'Block', 'ReusedCount', 'Serial'<br/>

Answer: 80

Q16.The catplot code to show the scatterplot of  FlightNumber vs LaunchSite with x as FlightNumber, and y to Launch Site and hue to 'Class’ is <br/>

Answer: <br/>

```
sns.catplot(y="LaunchSite",x="FlightNumber",hue="Class", data=df, aspect = 1)

plt.ylabel("Launch Site",fontsize=15)

plt.xlabel("Flight Number",fontsize=15)

plt.show()
```



### Week 3 >>Graded Quiz: Interactive Visual Analytics and Dashboard 

Q17. How can you add marking objects such as circles, markers, or lines on a Folium map? (Click all choices that apply) <br/>

Answer:<br/>

   - object.add_to(map)<br/>

   - map.add_child(object)<br/>


Q18. If you want to add multiple markers with similar coordinates on the Folium map, which Folium plugin you should use? <br/>

Answer: MarkerCluster 

Q19. Which attribute is used to provide available selections (such as a list of launch sites) for a Plotly DropDown input? <br/>
Answer: options

Q20. How can we associate the result of a callback function (like a Ploty figure) to an element defined in the application? <br/> 
Answer: Using a unique component id 

Q21. Can we add multiple input components to a dash callback function? <br/> 
Answer: Yes



### Week 4 >>Graded Quiz: Predictive Analysisis Answers 

Q22. How many records were there in the test sample? <br/>
Answer: 18 

Q23. For Support Vector Machines, what kernel has the best result on the validation dataset? <br/>
Answer: sigmoid

Q24. After selecting the best hyperparameters for the decision tree classifier using the validation data, 
what was the accuracy achieved on the test data Disclaimers? <br/>
Answer: 83.33%




