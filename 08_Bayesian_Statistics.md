# The Basics of Bayesian Statistics
The good stuff

$$p(\pi | y) = \frac{p(X | \pi) p(\pi)}{p(X)}$$

## Back to Bayes' Rule

### The Prior
The distribution of our parameter before observing data is called a prior.

### The Likelihood
The likelihood function describes the probability of observing a certain result given the value of the parameter.

### The Posterior
After updating our prior based on the likelihood, we obtain the posterior, which is the distribution of our parameter given a prior and data.

### The Normalizing Constant
This is the key part of calculating the posterior. In order to be a proper probability distribution, the total probability of the outcomes in the support of the posterior must add to 1. This is often difficult to calculate, since it requires our ability to integrate over the posterior.

## Conjugate Families
These are families in which the distribution of the posterior is the same shape as the distribution of the prior.

### Normal-Normal Conjugacy
$$\mu \sim \mathcal{N}(\theta, \tau^2)$$
$$Y_i | \mu \sim \mathcal{N}(\mu, \sigma^2)$$

$$\mu|\vec y \sim \mathcal{N}(\theta \frac{\sigma^2}{n \tau^2 + \sigma^2} + \bar y \frac{n\tau^2}{n\tau^2 + \sigma^2}, \frac{\tau^2 \sigma^2}{n\tau^2 + \sigma^2})$$

## Choosing a Prior
It's mostly intuition. However, maybe we want to make the problem easier by choosing a conjugate prior. Maybe we don't have a good sense of the prior's distribution, so we want a distribution that doesn't make a bold claim about the u


## Hypothesis Testing
## The posterior probability 

## Bayes Factor

## Credible Intervals



## What if the prior isn't conjugate?

### Grid Approximation

### Markov Chain Monte Carlo

In Markov chain Monte Carlo (MCMC), we sample values from the posterior distribution by generating candidate points and only going to the ones that are most likely. There are a number of sampling algorithms.

![[Pasted image 20260519104116.png]]

#### Metropolis-Hastings Algorithm
1) Choose a candidate point via a proposal model with the following PDF:
$$q(\mu', \mu)$$
2) Evaluate the following function:
$$\alpha = \min\Biggl\{1, \frac{f(\mu')L(\mu'|y)}{f(\mu)L(\mu|y)} \frac{q(\mu|\mu')}{q(\mu'
|\mu)}\Biggl\}$$
3) Go to the next point with probability $\alpha$
## Related Topics
- [[02_Randomness_and_Paradigms]]
- [[07_Frequentist_Statistics]]
- [[01_Probability_Basics]]

#bayesian #statistics #bayes-rule #prior #likelihood #posterior #conjugate #normalizing-constant