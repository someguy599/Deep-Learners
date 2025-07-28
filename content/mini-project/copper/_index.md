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

MSE: 0.0093

{{< figure src="comex.png" alt="COMEX grpah" caption=" " class="center" width="100%" >}}

MSE: 1200677.8921

{{< figure src="shfe.png" alt="SHFE grpah" caption=" " class="center" width="100%" >}}

MSE: 0.2997

We Mean Square Error to find the quality of the prediction models. We used Random Forest Regression, a machine learning algorithm that predicts continuous values by combining the outputs of many decision trees. Each tree in the forest is trained on a random subset of the data and features, which helps reduce overfitting and improve generalization. The model averages the predictions of all the trees to produce a final result, making it more robust and accurate than a single decision tree. It’s particularly effective for handling nonlinear relationships and datasets with many input variables.




<iframe src="https://github.com/ucd25-cosmos-deeplearners/ucd25-cosmos-deeplearners.github.io/blob/main/content/mini-project/copper/index.html" width="100%" height="600" style="border:none;"></iframe>


