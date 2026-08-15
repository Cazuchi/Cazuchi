# Hi, I'm Mike
And this is my GitHub profile, which is meant to showcase skills that I have developed, which were not a part of my master's degree from Copenhagen Business School. 
My master's degree focused on a combination of data collection methodologies, statistical analysis of data and the interpretation of results for use in business, 
however after graduating I have been working constantly to develop my skillset, which now also includes, amongst others: 

- Setting up cloud pipelines from A to Z for data collection, analysis and visualization 
- Coding in Python, SQL, DAX 
- Setting up and interacting with SQL databases in Docker (PostgreSQL with and without dbt on top)
- GCP: BigQuery, IAM, Secret Manager, SSH, Firewall restrictions, Compute Engine (Debian usually) 
- Azure: Fabric notebooks, Spark, lakehouse table management

These skills are not obvious from my educational credentials however and because of confidentiality requirements I cannot directly show projects that I have worked on 
professionally. Therefore the projects in this GitHub profile have been created to highlight these skills and show off projects that I find interesting.

Over time, there is going to be a lot of projects within this profile, so the following is a highlight of my main projects and what skills they showcase. Each project 
also has a dedicated README to further explain the contents of the project and its purpose.

## [Transforming TourMIS data into a performance dashboard](https://github.com/Cazuchi/Transforming-TourMIS-data-into-a-performance-dashboard)
> [!NOTE]  
> Skills used in this project:  
> * Python  
> * DAX / PowerBi  
> * Google Compute Engine / Secret Manager / IAM / BigQuery

TourMIS is a tourism database with bed nights, arrivals and population figures for 135+ destinations in Europe along with calculated estimates for destinations that do 
not upload their own data. This project uses Python to pull bed nights, arrivals and population satistics from the TourMIS API, runs it through extensive formatting 
functions and uploads it to two Google BigQuery tables. These BigQuery tables are then loaded into PowerBi where I used DAX to create a series of measures to calculate 
performance statistics for the different travel destinations and allow for comparison of performance across different tourist destinations.

Tourism data is notoriously fractured and inconsistent, which required a lot of data wrangling in both Python and DAX. I used Python code to correct for missing values 
and insure continuity across the different data series within the dataset and then used DAX to create performance metrics in PowerBi that likewise account for the peculiarities 
of tourism data. Included in this repo is: 
- The Python code to pull, format and store the data from the API. Properly formatted and commented to explain design decisions. 
- The DAX code for the PowerBi measures. Commented to explain design decisions.
- [A link to the PowerBi dashboard to show off the final result.](https://app.powerbi.com/view?r=eyJrIjoiOGM4Yjk3NGUtMmVlNS00NTEyLTk3MjUtNWNiNDQ4ZDg2NTdhIiwidCI6IjcwZjRhY2NiLTM3N2UtNDg5ZS04YjhiLTI4NjllYjQwYmQ3MSJ9)

## [Streamlit dashboard made with the NYC taxi dataset](https://github.com/Cazuchi/nyc-cab-streamlit-dashboard)
> [!NOTE]
> Skills used in this project:  
> * Streamlit  
> * BigQuery  
> * Cloud Run  
> * Python  
> * SQL  

I used SQL to extract a subset of the NYC yellow taxi dataset and stored that in a BigQuery table. The Streamlit dashboard compares select KPIs across two boroughs of the user's choosing.  

The data is cached for 3,600 seconds to avoid unnecessary re-pulls and the data pulls are separated so that changing a value in one drop-down only updates the subset of the total dataset for that borough.  

[You can see and interact with the dashboard here.](https://nyc-cab-streamlit-dashboard-562594843791.europe-west1.run.app/)  

Here is a preview of the dashboard:  
![Alt text](/imgs/preview.png)    

## [F1 Ergast data SQL project](https://github.com/Cazuchi/F1-ergast-data-SQL-project) 
> [!NOTE]  
> Skills used in this project:  
> * SQL  
> * Docker  

This project builds the Kaggle F1 Ergast dataset into a local Docker SQL database using SQL and then presents two extensive SQL queries to output transformed, calculated 
table that highlight severall interesting aspects of the F1 Ergast dataset. The first query uses a series of CTEs to calculate a table highlighting interesting findings 
about individual drivers performance over time, while the second query utilizes a CTE chain, window functions and the Gaps & Islands approach to calculate a table showcasing 
interesting findings about the different teams' strategic choices when pairing drivers for a stint (unique combination of team and drivers). Included in this repo is: 
- [docker-compose.yml](https://github.com/Cazuchi/F1-ergast-data-SQL-project/blob/main/docker-compose.yml) with the docker settings
- [schema.sql](https://github.com/Cazuchi/F1-ergast-data-SQL-project/blob/main/schema.sql) to define and populate the database with data
- [analysis.sql](https://github.com/Cazuchi/F1-ergast-data-SQL-project/blob/main/Analysis.sql) to showcase and explain my queries
- The raw F1 Ergast datafiles (credit to: https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020?resource=download)

While this project is supposed to primarily be a SQL exercise, I've made a PowerBi dashboard that shows some of the output of my CTE chain queries, which is available here:  
https://app.powerbi.com/view?r=eyJrIjoiZDFhOGMyMTMtYzBjMS00Mjc1LTgzN2UtMGJjNjEzMDA3N2ZlIiwidCI6IjcwZjRhY2NiLTM3N2UtNDg5ZS04YjhiLTI4NjllYjQwYmQ3MSJ9  

The graphs is just a simple scatterplot showing the difference in drivers' total career points between using the legacy scoring models in place when a given race took place and adjusting all of a driver's points to match the newest 25-point scoring model used in modern F1 races.  

Legacy career points are shown on the x-axis. Modern career points are shown on the y-axis and the dots a colored depending on how large the difference is between the modern and the legacy career points totals:  
* Green: Less than 50% difference  
* Yellow: Between 50% and 100% difference  
* Red: More than 100% difference  

## [dbt version of my F1 Ergast SQL project](https://github.com/Cazuchi/dbt-F1-ergast-data-SQL-project)
> [!NOTE]  
> Skills used in this project:  
> * SQL
> * dbt  
> * Docker  
> * Python  

This project uses the same dataset and the same queries, except they've been modified to follow the pattern of a dbt database. To show that it's working and output correct data, [I've included a notebook with inline visualization to show the output of the project.](https://github.com/Cazuchi/dbt-F1-ergast-data-SQL-project/blob/main/analysis.ipynb)

Since it's just a proof of functionality, I've just created a simple array of spider charts, comparing 6 select drivers performance on chosen metrics to the average driver, which resulted in this plot:  
![Alt text](https://github.com/Cazuchi/dbt-F1-ergast-data-SQL-project/blob/main/plots/driver-performance-comparison.png)  

## [Automating a browser in Playwright to download raw data and format it into a compressed, easy-to-read visual format for use in presentations](https://github.com/Cazuchi/Automating-browser-for-data-collection-and-visualization)  
> [!NOTE]  
> Skills used in this project:  
> * Python  
> * Playwright / Browser automation
> * PowerShell interaction

Simple script I made to automate a browser in order to:  
* Navigate to a website
* Log in
* Navigate the website's sub-menus
* Download the desired dataset with hotel statistics and save it in the project folder
* Load the data from the downloaded .csv file and format it into a compressed, easy-to-read visual format for use in presentations

Since the script requires login info, but also needs to be usable by more than one person, it simply asks for login information from the user in the PowerShell terminal window.

The output looks like this:  
>[!IMPORTANT]
>The data shown in the image is **MOCK** data. It broadly mimicks real trends, but is randomized and varies significantly from real data.  

![Script output](https://github.com/Cazuchi/Automating-browser-for-data-collection-and-visualization/blob/main/Benchmarking%20Alliance%20occupancy%20overview.png)  
The table shows the occupancy rates for hotels in a select geographic area per day, per month with specific highlights in yellow for days with lower occupancy and highlights in green for days with higher occupany. Used to figure out and showcase what times of the year that there is the most room for added tourism activity for a given year

## [Cheatsheet](https://github.com/Cazuchi/Cheatsheet) 
> [!NOTE]  
> Skills used in this project:  
> * Crontabs  
> * Debian  
> * Docker  
> * Fabric notebooks  
> * Git  
> * GCP (Bigquery, IAM, Compute Engine)  
> * PowerShell  
> * Python  
> * SSH  
> * SQL  
> * ... and more.  

My cheatsheet that I continually add to as I troubleshoot issues that I encounter. It is purposefully written to match the way that I think when problemsolving and is meant as a personal reference when working on projects, but it might be interesting / useful to some of you reading this.  

#### More projects coming soon. I am actively developing this profile.