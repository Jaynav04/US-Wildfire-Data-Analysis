<h1> Analyzing Large-Scale Wildfires in the United States </h1>

<h2> Overview </h2>

A dynamic dashboard comprising three distinct perspectives revealing insights into wildfires categorized as size G (involving over 5,000 acres burned) that occurred within the United States between 2000 and 2020. 

For the creation of our dashboard, we chose to employ a range of JavaScript visualization libraries including D3, Leaflet, Plotly, and Highcharts. To enhance the aesthetics, we applied CSS and HTML5 for styling. The data displayed on the dashboard is retrieved through a Flask-powered API connected to a local PostgreSQL database. 

The dashboard's inspiration stemmed from the questions we formulated:

* What are the Primary Factors Contributing to these Fires?
* Does a relationship exist between the passage of time and the total count of large wildfires?
* Top 10 states with the most fires? Top ten with the least?
* Which states had the most acres burned? Which states had the least?


Team members: Emily Boulware, Jair Navarrete, Shelby Reyes-Widrick, and Desmond Workman

<h2> Data Sources </h2>

The dataset used was from kaggle and can be found [here.](https://www.kaggle.com/datasets/behroozsohrabi/us-wildfire-records-6th-edition 'US Wildfires') 
The wildfire records were acquired from several reporting systems of federal, state, and local fire organizations. 

*Note: Original dataset contains data from 1992-2020 we opted to minimize the dataset and analyze years 2000-2020 on size G wildfires only*

## To run the dashboard 

<h2> Screen Shots of Dashboard Visualizations</h2>

<div align="center"> Complete Dashboard </div>

![Dashboard](https://github.com/emilymees/ProjectThree/blob/main/images/dashboard.png)

<div align="center"> Example of Wildfire DataFrame </div>

![Wildfire DataFrame](https://github.com/emilymees/ProjectThree/blob/main/images/wildfires_df.png)

<div align="center"> Causes of Human Wildfires </div>

![Types of Human Wildfires](https://github.com/emilymees/ProjectThree/blob/main/images/humanFires_df.png)

<div align="center"> Pie Chart of Non-Natural Wildfires </div>

![Pie Chart](https://github.com/emilymees/ProjectThree/blob/main/images/non-natural_causes.png)

<div align="center"> Total Wildfires per Year </div>

![Bar Graph](https://github.com/emilymees/ProjectThree/blob/main/images/yearly_fire_total.png)
