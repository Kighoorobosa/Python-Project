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


Please click HERE to view the difference in R-values 









