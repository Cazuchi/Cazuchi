# Hi, I'm Mike
And this is my GitHub profile, which is meant to showcase skills that I have developed, which were not a part of my master's degree from Copenhagen Business School. 
My master's degree focused on a combination of data collection methodologies, statistical analysis of data and the interpretation of results for use in business, 
however after graduating I have been working constantly to develop my skillset, which now also includes, amongst others: 

- Setting up cloud pipelines from A to Z for data collection, analysis and visualization 
- Coding in Python, SQL, DAX 
- Setting up and interacting with SQL databases in Docker 

These skills are not obvious from my educational credentials however and because of confidentiality requirements I cannot directly show projects that I have worked on 
professionally. Therefore the projects in this GitHub profile have been created to highlight these skills and show off projects that I find interesting.

Over time, there is going to be a lot of projects within this profile, so the following is a highlight of my main projects and what skills they showcase. Each project 
also has a dedicated README to further explain the contents of the project and its purpose.

## [Transforming TourMIS data into a performance dashboard](https://github.com/Cazuchi/Transforming-TourMIS-data-into-a-performance-dashboard)
TourMIS is a tourism database with bed nights, arrivals and population figures for 80+ destinations in Europe along with calculated estimates for destinations that do 
not upload their own data. This project uses Python to pull bed nights, arrivals and population satistics from the TourMIS API, runs it through extensive formatting 
functions and uploads it to two Google BigQuery tables. These BigQuery tables are then loaded into PowerBi where I used DAX to create a series of measures to calculate 
performance statistics for the different travel destinations and allow for comparison of performance across different tourist destinations.

Tourism data is notoriously fractured and inconsistent, which required a lot of data wrangling in both Python and DAX. I used Python code to correct for missing values 
and insure continuity across the different data series within the dataset and then used DAX to create performance metrics in PowerBi that likewise account for the peculiarities 
of tourism data. Included in this repo is: 
- The Python code to pull, format and store the data from the API. Properly formatted and commented to explain design decisions. 
- The DAX code for the PowerBi measures. Commented to explain design decisions.
- A link to the PowerBi dashboard to show off the final result. 

## [F1 Ergast data SQL project](https://github.com/Cazuchi/F1-ergast-data-SQL-project) 
This project builds the Kaggle F1 Ergast dataset into a local Docker SQL database using SQL and then presents two extensive SQL queries to output transformed, calculated 
table that highlight severall interesting aspects of the F1 Ergast dataset. The first query uses a series of CTEs to calculate a table highlighting interesting findings 
about individual drivers performance over time, while the second query utilizes a CTE chain, window functions and the Gaps & Islands approach to calculate a table showcasing 
interesting findings about the different teams' strategic choices when pairing drivers for a stint (unique combination of team and drivers). Included in this repo is: 
- [docker-compose.yml](https://github.com/Cazuchi/F1-ergast-data-SQL-project/blob/main/docker-compose.yml) with the docker settings
- [schema.sql](https://github.com/Cazuchi/F1-ergast-data-SQL-project/blob/main/schema.sql) to define and populate the database with data
- [analysis.sql](https://github.com/Cazuchi/F1-ergast-data-SQL-project/blob/main/Analysis.sql) to showcase and explain my queries
- The raw F1 Ergast datafiles (credit to: https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020?resource=download)

#### More projects coming soon. I am actively developing this profile.