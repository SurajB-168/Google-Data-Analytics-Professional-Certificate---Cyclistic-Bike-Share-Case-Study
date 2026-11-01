# Cyclistic Bike Share Case Study

## Introduction

This is a capstone project for the Google Data Analytics Professional Certificate. It follows the six steps from the course: Ask, Prepare, Process, Analyze, Share, and Act.

## Background

Cyclistic is a bike-share company in Chicago. Riders can pick up a bike at one station and return it at any other. The company wants more annual members, so this project looks at how casual riders and members use the bikes differently.

## Business Task

Find ways to convert casual riders into annual members.

## Data and Tools

- **Data:** [Divvy trip data](https://divvy-tripdata.s3.amazonaws.com/index.html), January to December 2022
- **Cleaning and analysis:** SQL on Google BigQuery
- **Visualization:** Tableau

## Process

1. Combined 12 monthly tables into one (5,667,717 rows)
2. Checked the data for missing values, outliers, and errors
3. Cleaned the data:
   - Removed rows with null values
   - Added columns for ride length, day of week, and month
   - Removed rides shorter than 1 minute or longer than 1 day
4. Ended with 4,224,062 rows

SQL files: [Combining](01_Data_Combining.sql), [Exploration](02_Data_Exploration.sql), [Cleaning](03_Data_Cleaning.sql), [Analysis](04_Data_Analysis.sql)

## Analysis

### Total rides
![Total Rides](images/total_rides.png)

Members took 59.4% of rides and casual riders took 40.6%.

### Bike types
![Bike Types](images/bike_types.png)

Both groups prefer classic bikes. Only casual riders used docked bikes.

### Average ride length
![Average Ride Length](images/avg_ride_length.png)

Members ride for 12.41 minutes on average. Casual riders ride for 23.82 minutes.

### Rides per month
![Rides per Month](images/rides_per_month.png)

Both groups ride most in summer and least in January.

### Rides per weekday
![Rides per Weekday](images/rides_per_weekday.png)

Members ride steadily through the week. Casual riders ride mostly on weekends.

## Dashboard

![Dashboard](images/dashboard.png)

[View the interactive dashboard on Tableau](https://public.tableau.com/app/profile/hui.min.ho/viz/CyclisticBikeShareCaseStudy_16931448059910/Sheet1#2)

## Key Findings

- Both groups ride more from May to September.
- Both groups prefer classic bikes.
- Members take short, regular trips, likely for work or errands.
- Casual riders take longer trips, mostly on weekends, likely for fun.

## Recommendations

- **Flexible plans:** Offer monthly and daily memberships, not just yearly.
- **Loyalty points:** Reward riders with points for every ride.
- **Member events:** Hold events that only members can join.
- **Seasonal offers:** Run discounts in the busy spring and summer months.
- **Social media:** Share member stories and photos to attract casual riders.

## Conclusion

Members ride often for short trips, while casual riders ride less often for longer, mostly on weekends. Marketing that fits these habits can help turn casual riders into members.

## 👨‍💻 About the Author

**Surajkumar Bevnale**
Data Analyst | SQL • Excel • Power BI • Python
B.Tech, Engineering Physics, IIT Ropar (2023–2027)

- 📫 Reach me at: surajk.b168@gmail.com
- 🔗 LinkedIn: [Surajkumar B](https://www.linkedin.com/in/skb168/)
