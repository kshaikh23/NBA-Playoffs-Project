# The Play of the Playoffs
In the world of basketball, more specifically the NBA, clutch is a term that is thrown around very liberally; the term relates to the phenomenon where athletes excel under pressure. Analysts attempt to identify different factors that indicate whether or not a team is constructed with clutch players or playoff culture, among many other things, that culminate to winning the ultimate prize, The Larry O’Brien Trophy. Supposedly, the NBA playoffs is a whole different animal compared to the regular season. We wanted to see if the analytics supported this theory. We set out to see the difference between regular season and playoff play, both for individuals and teams. 

After scraping and cleaning data for basketball-reference.com using the pandas library:

We ran multiple t-tests on different team statistics, comparing them in the regular and postseason, in order to determine whether or not there is a statistically significant difference with these stats in these situations. We ran t-tests for the stats: Pace, True Shooting %, 3-Point %, Free-Throw %, 3-Point Attempt rate, Free-Throw Attempt rate, Assist %, Turnover %, Offensive Rebound %, Defensive Rebound %, Offensive Rating, and Defensive Rating.

We found that there is not a statistically significant difference in Free-Throw %, 3-Point Attempt rate, Turnover %, and Defensive Rebound %. In the playoffs, Pace of play, True Shooting %, 3-Point %, Assist %, Offensive Rebound %, and Offensive Rating all decrease while Free Throw Attempt rate and Defensive Rating increase. These difference are visualized in a catplot which you can see in the code.

We used linear regression to predict points per game for players in the playoffs based on regular season stats. The stats that we used to predict playoff points per game included regular season points per game, assists per game, total rebounds per game, true shooting percentage, and player efficiency rating. Linear regression was a suitable choice for this problem because the model allows for a straightforward interpretation of how regular season stats influence playoff performance. Additionally, we made sure to create a correlation heat map between different statistics. This heatmap helped us identify which stats would be best used as features to predict points as the two stats would be correlated. Initially, we just used points in the regular season to predict points in the playoffs. However, we applied the info from the correlation visualization to create a model that should be accurate. When we tried varying the features that we used for prediction to the 5 stats most correlated with points, according to the correlation heatmap, we got a model that still wasn’t as accurate as we liked. However, we found that the additions of assists per game, total rebounds per game, true shooting percentage, and player efficiency rating made a more accurate model, other stats that were correlated with points, made the most accurate predictions.

We used both R2 and Mean Squared Error as measures of accuracy for our linear regression model. The R2 value for the initial model that just used regular season points per game as a predictor for postseason points per game had an R2 value of 0.695 and a Mean Squared Error of 13.468. When we used points per game, minutes played, free throws attempted, turnovers, and assists we got a model with R2 value 0.695 and Mean Squared Error 13.479. The most improved model with points, assists, rebounds, true shooting percentage, and player efficiency rating as the predicting features had an R2 value of 0.711 and a Mean Squared Error of 12.760.
