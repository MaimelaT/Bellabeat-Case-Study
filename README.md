#  Bellabeat Case Study 
My first Data Analysis Project

##### Author: Tshifhiwa Maimela

##### Date: 10 July 2023

#

_The case study follows the six step data analysis process:_

### ❓ [Ask](#1-ask)
### 💻 [Prepare](#2-prepare)
### 🛠 [Process](#3-process)
### 📊 [Analyze](#4-analyze)
### 📋 [Share](#5-share)
### 🧗‍♀️ [Act](#6-act)

## Introduction
BELLABEAT is a high-tech company that manufactures health-focused smart products for women. Their products include trackers in a form of necklaces and smart watches, clips, apps and water bottles. They also have different memberships for their users. Stakeholders asked for recommendations from insights gained when analyzing smart usage data based on the following questions:
1.	What are some trends in smart device usage?
2.	How could these trends apply to Bellabeat customers?
3.	How could these trends help influence Bellabeat marketing strategy?
#

## 1. ❓ Ask
💡 **BUSINESS TASK: Analyze smart device usage data to gain insight into how customers use non-Bellabeat smart devices.**
**Stakeholders:**
1.	Urska Srsen – Bellabeat’s co-founder and Chief Creative Officer.
2.	Sando Mur – Mathematician and Bellabeat’s co-founder.
3.	Bellabeat’s marketing analytics team – Data Analysts. 

#

## 2. 💻 [Prepare](#2-prepare)

+ Datasets used is Fitbit Fitness Tracker Data https://www.kaggle.com/datasets/arashnic/fitbit

+ Found in Kaggle at CC0: Public Domain, available through Mobius. https://www.kaggle.com/arashnic

+ 30 eligible Fitbit users gave consent to the submission of personal tracker data, including minute-level output for physical activity, 
         heart rate and sleep monitoring.

+ The data include information about daily activity, steps, and heart rate that can be used to explore user’s habits.


ENTER ROCCC INFORMATION



After downloading the datasets, I prepared my data by cleaning it in uploading it in Google Sheets. I changed the format of data to 2 decimals, checked for spelling errors. I removed empty columns and values. I sorted the datasets to display data from the highest calories lost.

**Limitations:**

         o Srsen, one of the Stakeholder mentioned that this data might have some limitations and encouraged to consider adding more data to address the limitations.
         
         o Data recorded data is between April – May 2016, meaning it is outdated. User behavior may have changed.
         
         o The data is from 30 users, however, Fitbit has approximately 30 million users. Using a population size of 30 million users and only using 30 sample size gives out a Margin of Error = 17.9% which concludes that the given sample size is little to make accurate predictions. 
         
         o I used Google Big Query to count the number of users using SQL and found 33 users instead of 30.


-- Checking the number of number of users
SELECT
DISTINCT Id
FROM `bellabeat-392006.Bellabeat.dailyActivity`

         o The data was recorded from 2016-04-12 to 2016-05-12, 30 days of data collection.

         -- Checking the time frame of the recording of data
         SELECT
         DISTINCT Id, ActivityDate
         FROM `bellabeat-392006.Bellabeat.dailyActivity`
         ORDER BY ActivityDate

## 3. 🛠 [Process](#3-process)

For data cleaning, Google sheets and SQL were used to ensure the integrity and cleanliness of the data.
* Checked Id user length consistency.
* Removed empty columns.
* Rounded the values to 2 decimal places.
* Checked for duplicates.
* Extra space within cells.
* Checked for date formats.
* Checked for nulls and empty spaces.


The following data cleaning was used. *File: dailyActivity_Merged*
* Checked Id length consistency.
* Removed empty columns and rows.
* Rounded all numeric values to 2 decimal places.
* Removed the VeryActiveDistance, ModeratelyActiveDistance and LightActiveDistance columns. 
* Focused on the Id, ActivityDate, TotalSteps, TrackerDistance,SedentaryMinutes and Calories columns.
* Renamed SedentaryMinutes to IdleMinutes.

File: *weightLogInfo_Merged*
  * Used the LEFT & RIGHT Function to separate the Date and Time.
  * Rounded the WeightKg numerical values to 2 decimal places.

File: *sleepDay_Merged*
  * Separated the Date and Time Function.
  * The data was clean.


## 📊 [Analyze](#4-analyze)

I checked the number of users of *dailyActivity_merged*, *sleepDay_merged*, *weightInfo_merged*, *heartRate_merged*, and *dailyStep_merged* using Big Query SQL to determine how many users used each of these Bellabeat product features. I used the following codes:

         *dailyActvity_Merged data*
         -- Cheking the total number of users
         SELECT COUNT(DISTINCT Id) AS Total_Ids
         FROM `bellabeat-392006.Bellabeat.dailyActivity`

*sleepDay_Merged data*
SELECT
DISTINCT Id
FROM `bellabeat-392006.Bellabeat.sleepDay`

*weightInfo_Merged data*
SELECT
DISTINCT Id
FROM `bellabeat-392006.Bellabeat.weightInfo`

*heartrate_Merged data*
SELECT
DISTINCT Id
FROM `bellabeat-392006.Bellabeat.heartrate`

*dailyStep_Merged data*
SELECT
DISTINCT Id
FROM `bellabeat-392006.Bellabeat.dailySteps`

