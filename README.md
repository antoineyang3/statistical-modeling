# statistical-modeling

This repository groups two small projects I have worked on in statistical modeling.

The first one (notebook apple_quotation.ipynb) is about statistics of extreme. The problem here is to estimate events that rarely happen so that we have very few observed data about such events. We get into the skin of a careful shareholder in Apple and want to estimate the probability that Apple's quotation decreases of more than X% in one day. 

Using the Hill estimator, we estimate the parameter of the Frechet Law that approximates the distribution of negative relative variations of Apple's quotation given a tunable threshold. Then we verify that relatively high empiric quantiles are reasonably close to Hill estimated quantiles. Finally, we use the estimator to give meaningful interpretations : less than 0.5% of negative relative variations of Apple's quotation exceed 8.83%.

Using Pick over Threshold method, we estimate the survival function of the distribution of negative relative variations of Apple's quotation above a tunable threshold. Using maximum likelihood, we estimate numerically the parameters of the general Pareto distribution that models the exceedences. We verify that the tail-parameter is close to the one we obtained using Hill estimator, and that the estimated survival function is close to the empirical survival function. Finally, we use the estimated survival function to provide meaningful interpretations : 4.7% of the negative relative variations of Apple's share are above 5.06%.


The second one (notebook rainfall_forecast.ipynb) is about time series. We want to understand how time series could help predicting rainfall in a given place (Melbourne in this study). We propose to decompose the serie into trend, seasonality (of 365 days) and residual. The seasonality can be verified observing a peak at about 365 looking at the autocorrelation of the original serie. A Dickey-Fuller test allows us to verify the stationarity of the residuals. Looking at the autocorrelation of residuals, we propose two different models : MA(3) and AR(12). 

We then have to verify these models. Normality tests (Kolmogorov-Smirnov) are not successful, while significativity tests and Box Pierce tests of absence of correlation are successful for both models. The AIC and BIC tests shows the superiority of the AR(12) model, despite high computational cost. 

To make prediction, we average rainfall over month to shorten computation. We choose a SARIMA model ((0,0,0), (5,0,0,12)) because it keeps the autoregressivity of the AR model and the yearly seasonality. While it reproduces pretty well the seasonality of monthly rainfall, it fails to reproduce brutal variations of monthly raining. As a conclusion, predicting rainfall on a daily basis seems to be too hard with a time series model as there is a consequent daily variability plus particular events such as anticyclones. However, this kind of model could help predicting the trend of the volume of precipitations in a couple of months horizon.
