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

To view death distribution click HERE






