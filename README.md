# hotels
Developed a database to analyze and visualize hotel booking data
Hotel revenue over the course of 3 years
Project Description:

The goal of this project was to develop a comprehensive database that would enable the analysis and visualization of hotel booking data and revenue trends over a period of three years. The primary business questions addressed by the project were to determine if hotel revenue was growing by year (specifically for two hotel types) and whether the parking lot size should be increased based on data trends.

To achieve this, a database was created and populated with hotel booking data from 2018, 2019, and 2020. The data included information such as arrival dates, hotel types, stays in weeknights and weekends, and average daily rates (ADR).

The revenue growth analysis was conducted by calculating and rounding the revenue figures to two decimal places. The data was grouped by year and hotel type to provide insights into the revenue growth trends from 2018 to 2020.

The following SQL query was used to retrieve the necessary data for revenue analysis:

```
WITH hotels AS (
    SELECT * FROM dbo.['2018$']
    UNION
    SELECT * FROM dbo.['2019$']
    UNION
    SELECT * FROM dbo.['2020$']
)

SELECT 
    arrival_date_year, 
    hotel, 
    ROUND(SUM((stays_in_week_nights + stays_in_weekend_nights) * adr), 2) AS revenue 
FROM 
    hotels 
GROUP BY 
    arrival_date_year, 
    hotel
```

The output of this query provided the aggregated revenue data grouped by year and hotel type, allowing for a clear visualization of the revenue growth patterns over the three-year period.

By analyzing the revenue growth trends, the project aimed to provide insights into the hotel's financial performance, specifically evaluating revenue growth by year for two distinct hotel types. Additionally, the project sought to determine whether the parking lot size should be increased based on the data trends observed.

Overall, the developed database and revenue analysis provided valuable information for making data-driven decisions related to hotel revenue and potential infrastructure improvements.
