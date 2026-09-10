# Cyclistic Bike-Share Case Study: Converting Casual Riders into Annual Members

Google Data Analytics Professional Certificate — Capstone Project

A data analysis case study exploring how casual riders and annual members use Cyclistic's bike-share service differently, using SQL (BigQuery) for data cleaning/transformation and Data Studio for visualization — with the goal of informing a marketing strategy to convert casual riders into annual members.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Business Task](#business-task)
3. [Data](#data)
4. [Processing and Cleaning](#processing-and-cleaning)
5. [Analysis and Visualizations](#analysis-and-visualizations)
6. [Conclusions and Recommendations](#conclusions-and-recommendations)
7. [Tools Used](#tools-used)

---

## Introduction

This project is part of the **Google Data Analytics Professional Certificate capstone**. The scenario involves analyzing trip data from Cyclistic, a fictional bike-share company operating in Chicago with around 6,000 bikes across 700 stations.

Cyclistic offers two ways to ride:
- **Casual riders** — single-ride and full-day passes
- **Members** — annual subscriptions

The company's finance team has determined that annual members are significantly more profitable than casual riders. Cyclistic's marketing director believes that maximizing the number of annual members is key to future growth, and wants to design a marketing campaign aimed at converting casual riders into members — but the team first needs to understand how the two groups' usage patterns differ.

## Business Task

> **How do annual members and casual riders use Cyclistic bikes differently?**

**Objective:** Clean, analyze, and visualize a year of ride data to identify behavioral differences between casual riders and annual members, and translate those differences into actionable marketing recommendations.

## Data

- **Source:** Public trip data from Motivate International Inc. (the Divvy bike-share system in Chicago), made available under [this license](https://www.divvybikes.com/data-license-agreement).
- **Data range analyzed:** May 2020 – April 2021 (~608 MB across 12 monthly `.csv` files)
- **Full historical archive:** Available [here](https://divvy-tripdata.s3.amazonaws.com/index.html) (2013–present)
- **Granularity:** Each row is an individual ride, with start/end timestamps, station names, station IDs, latitude/longitude, bike type, and rider type (casual/member).
- **Storage:** Raw monthly files were uploaded to Google Cloud Storage (GCS) to handle their size before import into BigQuery.

## Processing and Cleaning

All processing was done in **BigQuery** using SQL.

- The 12 monthly files were imported from GCS and consolidated into a single view with consistent data types — see [`uncleaned_compile.sql`](./uncleaned_compile.sql).
- Four calculated columns were added to support analysis:
  - Start point location
  - End point location
  - Ride start day of week
  - Ride duration (seconds)
- The initial consolidated dataset returned **3,742,624 rows**, which then went through a cleaning pass.

**Cleaning steps:**
| Check | Purpose | Query |
|---|---|---|
| Station check | Identify missing start/end station names | [`station_check.sql`](./station_check.sql) |
| Column check | Validate other fields for nulls/inconsistencies | [`columns_check.sql`](./columns_check.sql) |
| Duration check | Flag negative or zero-length rides | [`duration_check.sql`](./duration_check.sql) |

After removing invalid and incomplete records, **3,476,354 rows** remained for analysis. The full cleaning-and-consolidation logic — including `JOIN`, `WITH`, `UNION ALL`, `WHERE`, and subqueries — is combined in a single master query: [`single_query.sql`](./single_query.sql).

## Analysis and Visualizations

The cleaned dataset (~3.4M rides) was visualized in **Google Data Studio** to compare casual riders and members across several dimensions.

### 1. Total Ride Share
- **58.6%** of rides were taken by annual members; **41.4%** by casual riders.
- Members represent the majority of ride volume, reinforcing their importance to long-term growth.

### 2. Weekly Distribution of Rides
- Casual ridership **peaks sharply on weekends**, while member ridership stays relatively flat across the week.
- Casual ridership is roughly **50% lower on weekdays** than on weekends — consistent with leisure use rather than commuting.

### 3. Weekly Distribution of Average Ride Duration
- Casual riders' average ride duration is about **3x longer** than members'.
- Both groups' average durations increase on weekends, but the gap remains wide.

### 4. Ride Duration vs. Ride Distance
- Both rider types travel a **similar average distance** per ride.
- Despite similar distances, casual riders take **~3x longer**, suggesting more leisurely, less direct riding.

### 5. Hourly Distribution of Rides
- Casual riders' share jumps from **18%** during commute hours to as much as **50%** during late-morning and evening (post-8pm) hours.
- Members make up **up to 82%** of rides during typical morning/evening commute windows.

### 6. Monthly Distribution — Seasonality
- Casual ridership drops to about **20%** of total rides during winter (Dec–Feb).
- Casual ridership peaks at about **40%** during summer months (June–September).

*Visualizations to be added once finalized in Data Studio.*

## Conclusions and Recommendations

**Key insight:** Casual riders predominantly use Cyclistic bikes for **leisure and tourism**, while annual members use them primarily for **commuting**. This is evident from casual riders' weekend concentration, longer ride durations at similar distances, off-peak hourly usage, and strong summer seasonality.

**Recommendations:**
1. **Target leisure locations** — Run on-the-ground marketing campaigns near parks, tourist attractions, restaurants, and entertainment venues where casual riders are concentrated.
2. **Weekday incentives** — Offer discounted weekday passes or bundles to nudge casual riders toward using bikes for commuting, building the habit that leads to membership.
3. **Off-peak engagement** — Use push notifications or in-app promotions during the late-morning and evening leisure windows when casual ridership is highest.
4. **Seasonal campaigns** — Launch a winter-specific promotion (e.g., tied to the holiday season) to offset the steep seasonal drop-off in casual ridership and keep the conversion funnel active year-round.

## Tools Used

- **Google BigQuery** — data storage, SQL-based cleaning and transformation
- **Google Cloud Storage** — staging for large raw CSV files
- **Google Data Studio (Looker Studio)** — visualization and dashboarding
- **SQL** — `JOIN`, `WITH`, `UNION ALL`, `WHERE`, subqueries, and aggregate functions

---

*This is a fictional case study completed as part of the Google Data Analytics Professional Certificate. Data is provided by Motivate International Inc. under their public [data license agreement](https://www.divvybikes.com/data-license-agreement).*
