# hotels
Developed a database to analyze and visualize hotel booking data
Hotel revenue over the course of 3 years
Business questions: is hotel revenue growing by year? (segment two hotel types),
Should parking lot size be increased?.
Data trends?

Revenue by year calculated and rounded to 2 decmial places. Grouped by year and hotel type, to display the revenue growth from 2018-2020.

with hotels as (
select * from dbo.['2018$']
union
select * from dbo.['2019$']
union
select * from dbo.['2020$'])

select
arrival_date_year,
hotel,
round(sum((stays_in_week_nights + stays_in_weekend_nights) *adr),2) as revenue
from hotels
group by arrival_date_year, hotel
