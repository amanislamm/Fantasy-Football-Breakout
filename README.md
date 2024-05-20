# Fantasy-Football-Breakout
Second Year Fantasy Football Breakout
Executive Summary

Objective: The aim of our project is to develop a machine learning model capable of accurately predicting fantasy football points for second-year wide receivers, leveraging advanced football analytics.

Approach: Faced with the challenges of a high-dimensional and multicollinear dataset, we used the elastic net regression method. This choice effectively addresses both issues.

Results: Our model has yielded a competitive prediction of the fantasy performance of second-year wide receivers. We are committed to further refining and adjusting it to improve accuracy.

Impact: Fantasy football enthusiasts rely on precise player projections to make well-informed decisions during drafts and lineup selections. Leveraging PFF's extensive receiving performance metrics, our goal is to craft a predictive model aiding fantasy football managers in identifying wide receivers poised for a breakout second year, as measured by a significant increase in fantasy points. This, in turn, can empower fantasy owners to excel in their leagues and generate profits.

Introduction

As Fantasy Football continues to gain popularity across diverse demographics, the demand for sophisticated fantasy-assisting tools has surged. Ideally, our model will furnish fantasy players with a robust and accurate instrument to help them achieve their objectives.

Dataset Description

Data Source: Pro Football Focus (PFF), Pro Football Reference, NFL.com

Data Characteristics: The dataset encompasses receiving summaries of NFL wide receivers over a single season, amalgamating receiving grades and statistics for each receiver with recorded receiving stats. Given the similarity and correlation among many attributes/statistics, multicollinearity is prevalent.

Suitability of Data: Widely utilized by NFL teams and non-NFL analysts alike (e.g., ESPN, FantasyPros), this dataset provides a plethora of player statistics, ranging from basic to intricate, making it ideally suited for our objectives.

Pro Football Focus (PFF): PFF furnishes detailed player grades and metrics, including advanced statistics beyond traditional metrics, snap counts, and play-by-play data.
Pro Football Reference: This source offers extensive historical player data known for its accuracy and reliability.
NFL.com: Providing official and up-to-date statistics and player information, NFL.com also supplies official NFL Draft Prospect Grades for each year.
Methodology

Data Preprocessing:

Data Cleaning: Given the dataset's high dimensionality, several columns were eliminated prior to exploratory data analysis (EDA), utilizing domain knowledge. Various methods were employed to address NaN values, including row deletion, mean replacement, and zero substitution.
Feature Engineering: While the in-depth statistics from PFF reduced the need for extensive feature engineering, we crafted the fantasy points column using a combination of yards, receptions, touchdowns, and lost fumbles.
Data Transformation: Categorical variables were either dropped or ordinally encoded. Variables such as player name and rookie year were dropped, while College and Team Name were ordinally encoded based on their correlation with the target variable (points scored in the following year).
Train-Test Split: Statistics for rookie wide receivers from 2017-2022 served as the training data, with the years 2022 and 2023 utilized for the test set.
Model Selection: Elastic net regression was chosen due to the dataset's extreme multicollinearity and high dimensionality. Balancing Ridge and Lasso, elastic net offers a combined approach to addressing both challenges.

Model Training and Tuning: Elastic Net Regularization was employed to mitigate overfitting, given the dataset's multicollinearity and high dimensionality.

Results:

Model Evaluation: We evaluated our model using R2 and RMSE. RMSE serves as a measure of the average magnitude of error between the predicted and actual values, which offers insight into the model's accuracy in estimating the target variable. In the context of our model, this is the most important metric because a higher RMSE would mean more inaccurate predictions, which is exactly what we don’t want. Lower RMSE values indicate closer predictions to the actual fantasy points scored, signifying better model performance and increased reliability. The other metric, R2, represents the proportion of variance in fantasy football points that can be explained by the independent variables. This metric aids in assessing the model's ability to capture the variation in player performance based on selected features. A high R2 and a relatively low RMSE is ideal, as it signifies the following: 1. The model is accurate enough to predict the points of a player within a reasonable margin of error 2. The variability of the error is accounted for by the independent variables (this means that we are generally using the right variables for our prediction, as there will always be variance in something as random and unpredictable as live sports). 
