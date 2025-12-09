✈️ Project Description – Flight Performance & Delay Analytics

This project analyzes U.S. domestic flight performance using a large dataset containing over 6 million records. The dataset includes information such as flight dates, airline, aircraft details, airport codes, scheduled and actual departure/arrival times, delay durations, cancellation reasons, distance traveled, and airport geolocation (latitude/longitude).
The objective was to derive meaningful operational insights through SQL queries, Excel dashboards, and Power BI visualizations, focusing on flight delays, cancellations, and travel patterns.

🔍 Project Goals

Identify delay patterns across weekdays and weekends.

Evaluate airline-wise cancellations, especially for JetBlue on the 1st of each month.

Perform week-wise, state-wise, and city-wise delay analysis.

Identify airlines with zero departure/arrival delay on long-distance routes (2500–3000 miles).

Build analytical dashboards and run real-time SQL queries to demonstrate insights.

📂 Data Model & Schema

The project uses a 3-table relational schema:

1. Flights (Fact Table)

Contains >6M rows of operational flight data.
Key fields:

Date fields: Year, Month, Day

Airline code (IATA), Flight number

Origin & Destination airport codes

Scheduled & actual departure/arrival times

Departure delay, arrival delay, cancellation flag

Cancellation reasons

Distance, Taxi-in, Taxi-out, Wheels-on, Wheels-off

2. Airlines (Dimension Table)

Includes airline names and their IATA codes.

3. Airports (Dimension Table)

Contains airport name, city, state, and geolocation (latitude & longitude).
Used for state/city analyses.

Relationships

Flights.Airline = Airlines.IATA_Code

Flights.Origin_Airport = Airports.IATA_Code

Flights.Destination_Airport = Airports.IATA_Code

⭐ Key Performance Indicators (KPIs)
1. Weekday vs Weekend – Total Flight Analysis

Objective: Check how flight volume changes between weekdays and weekends.
Method:

Use DAYOFWEEK() or WEEKDAY() functions in SQL

Aggregate flight counts
Insight focuses on traffic patterns and operational load.

2. Total Flights Cancelled for JetBlue on the 1st of Every Month

Objective: Evaluate monthly cancellation behavior for JetBlue.
Method:

Filter Airline = 'B6' (JetBlue IATA)

Filter for DAY = 1

Sum(cancelled)
This helps understand if JetBlue shows recurring monthly cancellations.

3. Week-wise, State-wise, City-wise Delay Analysis with Airline Breakdown

Objective: Identify high-delay states, cities, and airlines.
Method:

Join Flights with Airports

Calculate avg departure/arrival delay by week, state, city

Use WEEK() function for week grouping
Insight: Reveals geographical delay hotspots and responsible airlines.

4. Airlines With Zero Departure/Arrival Delay for 2500–3000 Mile Flights

Objective: Find airlines performing best on long-distance routes.
Method:

Filter distance BETWEEN 2500 AND 3000

Select airlines where both delays = 0
Insight: Identifies high-precision airlines for long flights.

5. Cancellation Percentage

Objective: Measure cancellations relative to total flights.
Method:

(SUM(cancelled) / COUNT(*)) * 100
Insight: Shows operational reliability of airlines.

🛠 Tools & Techniques Used
SQL (MySQL Workbench 8.0 CE)

Complex joins (fact → airport → airline)

Window functions

Aggregations (SUM, AVG, COUNT)

Date functions (WEEK(), DAYOFWEEK(), MONTH())

Data cleaning (handling NULLs, invalid integers)

Optimized long-query performance for 6M+ rows

Excel

PivotTables & PivotCharts

KPI cards

Combined slicers

Dashboard design & formatting

Power BI

Data modeling with relationships

DAX measures (Avg delay, cancellation %)

Multiple dashboards using Cards, Bar charts, Maps

Calendar table for proper time intelligence

🎯 Final Outcomes

Successfully built five analytical KPIs.

Created Excel dashboards and Power BI dashboards.

Ran live SQL queries showing accurate insights.

Demonstrated understanding of flight-delay behavior across time, geography, and airlines.

Gained practical experience with big-data SQL operations, relational modeling, and BI visualization.
