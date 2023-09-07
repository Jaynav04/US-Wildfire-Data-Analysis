<h1> Analyzing Large-Scale Wildfires in the United States </h1>
![image](https://github.com/Jaynav04/US-Wildfire-Data-Analysis/assets/130405173/455616dd-6833-4121-b12b-87f2e80be171)

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

## Presentation
Click to view (presentation)[https://docs.google.com/presentation/d/150Lm1gTc_hOu8m9YfVRSV_vG_XqX0CFp5QRIv5TwM9A/edit?usp=sharing]

## To run the dashboard 
1. Download the project files 
2. Run the initial SQL query and upload the provided CSV to the corresponding table. This will be the primary table used in the Flask API

       DROP TABLE wildfires_sizeG

    	create table wildfires_sizeG (
    		Fire_ID serial PRIMARY KEY,
    		Agency_Type VARCHAR(100) NOT NULL,
    		NWCG_Reporting_Agency VARCHAR(100) NOT NULL,
    		Reporting_Unit_Name VARCHAR(100) NOT NULL,
    		Fire_Name VARCHAR(100) NOT NULL,
    		Year INT,
    		Fire_Discovery_Date DATE,
    		Date_Contained DATE,
    		NWCG_Cause_Classification VARCHAR(100) NOT NULL,
    		Cause_Description VARCHAR(100) NOT NULL,
    		Fire_Size REAL,
    		Latitude REAL,
    		Longitude REAL,
    		Fire_Origin_Land_Owner VARCHAR(100) NOT NULL,
    		State VARCHAR(10) NOT NULL,
    		County VARCHAR(50) NOT NULL
    		);
    
        DELETE FROM wildfires_sizeg WHERE year < 2000;
        
        
        DELETE FROM wildfires_sizeg WHERE cause_description = 'Missing data not specified undetermined';
        
        
        UPDATE wildfires_sizeg SET cause_description = REPLACE(cause_description, '/', ' ');
        
        
        SELECT * FROM wildfires_sizeG;
4. With the downloaded files open up vs code and organize the folders in this order

          data/
              .csv
              .sql
          static/
               logic.js
              css/
                  style.css
          templates/
              index.html
          app.py
5. In the app.py file enter your pgAdmin credentials.

              app = Flask(__name__)
        
        def get_db_connection():
            conn = psycopg2.connect(host=' ',
                                    database='wildfires_db',
                                    user=' ',
                                    password=' ')
            return conn
7. Install psycopg2, if necessary

       pip install psycopg2  
8. Open Anaconda Prompt/Terminal depending on your device and cd to your folder location and run

       python app.py
9. Copy your development server into your browser and enjoy!

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
