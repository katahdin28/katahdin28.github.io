---
layout: post
title:      "Time Series ARIMA Graphing"
date:       2020-01-27 10:22:39 +0000
permalink:  time_series_arima_graphing
---

How to create a pleasant-looking set of graphs for ARIMA forecasts, both for train-test viewing and for forecasting out of sample.

def arima_forecast(zipc, pdq_combo, break_date, term_date):
    """ Plots forecast graph based on a split / test date and forecast end date

    Arguments:
    zipc -- integer zipcode value
    pdq_combo -- three-element tuple of pdq inputs
    break_date -- end of test data / start of forecast
    term_date -- end of forecast period
    """    
    df_orig = create_ts(zipc)
    df_trial = df_orig[:break_date]
    model = ARIMA(df_trial, order = pdq_combo)
    out = model.fit()
    plt.clf()
    fig, ax = plt.subplots()
    fig = out.plot_predict(start_date, term_date, plot_insample = False, ax = ax)
    ax = df_orig.plot(ax=ax)
    plt.show()

