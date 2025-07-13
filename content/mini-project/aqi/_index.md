---
title: "Relationship Between Air Quality and Income in California"
showToc: true
tocOpen: true
summary: Our goal was to determine whether air quality and people's income are correlated among California counties.
date: 2025-07-08
---

## Introduction

Our goal was to determine whether air quality and people's income are correlated among California counties.

---
## Data Acquisition


First, we obtained data from publicly avilable government datasets on air pollution—specifically PM2.5 concentration—and income from all counties within California. 

We found the average annual income per capita from each California county [here](https://fred.stlouisfed.org/release/tables?eid=266305&rid=175). This data comes from the Federal Reserve Bank of St. Louis (FRED) from 2023.


We found PM2.5 concentrations, which were measured in micrograms per cubic meter (µg/$m^3$), [here](https://hdpulse.nimhd.nih.gov/data-portal/physical/table?age=001&age_options=ageall_1&demo=234&demo_options=air_pollution_1&physicaltopic=002&physicaltopic_options=physical_2&race=00&race_options=raceall_1&sex=0&sex_options=sexboth_1&statefips=06&statefips_options=area_states). This data comes from the NIH. 

---
## Data Cleaning and Exploratory Data Analysis

Next, we created a scatterplot of air pollution vs. income for all California counties. However, we encountered a few outliers, so we used the 1.5 IQR Rule to remove them to avoid skewing the results. 

We re-analyzed the data with linear regression to acquire a line of best fit. Our data's correlation coefficient $r \approx{-0.30}$ indicates a weak, negative correlation between income and air pollution. In other words, the lower the air pollution for a county, the higher the predicted average income.

![](sctr.png#center)

---
## Interactive Map Showing County Data
<iframe src="/plotly/income_aqi.html" width="100%" height="400px" style="border:none;"></iframe>

