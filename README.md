# big_data_technologies_class_project1


## Project bites :chocolate_bar:

**Brief**: 

**Key insights**: 

**Tools**: 

**Concepts**:



## Project objective :dart:

In this Big Data Technology project, I applied the concepts and tools I learned about Infrastructure as a Service (IaaS) with EC2, the terminal, containerization with Docker, and a NoSQL database like OpenSearch to handle a dataset that exceeded the capacity of a single machine. I also crafted a dashboard with Kibana to uncover insights from the data.


## Dataset

The [Fire Incident Dispatch Data](https://data.cityofnewyork.us/widgets/8m42-w767)
file originates from the Starfire Computer Aided Dispatch System, tracking incidents from creation to closure. It details resource allocation and the Fire Department's response to emergencies while safeguarding personal information under HIPAA (Health Insurance Portability and Accountability Act) by aggregating incident locations.

[Data schema] (https://dev.socrata.com/foundry/data.cityofnewyork.us/8m42-w767)

NYC Open Data provides free datasets, including large ones. They offer an API for easy data retrieval. I use a Python client to fetch Fire Incident Dispatch Data from the API.

Obtain an app [token]( https://data.cityofnewyork.us/login)

Used [Socrata Open Data API](https://dev.socrata.com/)








## Questions and KPIs (Key Performance Indicators)

Next, I took a moment to think about important questions and suitable indicators to enhance my understanding and analysis of the data. This was a purposeful step to make sure that my data exploration remained relevant and meaningful.


KPI # 1: Number of incidents by borough 
KPI # 2: Total engine assigned by zip codes
KPI # 3: Average ladders assigned by borough
KPI # 4: Number of incidents by the borough over time
World cloud: Frequency of incident by fire incident classification

Which borough has more fire incidents?
Which five zip codes are assigned the total highest number of engines?
Which are the top two boroughs by assigned ladders on average?
What happened to fire incidents during the pandemic?
Answer: If we look at KPI # 4: Fire incident reports by borough in NYC (2005 - 2021). 
What is the most frequent classification of fire incidents?



| Field Name                | Data Type | Field Description                                                           |
|---------------------------|-----------|-------------------------------------------------------------------------------|
| starfire_incident_id      | number    | An incident identifier comprising the 5 character julian date, 4 character... |
| incident_datetime         | datetime  | The date and time of the incident.                                           |
| incident_borough          | text      | The borough of the incident.                                                 |
| zipcode                   | text      | The zip code of the incident.                                                |
| incident_classification   | text      | The incident classification.                                                 |
| engines_assigned_quantity | number    | The number of engine units assigned to the incident.                         |
| ladders_assigned_quantity | number    | The number of ladder units assigned to the incident.                         |





## Project workflow

After setting up an EC2 instance on AWS, I developed a Python script within Docker to retrieve data from the NYC Open Data via their API and transmit it to OpenSearch. I made sure the data bypassed my EC2 instance and was directly streamed to OpenSearch. Once the data was accessible in OpenSearch, I generated multiple AWS Kibana  to create a dashboard to explore the data and uncover insights.


### Python scripting

I wrote a Python command-line interface that connected to the Fire Incident Dispatch Data. My script was designed to run within Docker and accepted command-line parameters. Each data line processed by my script was accurately passed into OpenSearch. I had the freedom to choose which API fields to push into OpenSearch.

### Project composition

project01/
+-- Dockerfile
+-- requirements.txt
+-- src/
+-- +-- main.py
+-- assets/
+-- +-- Gauge_chart_total_number_of_rows.png
+-- +-- KPI_1_Number_of_incidents_by_borough_in_NYC_2005_2021.png
+-- +-- KPI_2_Top_20_zip_codes_by_total_engine_assigned_in_NYC_2005_2021.png
+-- +-- KPI_3_The_Bronx_and_Brooklyn_are_assigned_more_ladders_on_average_in_NYC_2005_2021.png
+-- +--KPI_4_Fire_incident_reports_by_borough_in_NYC_2005_2021.png
+-- +-- Medical_Assistant_Civilian_is_the_most_frequent_fire_incident_in_NYC_2005_2021.png
+-- +-- Dashboard_with_all_visualizations.png
+-- README.pd


## Key insights :bulb:


### Lessons learned :sparkles:

