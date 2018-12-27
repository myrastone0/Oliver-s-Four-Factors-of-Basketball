# What impact do Oliver's Four Factors have on a basketball team's success?

In an attempt to determine the most important attributes needed for a basketball team to win games, Dean Oliver identified what he called the "Four Factors of Basketball Success." In order of importance (or relative weight), those factors are:

- Shooting (40%)
- Turnovers (25%)
- Rebounding (20%)
- Free Throws (15%)

These factors can be applied to a team's offense and defense, so we actually have eight factors that can determine a team's success. The specific stats we'll be looking at are:

- **Offensive Factors**
    - Effective Field Goal Percentage: This is a scale corrected measure to account for 3 point shots. Since 3 pointers are more difficult and are worth more, they are given greater weight than 2 point shots.</br>

        $$\mathrm{eFG}\% = \frac{\mathrm{FGM}+0.5*3\mathrm{PM}}{\mathrm{FGA}}$$
        Where FGM is the number of field goals made, 3PM is the number of 3 pointers made, and FGA is the number of field goals attempted.

    - Turnover Percentage: This is the percentage of possessions that ended without a field goal attempt or a free throw attempt.
        $$\mathrm{TO}\% = \frac{\mathrm{Number\, of\, possessions\, ending\, in\, a\, TO}}{\mathrm{Total\, number\, of\, possessions}}$$

    - Offensive Rebound Percentage: This is the number of offensive rebounds divided by the number of available *rebounds* after a missed field goal attempt.
        $$\mathrm{OREB}\% = \frac{\mathrm{teamOREB}}{\mathrm{teamOREB + opptDREB}}$$
        Where teamOREB is the number of offensive rebounds and opptDREB is the number of defensive rebounds of the opponent.

    - Free Throw Rate: This is the number of free throws made per field goal attempt.
        $$\mathrm{FTR} = \frac{\mathrm{FTM}}{\mathrm{FGA}}$$
- **Defensive Factors**
    - Opponent's Effective Field Goal Percentage
    - Opponent's Turnover Percentage
    - Opponent's Free Throw Rate

    These three factors are computed the same as the offensive factors, but using the opponents stats. For defensive rebounds we instead calulate the team's number of defensive rebounds per number of the opponent's field goal misses that are available for rebound.
    - Defensive Rebound Percentage:
        $$\mathrm{DREB}\% = \frac{\mathrm{teamDREB}}{\mathrm{teamDREB + opptOREB}}$$


## Our Goal

We wish to determine if the relative importance of each factor (eFG%, TO%, OREB%, and FTR) actually follows Oliver's breakdown of 40/25/20/15.

Using the 2016-2017 NBA Team Box Stats obtained from [Kaggle](https://www.kaggle.com/pablote/nba-enhanced-stats), let's see if the data follows Oliver's breakdown to predict the number of wins a team amasses during the regular season.

We'll use a Random Forest and Linear Regression to model the data.
