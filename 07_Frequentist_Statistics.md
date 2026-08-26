# The Basics of Statistics*
*Frequentist but you know

## Parameters
A parameter is a value that characterizes the distribution of a random variable in a population. They are the basis of statistical inference in both paradigms and we seek to estimate them.

## Samples
A sample is a subset of a population (the object of study). A sample is typically chosen carefully to maximize its chances of representing the population of study.

## Statistics

Statistics are values calculated from a population. Mean, median, and mode are all statistics.

### Central Limit Theorem

$$\overline{X}_n \sim \mathcal{N}(\mu, \frac{\sigma^2}{n})$$ for sufficiently large $n$.

We have the classic Z-test reliant on the sample variance.

$$
Z_n = \frac{\overline{X} - \mu}{\sigma/\sqrt{n}} \sim \mathcal{N}(0, 1)
$$



## Estimators
Estimators are functions of data. Estimators take in data and give us an estimate for a population parameter. While we most often use the [[#Maximum Likelihood Estimation|maximum likelihood estimator]], there are lots of other estimators.

## Maximum Likelihood Estimation
The maximum likelihood estimate is the estimate of a population parameter that has the highest probability of producing the data that we observe. We find it by maximizing the likelihood function, which is effectively the joint probability of the PMF for the distribution we are sampling from.

## Bias
Bias is the difference between the expected value of an estimator and the actual parameter. Asymptotically, the MLE is unbiased.

## Consistency
Consistency means that an estimator gets more accurate as n increases. However, efficiency is how comparatively accurate an estimator is compared to another estimator of the same parameter.

## Advanced Topics
- [[#Fisher Information]]
- [[#Cramer-Rao Lower Bound]]
- [[#Likelihood Ratio Testing]]

### Fisher Information

### Cramer-Rao Lower Bound

### Likelihood Ratio Testing

## Related Topics
- [[02_Randomness_and_Paradigms]]
- [[08_Bayesian_Statistics]]
- [[10_Hypothesis_Testing]]

#frequentist #statistics #parameters #estimators #mle #bias #consistency