# Vegas Betting Odds for NBA Games

## Description of Problem
Vegas releases betting odds in order to attract bettors to bet on the outcome of a certain sports event. In this case, for an NBA game, Vegas would hypothetically say that for every dollar that a bettor bets, they will get 'x' amount of dollars if they correctly bet that a certain team wins. Otherwise, they lose their money and it goes to Vegas. However there is a fine line between attracting people to actually bet on the games so that external bettors will lose and the organization in Vegas makes the most money out of lost bets. In this project, I will be introducing several models and picking the best model that this certain organization in Vegas can use to figure out which team will likely win a sports match and so entice bettors to bet on the other team, and thus win all of their money.

Goal: We will be using data from the National Basketball Association (NBA) to figure out which team will win a given basketball matchup

## Data
I used data from Kaggle(https://www.kaggle.com/nathanlauga/nba-games) from the games.csv and teams.csv. I performed external EDA (not shown in the code) and joined them into the nba_data.csv file that is in this github repo. A thorough description of all the features and labels used are included in the code below. 

## Code
[Code for the Project Can Be Found Here](https://github.com/surengunturumasters/msds699_final_proj/blob/main/Final_Proj_Code.ipynb)

## Results
I used descriptive metrics: Precision and Recall for each class. Based on the end goal, I used precision to determine the best model to use (between a Random Forests and Logistic Regression Model) since it is important for the client (Vegas Sports Betting) to know the chance that the model result is actually the true result for future outcomes. The best model to use was Logistic regression in a pipeline with a standard scaler, simple imputer, and quantile transformer. 

## Inference
This is an example of how the model will be used. In this example scenario, imagine that the Lakers will be facing the Clippers in an upcoming NBA game where the Lakers will be at home. 
1) Inputs will be the team ids and average stats from 2018 to now as well as the season they are playing in (2020)
2) Run the pipeline Logistic Regression Model
3) If get 0, the Clippers are projected to win, otherwise the Lakers will be projected to win. 
4) Use the metrics given from the logistic model on validation data in training to determine the confidence of the projection (as explained in detail in the code). Based on the confidence, Vegas can create odds so that they can maximize their revenue off of lost bets from external bettors. 
