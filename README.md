# Python-Project

## Introduction
This python project focuses on covid data from continents around the world.
The objective is to gain insights into the spread and as well as mortality rates across continents.

**_Disclaimer_**:_The reports provided have been created solely for the purpose of demonstrating the capabilities of PYTHON in data analysis_.

## Analysis Questions And Answers
# Importing the neccessary packages

import pandas as pd

import matplotlib.pyplot as plt

import seaborn as sns

import numpy as np

# Load the dataset
df = pd.read_csv('covid-data')

# Data Assesment
"Data Assessment:"
"Null Values: ", df.isnull().sum()

"Duplicates: ", df.duplicated().sum()

"Incorrect datatypes: ", df.dtypes

"Incorrect Date Entries: ",df['date'].dtypes

"Mispellings: ", df['location'].nunique()

"Outliers: ", df.describe()

# Outliers
To view outliers click HERE



## Data Cleaning 
#Replacing null values with mean

df['total_cases'].fillna(df['total_cases'].mean(), inplace=tTrue

df['total_deaths'].fillna(df['total_deaths'].mean(), inplace=tTrue

# Converting date column to datetime
df['date'] = pd.to_datetime(df['date'])

# Data Exploration
"\nData Exploration:"

"Distribution of Total Cases: ", df['total_cases'].describe()

"Distribution of Total Deaths: ", df['total_deaths'].describe()

df_numeric = df.select_dtypes(include=[np.number])

correlation_matrix = df_numeric.corr()

correlation_matrix
![CorrelationMatrix](https://github.com/Kighoorobosa/Python-Project/assets/159533793/41f1a94e-dcac-4e56-97a0-745e57379f13)

Please click HERE to view the correlation matrix

To view death distribution click HERE

## Problem Statement
# Generate KPIs
"\nProblem Statement 1: Generate KPIs"
"Total Cases: ", df['total_cases'].sum()
"Total Deaths: ", df['total_deaths'].sum()
"Case Fatality Rate (CFR): ', (df['total_deaths'].sum() / df['total_cases'].sum()) * 100

# Show the total number of COVID-19 cases by continent (Top 5)
"\nProblem Statement 2: Total COVID-19 cases by continent"
continent_cases = df.groupby('continent')['total_cases'].sum().reset_index()
continent_cases.df.sort_values(by='total_cases', ascending=False, inplace=True)
continent_cases.head(5)

Please click HERE to view top 5 continent with total number of Covid-19 cases.

![image](https://github.com/Kighoorobosa/Python-Project/assets/159533793/c7830cb8-5d6c-4225-a101-dc234a1e9008)


# Identify countries with fluctuating R-values
"\nProblem Statement 2: Countries with fluctuating R-values"
# Calculate the difference in R-values for each country
df['r_value_diff'] = df.groupby('location')['reproduction_rate'].diff()
# Identify countries with a difference greater than 0.5
flunctuation_countries = df[df['r_value_diff'] > 0.5].groupby('location')['r-value_diff'].max().reset_index()
fluctuating_countries
 
![image](https://github.com/Kighoorobosa/Python-Project/assets/159533793/ae371863-0fc1-4b7f-a649-bf47f6944950)

# Average Birth Rate
avg_birth_rate = df.groupby9(['location', 'month'])['reproduction_rate'].mean().reset_index()

![image](https://github.com/Kighoorobosa/Python-Project/assets/159533793/5d732d35-4d89-4fa0-be86-011d8eb5583c)


# Differential Birth Rate
avg_birth_rate = ['difference'] = avg_birth_rate['reproduction_rate'].diff
avg_birth_rate = ['absolutedifference'] = avg_birth_rate['reproduction_rate'].diff().abs()
avg_birth_rate

![image](https://github.com/Kighoorobosa/Python-Project/assets/159533793/4ff773b8-925c-4f24-8bba-71f5b7b71f08)

# Group by country and calculate difference in average birthrate between months
country_diff = avg_birth_rate.groupby('location')['absolutedifference'].max().reset_index()
country_diff

![image](https://github.com/Kighoorobosa/Python-Project/assets/159533793/326223ec-abd1-4f97-85f1-a1bf95e37176)

# Filtering for signicant fluctuations (e.g., > 50% change)
signicant_fluctuations = country_diff[country_diff['absolutedifference'] > 0.50]
![image](https://github.com/Kighoorobosa/Python-Project/assets/159533793/b79728b5-a242-4daa-b913-3e51346d5778)


## Problem Statement 4: Distribution of COVID-19 cases  and deaths by age group
The COVID-19 dataset does not have the detailed data required to accurately answer the question about the distribution of COVID-19 cases and deaths among different age groups and how it varies across countries.It has the following limitations:
1. It provides daily/weekly summaries at the country level,rather than 
   individual data.
2. It does not include age bracket information for COVID cases and 
   deaths.
3.The only age-related data provided is the percentage of the population above 65,which is not relevant to the question at hand.
Therefore,I am unable to provide a meaningful answer to the question using this dataset.

## Insights from the Analysis
1.Areas with high total cases tend to see more new cases.
2.New cases and their smoothed versions are similar.
3.More deaths are associated with areas having higher total cases.
4.Countries with better healthcare infrastructure (hospital beds) might have higher life expectancies.
5.There might be a link between stricter COVID-19 restrictions and fewer new cases, but no other factors likely influence this.
NOTE:Correlation does not equal caussation, and further analysis is recommended.















