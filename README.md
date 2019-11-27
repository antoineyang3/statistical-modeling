# statistical-modeling

This repository groups two small projects I have worked on in statistical modeling:
- The first one (notebook quantile_estimation.ipynb) is about statistics of extreme. The problem here is to estimate events that rarely happen so that we have very few observed data about such events. We get into the skin of a careful shareholder in Apple and want to estimate the probability that Apple's quotation decreases of more than X% in one day. 

Using the Hill estimator, we estimate the parameter of the Frechet Law that approximates the distribution of negative relative variations of Apple's quotation given a tunable threshold. Then we verify that relatively high empiric quantiles are reasonably close to Hill estimated quantiles. Finally, we use the estimator to give meaningful interpretations : less than 0.5% of negative relative variations of Apple's quotation exceed 8.83%.

Using Pick over Threshold method, we estimate the survival function of the distribution of negative relative variations of Apple's quotation above a tunable threshold. Using maximum likelihood, we estimate numerically the parameters of the general Pareto distribution that models the exceedences. We verify that the tail-parameter is close to the one we obtained using Hill estimator, and that the estimated survival function is close to the empirical survival function. Finally, we use the estimated survival function to provide meaningful interpretations : 4.7% of the negative relative variations of Apple's share are above 5.06%.
