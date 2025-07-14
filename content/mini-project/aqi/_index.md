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
## Data Table
| County | Air Pollution (PM2.5) | Per Capita Income ($) |
|--------|------------------------|------------------------|
| Alameda County | 11.8 | 106657 |
| Alpine County | 9.7 | 75395 |
| Amador County | 14.2 | 50020 |
| Butte County | 16.1 | 56847 |
| Calaveras County | 12.7 | 58425 |
| Colusa County | 12.8 | 58303 |
| Contra Costa County | 11.1 | 103218 |
| Del Norte County | 10.3 | 47141 |
| El Dorado County | 14.6 | 84533 |
| Fresno County | 20.3 | 52728 |
| Glenn County | 17.0 | 53013 |
| Humboldt County | 8.8 | 57264 |
| Imperial County | 11.9 | 47991 |
| Inyo County | 12.2 | 64246 |
| Kern County | 21.1 | 47350 |
| Kings County | 20.0 | 43994 |
| Lake County | 9.6 | 48198 |
| Lassen County | 12.4 | 43736 |
| Los Angeles County | 15.6 | 78302 |
| Madera County | 17.1 | 46709 |
| Marin County | 8.6 | 180575 |
| Mariposa County | 21.3 | 65423 |
| Mendocino County | 12.4 | 59050 |
| Merced County | 15.3 | 46654 |
| Modoc County | 10.4 | 60674 |
| Mono County | 39.1 | 70699 |
| Monterey County | 8.8 | 68943 |
| Napa County | 10.3 | 94973 |
| Nevada County | 12.4 | 75539 |
| Orange County | 12.7 | 88897 |
| Placer County | 13.1 | 85265 |
| Plumas County | 21.1 | 64856 |
| Riverside County | 14.8 | 53750 |
| Sacramento County | 14.9 | 65104 |
| San Benito County | 8.9 | 66310 |
| San Bernardino County | 17.4 | 51194 |
| San Diego County | 20.6 | 79122 |
| San Francisco County/city | 10.5 | 164807 |
| San Joaquin County | 15.1 | 59361 |
| San Luis Obispo County | 10.0 | 72721 |
| San Mateo County | 9.8 | 172828 |
| Santa Barbara County | 9.3 | 82736 |
| Santa Clara County | 12.5 | 151003 |
| Santa Cruz County | 11.1 | 88581 |
| Shasta County | 9.8 | 57637 |
| Sierra County | 10.8 | 53251 |
| Siskiyou County | 10.9 | 55052 |
| Solano County | 12.4 | 64514 |
| Sonoma County | 8.3 | 83408 |
| Stanislaus County | 15.6 | 53058 |
| Sutter County | 16.7 | 53900 |
| Tehama County | 13.3 | 49265 |
| Trinity County | 10.2 | 38243 |
| Tulare County | 20.8 | 48253 |
| Tuolumne County | 16.2 | 56239 |
| Ventura County | 7.9 | 78091 |
| Yolo County | 15.9 | 67778 |
| Yuba County | 16.3 | 50587 |

---
## Data Cleaning and Exploratory Data Analysis

Next, we created a scatterplot of air pollution vs. income for all California counties. However, we encountered a few outliers, so we used the 1.5 IQR Rule to remove them to avoid skewing the results. 

We re-analyzed the data with linear regression to acquire a line of best fit. Our data's correlation coefficient $r \approx{-0.30}$ indicates a weak, negative correlation between income and air pollution. In other words, the lower the air pollution for a county, the higher the predicted average income.

![](sctr.png#center)

---
## Interactive Map Showing County Data
<iframe src="/plotly/income_aqi.html" width="100%" height="400px" style="border:none;"></iframe>

