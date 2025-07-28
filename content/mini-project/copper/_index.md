---
title: "Copper Price Prediction"
date: 2025-07-23
---

## Introduction
The goal of this project is to develop a machine learning model that predicts the daily closing price of U.S. copper futures (COMEX) using only data available before the market opens. By leveraging historical price data from COMEX, SHFE, and LME, the model aims to support informed decision-making for traders, analysts, and researchers while maintaining realistic forecasting conditions without data leakage.

## Data Cleaning
In the data cleaning stage, we standardized copper futures data from COMEX, SHFE, and LME by converting column names to lowercase, setting datetime indices, and sorting rows chronologically. Missing values were forward-filled when appropriate. SHFE prices were converted from CNY per ton to USD per pound using daily exchange rates, while LME prices were similarly converted from USD per ton. This processing ensured consistency across datasets for modeling and analysis.

## Exploratory Data Analysis

{{< figure src="lme.png" alt="LME grpah" caption=" " class="center" width="100%" >}}

{{< figure src="comex.png" alt="COMEX grpah" caption=" " class="center" width="100%" >}}

{{< figure src="shfe.png" alt="SHFE grpah" caption=" " class="center" width="100%" >}}


<iframe src="index.html" width="100%" height="600" style="border:none;"></iframe>
