# General Issues

## Time Series Analysis

We have a few primary issues working with time series data that make it distinct from traditional, sampled statistical data.  

1. Time series data is **time dependent**.  The *iid* (independent and identically distributed) does not hold when time dependence is observed.  Standard linear regression models will not provide interperable results.
2. Seasonality trends exist.  The above time dependency refers primarily to close temporal adjacenecy, but seasonal trends and global data trends are also potentially observable.

Most methods also make a *stationarity* assumption.  This requires that the data have, over time:

* a constant mean;
* a constant variance;
* an autocoveriance that is not temporally dependent.