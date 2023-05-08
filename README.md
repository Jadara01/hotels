# hotels
Develope a database to analyze and visualize hotel booking data
Hotel revenue over the course of 3 years
Business questions: is hotel reveue growing by year? (segment two hotel types),
Should parking lot size be increased?.
Data trends?

Revenue by year calculated and rounded by 2 decmial places

select
arrival_date_year,
hotel,
round(sum((stays_in_week_nights + stays_in_weekend_nights) *adr),2) as revenue
from hotels
group by arrival_date_year, hotel
