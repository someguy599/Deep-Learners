---
title: "Relationship Between Air Quality and Income in California"
showToc: true
tocOpen: true
summary: Our goal was determining whether air quality and people's income are correlated among California counties.
date: 2025-07-08
---

## Introduction

Our goal was determining whether air quality and people's income are correlated among California counties.


## Data Acquisition


First, we obtained data from public datasets on air quality—-specifically PM 2.5 concentration--and income from all counties within California. 

We found the income data, which was income per capita per county in 2023, [here](https://fred.stlouisfed.org/release/tables?eid=266305&rid=175).

We found the air quality data, which was measured in Micrograms per cubic meter (PM2.5) [here](https://hdpulse.nimhd.nih.gov/data-portal/physical/table?age=001&age_options=ageall_1&demo=234&demo_options=air_pollution_1&physicaltopic=002&physicaltopic_options=physical_2&race=00&race_options=raceall_1&sex=0&sex_options=sexboth_1&statefips=06&statefips_options=area_states).


## Data Cleaning and Exploratory Data Analysis

Next, we created a scatterplot to graph the Air Pollution vs. the Income for all the counties and encountered a few outliers. We used a mathematical formula, called the IQR rule to remove the outliers so a trend would be more visible. 

To find a correlation, we used linear regression to get a line of best fit. We found the correlation coefficient $r^2 \approx{-0.30}$, which indicates some negative correlation. This means the lower the air pollution, the higher the incomes; however, to reiterate, this is a weak correlation.

![](sctr.png#center)


<iframe src="/plotly/income_aqi.html" width="100%" height="400px" style="border:none;"></iframe>

