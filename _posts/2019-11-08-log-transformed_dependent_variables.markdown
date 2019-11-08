---
layout: post
title:      "Log-Transformed Dependent Variables"
date:       2019-11-08 15:13:54 +0000
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

However - the real issue came in 

The very consistent 
https://data.library.virginia.edu/interpreting-log-transformations-in-a-linear-model/
