# Google-Data-Analytics-Capstone-Project
## Introduction
The eighth course in the Google Data Analytics Certificate is a Capstone Project. In the course, you have the option to create a case study by either working with existing questions and datasets or creating your own questions and datasets. 
<br>
<br>
I have selected the Cyclistic bike share analysis case study to work on. For the case study, I will perform the real-world tasks of a junior data analyst for the marketing team at Cyclistic, a fictional bike-share company in Chicago. To answer key business questions, I followed the six steps of the data analysis process taught in the course which are: Ask, Prepare, Process, Analyze, Share and Act.

## Ask
In the Ask phase, we learned how to ask effective questions to make data-driven decisions, while connecting with stakeholders’ needs. 

### Scenario
The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

### Key Stakeholders
* Cyclistic: A bike-share program that features more than 5,800 bicycles and 600 docking stations. 
* Lily Moreno: The director of marketing and your manager. 
* Cyclistic marketing analytics team: A team of data analysts who are responsible for collecting, analyzing, and reporting data that helps guide Cyclistic marketing strategy. 
* Cyclistic executive team: The detail-oriented executive team will decide whether to approve the recommended marketing program.

## Prepare
In the Prepare phase, we learned how to use tools like spreadsheets and SQL to extract and make use of the right data for your objectives and how to organize and protect our data.

### Data Source
As was mentioned earlier, Cyclistic is a fictional company. But, through the Motivate International Inc license, Divvy has been sharing their historical trip data from 2013 on. For the purposes of this case study, I've used the following files, which can be found here: https://divvy-tripdata.s3.amazonaws.com/index.html:
* 202101-divvy-tripdata.zip
* 202102-divvy-tripdata.zip
* 202103-divvy-tripdata.zip
* 202104-divvy-tripdata.zip
* 202105-divvy-tripdata.zip
* 202106-divvy-tripdata.zip
* 202107-divvy-tripdata.zip
* 202108-divvy-tripdata.zip
* 202109-divvy-tripdata.zip
* 202110-divvy-tripdata.zip
* 202111-divvy-tripdata.zip
* 202112-divvy-tripdata.zip

The csv file within each zip file provides us with trip data from 01/01/2021 - 12/31/2021, consisting of 13 columns containing information related to ride id, ridership type, ride time, start location and end location and geographic coordinates, etc, which I'ved used to analyze and identify trends. 
<br>
<br>
The 7th course of the Google Data Analytics certificate taught us about the R programming language. In that course, we learned how to clean, organize, analyze, visualize, and report data in new and more powerful ways. RStudio Desktop is the tool I've used to prepare, process, analyze, and visualize the data for this Capstone project. Further descriptions of how I do all of that within R can be found in the RMD file, which I have attached to this project.

After uploading the csv files into RStudio and analyzing each data frame to ensure the columns all matched, I used the rbind function to combine the 12 data frames into one. Next, I added columns to the data frame to list the date, month, day, and year of each ride, as well as a ride_length column by subtracting the started_at column from the ended_at column. In this new data frame, there are 5,595,063 rows and 19 columns.

## Process
In the Process phase, we learned how to ensure our data's integrity, clean our data using spreadsheets and SQL, and how to verify and report our data cleaning results.

In RStudio, I cleaned the data by ensuring there weren't any duplicate ride_ids and removing any rows where the ride length was less than 0. That removed 147 rows, leaving us with 5,594,916 rows and 19 columns.

## Analyze
In the Analyze phase, we learned how to organize and format our data using spreadsheets and SQL to help us look at and think about our data in different ways. We also found out how to perform complex calculations on our data to complete business objectives and how to use formulas, functions, and SQL queries as we conduct our analysis.

Once the data was cleaned, I analyzed the data in RStudio to determine the following:
* Count of trips by rider type
* Mean, median, maximum and minimum ride duration (by rider type)
* Average ride length by day and by rider type

While more riders are members than casual ones, in looking at the mean, median, maximum, and minimum ride duration by rider type, casual riders use the bikes the most. 

## Share

In the Share phase, we learned how data visualizations, such as visual dashboards, can help bring your data to life. 

For this phase, I created some bar graphs to better visualize when the following
* Number of rides per day of the week by rider type
* Average duration per day of the week by rider type
* Number of rides per month by rider type
* Average duration per month by rider type

Each of these visualizations can be found in the files I have attached to this project.

## Act

### Summary of insights gained from visualizations in RStudio

* While more riders are members than casual ones, in looking at the mean, median, maximum, and minimum ride duration by rider type, casual riders bike for longer periods of time than members. 
* Casual riders mainly ride on weekends. Members are much more consistent with using the bikes throughout the week, even though they do go for shorter rides. 
* From January - April, members use the bikes more often than casual riders. In May, the ridership between members and casuals almost evens out. 
* The ridership increases for both rider types in the summer months (June - September), with casual riders riding more often, then decreases after August, with members riding more often casual riders. 

### Recommendations of a new marketing strategy the team should use to convert casual riders into annual members
* Launch the new marketing strategy from January through May, as the number of trips made by the cyclists increases.
* Create promo codes from January through May, as a way to incentivize people to ride more.
* Add new membership plans, such as a weekend only option, due to the fact that ridership increases during the weekend.
