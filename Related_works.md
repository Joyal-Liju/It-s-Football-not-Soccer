## Related works

### 1 . A Bayesian bivariate conditional Poisson regression for goal dependence in the English Premier League
####  Authors: Marcus Nolan, Wagner Barreto-Souza, Luiza S.C. Piancastelli and Raanju R. Sundararajan

This paper investigates the relationship between the number of goals scored
by the home and away teams. It begins with the standard Poisson framework
for football scores but points out that treating the two teams' goal counts
as independent may be unrealistic. The authors therefore develop a Bayesian
Bivariate Conditional Poisson (BCP) model that allows the goal counts to
have either positive or negative dependence.

Using 1,140 Premier League matches from the 2018–19, 2020–21 and 2023–24
seasons, the authors find that the BCP models provide better joint predictive
performance than independent Poisson models. Their preferred model finds
negative dependence between home and away goals, while attendance is
positively associated with home-team scoring but has no clear association
with away-team scoring.

**Relevance to this project:**  
This paper provides a useful starting point for investigating the assumptions
behind simple Poisson models. In particular, it raises the question of
whether the goals scored by two opposing teams can really be treated as
independent. It also suggests possible future variables such as team
strength, attendance, fouls, and other match-level information.

---

### 2. A market-calibrated accelerated failure time model for in-play football forecasting
#### Authors: Lawrence Clegg , Zixing Song, and John Cartlidg

This paper approaches football forecasting from a different perspective.
Instead of asking only how many goals a team will score, it models the time
until the next goal using a Weibull accelerated failure time model.

The authors extend this model to in-play forecasting by incorporating
half-specific scoring behaviour, post-shot expected goals (PSxG), red cards,
and pre-match information from Betfair Exchange prices. They use Monte Carlo
simulation to generate possible completions of a match from its current
state and estimate the probabilities of a home win, draw, or away win.

The resulting calibrated model achieves 70.2% classification accuracy across
140 Premier League matches, close to the 70.6% accuracy of the Betfair
market. However, the authors note that the model still lacks several types
of in-play information, such as substitutions and richer measures of
attacking momentum.

**Relevance to this project:**  
This paper is particularly relevant to the long-term direction of this
project. It demonstrates how a static model of football scores can be
extended into a dynamic, in-play model. It also motivates the central
question of this project: how much information about a match's future is
contained in its current state, and what information should that state
include?
