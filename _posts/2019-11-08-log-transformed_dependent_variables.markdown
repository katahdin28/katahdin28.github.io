---
layout: post
title:      "Log-Transformed Dependent Variables"
date:       2019-11-08 10:13:55 -0500
permalink:  log-transformed_dependent_variables
---


The biggest issue I faced in putting together a recent analysis of the factors influencing home prices in King County, WA was in appropriately interpreting the magnitude of the impact of a log-transformed dependent variable.

For context, the data used: ~21,500 home sales in King County, from 2014-2015.

_Home Factors Regression:_
- Identified top usable home-specific predictors of price
- Living space square footage
- Lot size
- Home condition rating
- Waterfront proximity
- Renovation status
- Number of floors
- Whether house was viewed
- Zipcode dummy variables

The regression outcomes were highly predictive - with an Adjusted R-Squared of 85.7%, F-Statistic probability of <0.00, and p-values of individual regressors of <0.000.

However - the primary issue came in interpreting the coefficients of the zipcode dummy variables.  The zipcode dummy variable coefficient values ranged on the low end from 0 to the high end of ~1.5 ln(dollars).  The average home sale price in this region over the time period was ~13 ln(dollars), and the most expensive home was ~14 ln(dollars).  Intuitively, the contribution of the most-expensive zip code coefficient to overall predicted price in that zip code should be approximately 10% - as the cumulative effect of the other factors (the intercept, lot size coefficient, home condition coefficient etc.) add up to 11-12 ln(dollars).  

The issue I am grappling with currently is that this is not consistent with the econometrics literature on interpreting log transformaitons in a variable.  [This literature ](https://data.library.virginia.edu/interpreting-log-transformations-in-a-linear-model/) suggests that the appropriate way to calculate the impact of coefficients on log-transformed outcomes is to take the exponent of the coefficient, minus one, to get the proportional impact of the variable on the outcome.  The implication of using this method is that my highest-premium zip code, with a coeff. of 1.4 ln(dollars), should be responsible for an almost **350% increase** in home price in dollars.  Furthermore, the typical zip code contribution would fall in the **30%-100% increase** in home price in dollars.  Frankly, given the other contributing factors, also with cumulative ln(dollar) coefficient contributions of greater than 1.4 ln(dollars), in aggregate - e.g. the contribution of 1,000 sqft of living space vs. per sqft of living space, I find it very difficult to recommend the interpretation that my zip codes are quite as impactful as this approach suggests.

My interpretation in the final document was to evaluate the percent of the total predicted price in ln(dollars) that each zipcode dummy variable coefficient value contributed in ln(dollars).  This yields much more palatable values in the range of 0-10%, and avoids such attributed extreme values as the ~350% price increase.

I hope to nail down this difficult interpretive issue and return to update this piece with a more complete answer.

