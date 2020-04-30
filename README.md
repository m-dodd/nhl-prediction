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

All preprocessing was performed in Python. Logistic Regression was performed using R as per the project requirements.

## Results

We learned two things during this project that we could use as a baseline to judge our model.

1. The home team wins approximately 54.7% of the time.
2. The theoretically upper limit for NHL predictions is approximately 62%. This result is from:
    > Weissbock, J. (2014). *Forecasting Success in the National Hockey League using In-Game Statistics and Textual Data* (Doctoral dissertation, University of Ottawa).

With these two metrics in mind we had set a reasonable target of 57% accuracy for our model recognizing that there is a lot of additional work we could do to improve it in the future.

We achieved an accuracy of 57.4% over the entire 2018-2019 season; predicting 730 / 1271 correct results.

But, unfortunately this was not good enough to quite our day jobs as we would not have been able to beat the bookies:

![Tough to beat](/imgs/results.png)

Although, that's not the result we wanted it's not as bad as it looks as we would have lost ~$250 after wagering $12,710 so we are only losing about $0.02 for every $1 wagered and that's better than most games of chance at a Casino so the additional fun factor of having placed wagers may be justified. :sunglasses:
