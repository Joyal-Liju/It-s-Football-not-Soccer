## Report on : ‘A Bayesian Bivariate conditional Poisson regression for goal dependence in the English Premier League’ 
### By: Nolan et.al


#### Introduction

The paper explores the dependency between goals scored by the Home and Away teams in Football matches, as these goals determine the game. The case of dependency here matters since a team strategy can change based on whether the other team has scored a goal or not. 

Poisson distribution is considered as the starting point to understand the dependency of the goals. Additionally a bivariate Poisson distribution can be used to establish dependency between the two variables. Bivariate distribution counts whole numbers and is suitable for counting the number of goals scored in a football match, but it can only model positive dependency. 

So the paper proposes a **Bayesian Bivariate Conditional Poisson Regression**  to model the goal scored by the Home and Away team, along with it's dependency (both positive and negative). The paper considers attendance (the crowd) and fouls committed as explanatory variables for this model. 

**Objective** : The objective of this study can be said as to determine whether the Home and Away goals are dependent and if so, develop a model that is able to represent his dependence more realistically than independent Poisson or conventional bivariate Poisson models.

#### Data
The data used for this paper's study comes two sources :
  1. Football-data Uk (Match Results and Statistics) | [[>]](https://www.football-data.co.uk/)
  2. FBref (Stadium Attendance Figures) | [[>]](https://fbref.com/)

The paper used English Premier League data across three seasons and examines 1,140 matches. The three seasons were chosen intentionally as pre-Covid, during Covid, and after-Covid.
The main variables used are :

| Variable | Meaning |
|-----------|----------|
|Home Goals| Goals Scored by the Home Team |
|Away Goals| Goals Scored by the Away Team |
|Attendance | Number of spectators |
|Home Fouls | Fouls committed by the Home Team|
|Away Fouls | Fouls committed by the Away Team|

##### Exploratory Analysis
Before constructing the Model the paper shares some preliminary insights from the data they collected. The paper observes that Home teams won more often in matches. During the transition from the pre-pandemic season to the restricted-attendance season:
 - home goals decreased from 1.57 → 1.35
 - away goals increased slightly from 1.25 → 1.34
The authors say that this is consistent with a possible reduction in home advantage when spectators were absent, but importantly, they do not claim that attendance caused the change.

Further, attendance shows a weak relationship with home fouls. The paper emphasizes that these correlations are descriptive, not causal.
