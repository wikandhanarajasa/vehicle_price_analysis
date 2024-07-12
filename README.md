# Vehicle Price Analysis Project

## Introduction

Welcome to the Vehicle Price Analysis project. As an analyst at Crankshaft List, you are tasked with analyzing a vast dataset of vehicle advertisements to uncover the factors influencing vehicle prices. Every day, hundreds of free vehicle ads are posted on our company's website, and this project aims to leverage the data collected over the years to provide insights into pricing dynamics.

## Project Description

The goal of this project is to analyze historical vehicle advertisement data to identify key factors that affect vehicle prices. This involves cleaning and preprocessing the data, conducting exploratory data analysis, and ultimately determining which variables most significantly impact vehicle pricing.

## Project Instructions

### Step 1: Data Loading and Initial Examination
- Load the dataset located.
- Examine the general information of the dataset to understand its structure and contents.

### Step 2: Data Preprocessing

#### Handling Missing Values:
- Identify and examine missing values in the dataset.
- For columns where it is reasonable to infer missing values (e.g., Boolean columns), fill in the missing values accordingly.
- For other columns, determine the best approach to handle missing values, considering the significance and impact of the missing data.

#### Data Type Conversion:
- Identify columns that need data type conversions and explain the rationale behind these changes.

### Step 3: Feature Engineering
- Add columns for the day of the week, month, and year the advertisement was posted.
- Add the time and date the advertisement was posted.
- Calculate the age of the vehicle (in years) at the time of the advertisement.
- Compute the average annual mileage for each vehicle.
- Convert the condition column's string values to a numeric scale:
  - new = 5
  - like new = 4
  - excellent = 3
  - good = 2
  - fair = 1
  - salvage = 0

### Step 4: Exploratory Data Analysis
- Analyze key parameters: price, vehicle age, mileage, number of cylinders, and condition. Create histograms for each parameter and examine the effect of outliers on the histogram shapes.
- Identify outliers and remove them. Save the outliers in a separate DataFrame and continue analysis with the filtered data.
- Create new histograms without outliers and compare them with the original ones, drawing conclusions for each parameter.
- Analyze the number of days advertisements are listed (days_listed). Create a histogram, calculate the mean and median, and explain typical advertisement durations. Identify quickly removed ads and those listed for extended periods.
- Analyze the number of advertisements and average prices for each vehicle type. Create a graph showing the relationship between the number of ads and vehicle type, focusing on the two most frequently advertised types.

### Step 5: Detailed Analysis of Price Influencing Factors
- Investigate factors that most significantly influence vehicle prices. For the most popular vehicle types identified, analyze whether the price depends on age, mileage, condition, transmission type, and color.
- Create boxplots for categorical variables (transmission type and color) and scatter plots for continuous variables (age, mileage, and condition). Ensure each category has at least 50 ads to maintain validity.

## Conclusion
- Summarize findings from the analysis.
- Discuss key factors influencing vehicle prices.
- Provide recommendations based on the analysis results.

## Data Description

The dataset contains the following columns:
- `price`: Vehicle price
- `model_year`: Model year of the vehicle
- `model`: Vehicle model
- `condition`: Condition of the vehicle
- `cylinders`: Number of cylinders
- `fuel`: Type of fuel (gas, diesel, etc.)
- `odometer`: Mileage of the vehicle at the time of advertisement
- `transmission`: Transmission type
- `paint_color`: Color of the vehicle
- `is_4wd`: Whether the vehicle has four-wheel drive (Boolean)
- `date_posted`: Date the advertisement was posted
- `days_listed`: Number of days the advertisement was listed before being removed

By following these steps, we aim to gain a comprehensive understanding of the factors affecting vehicle prices and provide actionable insights for Crankshaft List.

## Summary

### Data Exploration
- Missing values were found in the columns `is_4wd`, `paint_color`, `odometer`, and `cylinders`.
- Outliers were found in the columns `price`, `odometer`, and `car_age`.
- Date formats and data types were not proper.

### Handling Data Anomalies
- Filled missing values in `is_4wd` and `cylinders` with 0, in `paint_color` with "unstated", and in `odometer` with the mean of `model_year`.
- Removed outlier values in `price`, `car_age`, and `odometer` as their quantities were insignificant.
- Corrected date formats with the `to_datetime` method.
- Adjusted data types with the `astype` method.

### Analysis
- Focused on parameters that might correlate with price using histograms, charts, and correlation analysis.
- Hypothesized that mileage, age, and engine capacity significantly influence car prices.

### Findings
- The main factors affecting car prices are age, mileage, and engine capacity.
- A younger car tends to be more expensive (positive correlation).
- Higher mileage generally results in a lower price (negative correlation).
