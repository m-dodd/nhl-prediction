# NHL Prediction

![More Fun](/imgs/hockey-betting.jpg)

This was a group project and our goal was to create a Logistic Regression model to predict the winner of NHL hockey games. NHL is a strong interest of ours and sports are always a little more interesting if you bet some money on them so those are the motivating factors for the project.

## Challenges

Obviously to predict the winner of a hockey game you have to make sure that you only use information that was available prior to that game being played, but the data that is available only provides game by game (boxscore) information. This isn't very useful for prediction purposes.

## Data

We contacted [Natural Stat Trick](https://www.naturalstattrick.com/) for permission to use data from their website for our project. We did this because we wanted to use some of the more modern statistics (such as Corsi) that are in use today and these statistics are not readily available in boxscore data. The website graciously provided permission for non-commercial use. We suplemented this data with data that we had previously obtained from the [Kaggle NHL dataset](https://www.kaggle.com/martinellis/nhl-game-data).

We obtained data for the 2014-15, 2015-16, 2016-17, 2017-18, and 2018-19 seasons.

## Preprocessing

As mentioned in the challenges section, now that we had the data we wanted we had to massage it into a format that we could use. Loosely these are the steps that we took.

1. Create running averages for each statistic for each individual team for Natural Stat Trick advanced statistics.
2. Add the NHL game ID to the Natural Stat Trick data.
3. Create running averages for each statistic for each individual team for NHL boxscore data.
4. Merge these into a single dataset.
5. For each game look at the average statistics for all games prior for the Home and Away teams and subtract the Away team statistics from the Home team to create *marginal* statistics for each game. All data is in reference to the Home Team.

We now have data in a form appropriate for machine learning.

All preprocessing was performed in Python. Logistic Regression was performed using R as per requirements.
