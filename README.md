# Google-Data-Analytics-Capstone-Cyclistic-Case-Study

**Course:** [Google Data Analytics Capstone: Complete a Case Study](#)

## Introduction

In this case study, I will perform many real-world tasks of a junior data analyst at a fictional company, Cyclistic. In order to answer the key business questions, I will follow the steps of the data analysis process: **Ask**, **Prepare**, **Process**, **Analyze**, **Share**, and **Act**.

## Quick links:

**Data Source:** [divvy_tripdata](#) [accessed on 07/10/25]

**SQL Queries:**
1. [Data Combining](Data%20Combining.sql)
2. [Data Exploration](Data%20Exploration.sql)
3. [Data Cleaning](Data%20Cleaning.sql)
4. [Data Analysis](Data%20Analysis.sql)

**Data Visualizations:** [Tableau](#)

## Background

### Cyclistic

A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use them to commute to work each day.

Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members.

Cyclistic’s finance analysts have concluded that annual members are much more profitable than casual riders. Although the pricing flexibility helps Cyclistic attract more customers, Moreno (the director of marketing and my manager) believes that maximizing the number of annual members will be key to future growth. Rather than creating a marketing campaign that targets all-new customers, Moreno believes there is a very good chance to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs.

Moreno has set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the marketing analyst team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.

### Scenario

I am assuming to be a junior data analyst working in the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, my team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve our recommendations, so they must be backed up with compelling data insights and professional data visualizations.

## 1. Ask

### Business Task

The primary business task is to analyze how casual riders and annual members use Cyclistic bikes differently to inform the creation of a new marketing campaign aimed at converting casual riders to members.


### Analysis Questions
As per the project brief, three questions guide this initiative:

1. How do annual members and casual riders use Cyclistic bikes differently? 

2. Why would casual riders buy Cyclistic annual memberships? 

3. How can Cyclistic use digital media to influence casual riders to become members? 

My assignment from Moreno is to focus on answering the first question: How do annual members and casual riders use Cyclistic bikes differently?

## 2. Prepare

I will analyse and discover trends in Cyclistic's historical trip data from January 2022 to December 2022, which can be accessed from [divvy_tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html). Motivate International Inc. has made the data available under this [license](https://divvybikes.com/data-license-agreement).

This is open data that may be used to investigate how various consumer categories use Cyclistic bikes. However, due to data privacy concerns, the use of riders' personally identifiable information is prohibited. This implies that we won't be able to associate pass purchases with credit card numbers to establish whether casual riders live in the Cyclistic service region or have purchased multiple single passes.

### Data Organization

There are 12 files with naming convention of **YYYYMM-divvy-tripdata** and each file includes information for one month, such as the ride id, bike type, start time, end time, start station, end station, start location, end location, and whether the rider is a member or not. The corresponding column names are ride_id, rideable_type, started_at, ended_at, start_station_name, start_station_id, end_station_name, end_station_id, start_lat, start_lng, end_lat, end_lng and member_casual.

## 3. Process

BigQuery is used to aggregate and clean many datasets.

**Reason:**
Microsoft Excel has a limit of 1,048,576 rows per worksheet due to its inability to handle huge data sets. Because the Cyclistic dataset contains over 5.6 million rows, a platform capable of handling large amounts of data, such as BigQuery, is required.

### Data Combining

SQL query: [Data Combining](Data%20Combining.sql)
The '2022_tripdata' dataset has 12 csv files supplied as tables. Another table called "combined_data" is created, including 5,667,717 rows of data for the full year.

### Data Exploration

SQL query: [Data Exploration](Data%20Exploration.sql)
Before cleansing the data, I'm familiarising myself with it to identify inconsistencies.

Observations:

The table below displays all column names and data types. The ride_id column is our primary key.
