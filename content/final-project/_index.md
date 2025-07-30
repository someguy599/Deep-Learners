---
title: "Final Project"
---
# Final Project -- Analyzing European Soccer 

## Introduction
We investigated data from European professional soccer leagues between 2007 and 2016. We built models that could predict ____ from ____. 

## Data Acquisition
We obtained our data as csv files from Kaggle from the [European Soccer Database](https://www.kaggle.com/datasets/hugomathien/soccer). We also incorporated data from Kaggle's [supplemental database](https://www.kaggle.com/datasets/jiezi2004/soccer). The data includes data about players' attributes (e.g. height, weight, age) and match results between European teams in each league. 

## Data Cleaning
### Cleaning Player Dataset
For our player attributes, we imputed data for the columns of categorical variables (dominant foot, attacking work rate, defensive work rate). We simply replaced any missing and nonsense values with the most frequent category. Additionally, we used one-hot encoding and ordinal encoding to convert these categorical variables to integers that our models can input. 

Each player in our dataset has over 30 standardized quantitative variables ranging from 0 to 100 that indicate various athletic qualities (e.g. abiility to handle penalties). 

We merged our two player attributes datasets into one dataframe for easier indexing where each row represents a season that a given player was rated. 

### Cleaning Match and Team Dataset

## Exploratory Data Analysis
Below is a histogram and KDE (smoothed out histogram) of player potential of all the more than 11,000 players in our dataset. Player potential refers to a player's future ability to perform at a high level. 
![](Potential_Histogram.png#center)

## Modeling

## Conclusion
