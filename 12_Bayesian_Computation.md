# Markov Chain Monte Carlo

In Markov chain Monte Carlo (MCMC), we sample values from the posterior distribution by generating candidate points and only going to the ones that are most likely. There are a number of sampling algorithms.

![[Pasted image 20260519104116.png]]

## Metropolis-Hastings Algorithm
1) Choose a candidate point via a proposal model with the following PDF:
$$q(\mu', \mu)$$
2) Evaluate the following function:
$$\alpha = \min\Biggl\{1, \frac{f(\mu')L(\mu'|y)}{f(\mu)L(\mu|y)} \frac{q(\mu|\mu')}{q(\mu'
|\mu)}\Biggl\}$$
3) Go to the next point with probability $\alpha$

## Gibbs Sampling

# Variational Inference (Variational Bayes)



## Evidence Lower Bound

