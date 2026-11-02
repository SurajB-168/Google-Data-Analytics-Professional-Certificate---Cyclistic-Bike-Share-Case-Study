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
![Total Rides](images/Membership%20Types.png)

Members took 59.4% of rides and casual riders took 40.6%.

### Bike types
![Bike Types](images/Types%20of%20Bikes.png)

Both groups prefer classic bikes. Only casual riders used docked bikes.

### Average ride length
![Average Ride Length](images/Avg%20Ride%20Length%20%28Year%29.png)

Members ride for 12.41 minutes on average. Casual riders ride for 23.82 minutes.

### Rides per month
![Rides per Month](images/Total%20Rides%20%28Month%29.png)

Both groups ride most in summer and least in January.

### Average ride length per month
![Average Ride Length per Month](images/Avg.%20Ride%20Length%20%28Month%29.png)

Casual riders take much longer rides than members in every month.

### Rides per weekday
![Rides per Weekday](images/Total%20Rides%20%28Week%29.png)

Members ride steadily through the week. Casual riders ride mostly on weekends.

### Average ride length per weekday
![Average Ride Length per Weekday](images/Avg.%20Ride%20Length%20%28Week%29.png)

Both groups take longer rides on weekends.

## Dashboard

![Dashboard](images/Cyclistic%20Bike%20Share%20Dashboard.png)

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
