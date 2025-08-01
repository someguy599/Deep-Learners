
# Final Project -- Analyzing European Soccer 

## Introduction
We investigated data from European professional soccer leagues between 2007 and 2016. We built models that could predict ____ from ____. 

## Data Acquisition
We obtained our data as csv files from Kaggle from the [European Soccer Database](https://www.kaggle.com/datasets/hugomathien/soccer). We also incorporated data on goals scored from Kaggle's [supplemental database](https://www.kaggle.com/datasets/jiezi2004/soccer). The data includes data about players' attributes (e.g. height, weight, age) and match results between European teams in each league. 

## Data Cleaning
### Cleaning Player Dataset
For our player attributes, we imputed data for the columns of categorical variables (dominant foot, attacking work rate, defensive work rate). We simply replaced any missing and nonsense values with the most frequent category. Additionally, we used one-hot encoding and ordinal encoding to convert these categorical variables to integers that our models can input. 

Each player in our dataset has over 30 standardized quantitative variables ranging from 0 to 100 that indicate various athletic qualities (e.g. abiility to handle penalties). 

We merged our two player attributes datasets into one dataframe for easier indexing where each row represents a season that a given player was rated. 

### Cleaning Match and Team Dataset
INSERT TEXT HERE


## Exploratory Data Analysis

[Click here to view the EDA](index.html)

Below is a histogram and KDE (smoothed out histogram) of player potential of all the more than 11,000 players in our dataset. Player potential refers to a player's future ability to perform at a high level, and this value ranges from 0 to 100. The distribution is approximately normally disitrbuted with most players' ratings between 60 and 90. 
![](PotentialHistogram(Normal).jpg#center)

### Correlation Matrices

This heatmap shows the correlation matrix between different player attributes. Correlation values range from -1 to 1, where:
- 1 means two traits increase together,
- -1 means one increases while the other decreases,
- 0 means no relationship.
![](Correlation_Matrix.png#center)

- Overall rating and potential are strongly correlated (0.77), as expected. Skills like short passing, ball control, and vision also show strong connections, indicating that good passers tend to be well-rounded technically.
- Agility, acceleration, and sprint speed are closely related, representing physical quickness.
- Defensive stats such as interceptions and tackling are related but not strongly connected to offensive traits.
- Goalkeeper attributes form a separate group, highly correlated with each other but negatively correlated with outfield player skills.


#### Technical Skills
![](heatmap.png#center) 
- Ball control is highly correlated with short passing (0.89), dribbling (0.90), and crossing (0.81), indicating that players who are good in one technical skill often excel in others.
- Volleys, finishing, and curve also show moderate to strong correlations with ball control and dribbling, further linking offensive precision with overall technique.

#### Goalkeeper Attributes
![](heatmap2.png#center)
- Goalkeeping attributes such as diving, handling, reflexes, and positioning are all highly correlated (above 0.93 in most cases).
- These values show that goalkeeper ability is largely defined by a tight group of specialized skills that behave independently from outfield traits.


### Effect of age on players

![](attributevsage.png)

Here, we examined how football players’ attributes change as they age. We used each player’s birthday and the date of their most recent data to calculate their age. Then we grouped the players by age and found the average values for five key traits: reactions, stamina, acceleration, sprint speed, and agility. The line chart we created shows how these averages shift as players get older.

The chart shows that physical traits like stamina, sprint speed, acceleration, and agility increase until around age 26 to 28 and then drop quickly after age 30. On the other hand, reactions continue to improve slightly with age and stay high even as the player gets older. This tells us that while older players may lose physical speed and movement, they often remain mentally sharp and experienced, which can still make them very effective on the field.

![](cormatrix.png)

To better understand how these attributes are related, we created a correlation matrix. The heatmap shows that physical traits such as sprint speed, agility, and stamina are strongly linked to one another and all decrease with age, while reactions are positively correlated with age. This means players who are quick often also have strong stamina and agility. Overall, the analysis shows that aging affects physical abilities more than mental sharpness, which helps explain why older players can still perform well in roles that rely on awareness and decision-making rather than speed.

### Bookmarkers

![](BookmarkerEvaluations.png)

One of the features that our model uses to predict a teams perfomance during a season are the betting odds from Bookmarkers so we evaluated the performance of these Bookmakring companies using their odds and turning them into the probabilities for the outcome of games. Then extrapolating a result and determining the accuracy, bier score, and margin which are graphed above.

## Modeling

## Random forest for Match Prediction
Using random forest regression, we built a model that takes in a certain team and season, and then would predict the score for each game the team had in that season's schedule. Random Forest Regression builds many decision trees, each trained on a random subset of data and features (bootstrapping + feature sampling). Each tree predicts a numerical value, and the forest’s final output is the average of all tree predictions. This ensemble approach reduces overfitting, captures non-linear patterns, and is robust to outliers while requiring no feature scaling. For example, when we run the model using the team Real Madrid, and the season 2015-16, here are the results of the model compared to the team's actual performance that season:

**Actual Summary**
- Average Goals Scored by Team: 2.89
- Average Goals Conceded: 0.89
- Record (W-D-L): 28-6-4
- Season Score: 90 points
  
**Predicted Summary**
- Average Goals Scored by Team: 2.92
- Average Goals Conceded: 1.32
- Record (W-D-L): 29-7-2
- Season Score: 94 points

## Neural Network for Rating Prediction 
Additionally, we created a neural network to predict a soccer player's rating for the next season based on their attributes and ratings from the past three seasons. We initially experimented with regression models like OLS, Lasso, and Ridge for rating prediction, but these models struggled to account for time series data from a given player. 

Our neural network is an LSTM (Long Short-Term Memory) model that analyzes timeseries data. It looks at the complex features of the various players in our dataset and uses them to discover patterns. The neural network is trained from a model with randomly selected values chosen as "weights" and then updates these weights during training "epochs" during which the model fine-tunes its results. The result is a predicted rating for the next season for the player. 

To train our model, we first split our dataset of players randomly into a training and testing set with 80% of the data being used for training. None of our testing set overlapped with the training data set, and as a result, we were able to evaluate our model's accuracy based on how well it performs on the unseen test dataset. 

We created a widget that models the predicted and actual player ratings with respect to their age. The ratings are outputted on a scale from 0 to 100. Our model ensures that there is no data leakage, which is the phenomenon where a model looks at future data to predict the past. Our LSTM neural network prevents this by utilizing backpropagation only throughout past data to update the model. Overall, our model is on average about 4 rating points off the true value of a player's rating for a given season, which is impressive given the volatility of soccer player performance throughout their career. 

## Conclusion
