# HW10


This homework will reuse the candy dataset, not with the goal of predicting whether a candy contains chocolate.

Recall: The data was obtained from [https://www.kaggle.com/fivethirtyeight/the-ultimate-halloween-candy-power-ranking](https://www.kaggle.com/fivethirtyeight/the-ultimate-halloween-candy-power-ranking). The original article and analysis is available at
[https://fivethirtyeight.com/features/the-ultimate-halloween-candy-power-ranking/](https://fivethirtyeight.com/features/the-ultimate-halloween-candy-power-ranking/).

```{r}
candy <- read_csv('http://math.montana.edu/ahoegh/teaching/stat446/candy-data.csv')
candy <- candy %>% mutate(chocolate_factor = as.factor(chocolate))
```

##### Context

What’s the best (or at least the most popular) Halloween candy? That was the question this dataset was collected to answer. Data was collected by creating a website where participants were shown presenting two fun-sized candies and asked to click on the one they would prefer to receive. In total, more than 269 thousand votes were collected from 8,371 different IP addresses.

##### Content

candy-data.csv includes attributes for each candy along with its ranking. For binary variables, 1 means yes, 0 means no. The data contains the following fields:

- chocolate: Does it contain chocolate?
- fruity: Is it fruit flavored?
- caramel: Is there caramel in the candy?
- peanutalmondy: Does it contain peanuts, peanut butter or almonds?
- nougat: Does it contain nougat?
- crispedricewafer: Does it contain crisped rice, wafers, or a cookie component?
- hard: Is it a hard candy?
- bar: Is it a candy bar?
- pluribus: Is it one of many candies in a bag or box?
- sugarpercent: The percentile of sugar it falls under within the data set.
- pricepercent: The unit price percentile compared to the rest of the set.
- winpercent: The overall win percentage according to 269,000 matchups.

##### Acknowledgements:

This dataset is Copyright (c) 2014 ESPN Internet Ventures and distributed under an MIT license. Check out the analysis and write-up here: The Ultimate Halloween Candy Power Ranking. Thanks to Walt Hickey for making the data available.

## 1 (3 points)
Use the `glm()` function to fit a regression model to understand if other factors can be used to model whether a candy item contains chocolate. Make sure to include `winpercent` but you are free to consider other variables too. Interpret the output.

## 2.  (8 points)
Using [Stan](https://mc-stan.org/docs/2_18/stan-users-guide/logistic-probit-regression-section.html) implement Bayesian logistic regression.

#### a. (2 points)
Write out the model, including priors. Note you did this in the last quiz.

#### b. (3 points)
Implement Bayesian logistic regression using Stan. This [Stan link](https://mc-stan.org/docs/2_18/stan-users-guide/logistic-probit-regression-section.html) will be helpful.

#### b. (3 points)
Interpret your output and explain the results without statistical jargon.

## 3.  (9 points)
Building on Quiz 9. Write your own Metropolis-Hastings sampler to estimate the parameters in the model specified in Q2a. Print out trace plots for a few of your variables. Note your answers should be very similar to those found with Stan.
