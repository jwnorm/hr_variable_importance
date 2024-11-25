# Home Run Variable Importance in Major League Baseball

> **Note:** This repo is related to my final project for ISE537 at NC State University.

## Overview

This project concerns analyzing Statcast data queried from Baseball Savant using the `sabRmetrics` package in `R` to determine which features are most important in determining whether a base hit is a home run or not. This is essentially a variable selection problem that is analyzed with the following methods:

-   Stepwise regression

    -   Forward selection

    -   Backward elimintaion

-   LASSO regression

-   Elastic Net regression

## Data

The data examined is from the 2024 MLB regular season for all Statcast events that resulted in a base hit. There are some row-wise exclusions, including:

-   No inside-the-park home runs

-   No bunts

-   No missing fields in any columns

Similarly, the columns of 115 data elements were reduced to a subset of 27 variables. All catetgorical variable were excluded for computational reasons.

## Model

The model for this analysis is logistic regression to predict whether a base hit is a home run or not. If the set of all predictors is $P$, then the equation for the full model is:

$$
p = 
\frac{
\exp(\hat\beta_0 + \sum_{p \in P}{\hat\beta_p x_p})
}
{
1 + \exp(\hat\beta_0 + \sum_{p \in P}{\hat\beta_p x_p})
}
$$

Where $\hat\beta_0$ represents the intercept term.
