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

#### Methodology
The paper starts with simple Poisson model.
Let : 

$Y_{1}$ = Goals scored by one team

$Y_{2}$ = Goals scored by the other team

Assuming both $Y_{1}$ and $Y_{2}$ to be independent. But this is not sufficient, since as said in the introduction section, the teams play against each other and if a team scores a goal it can affect the other team's gameplay and strategy. 

Next the paper discusses Bivariate Poisson Model. They construct three independent Poisson random variables: 
$Z_0 = Poisson(\lambda_{0})$

$Z_1 = Poisson(\lambda_{1})$

$Z_2 = Poisson(\lambda_{2})$

Then defines:
$Y_{1} = Z_1 + Z_0$

$Y_{2} = Z_2 + Z_0$

Since both the teams share $Z_0$ it creates a dependence between the two teams. But since it can't model negative dependence, the study opts for another model, which is the Bivariate Conditional Poisson Model (BCP) .

The structure follows : 

  $Y_1 \sim Poisson(\lambda_1)$

and

  $Y_2 \mid Y_1 = y_1 \sim \text{Poisson}\left(\mu_2 e^{\phi y_1}\right)$

The idea is to model the goals of team 1 first and then model team 2's goals conditional on Team 1's goals. The parameter $\phi$ is the dependence controlling factor. 

The interpretation is :
1. $\phi$ = 0 : $e_{\phi}$ = 1 | No dependence
2. $\phi \textgreater 0$ | Positive Dependence (More goals by Team 1 are associated with more expected goals for Team 2)
3. $\phi \textless 0$ | Negative Dependence (More goals by Team 1 are associated with fewer expected goals for Team 2)

(Some More stuff to add)

##### Regression Model
