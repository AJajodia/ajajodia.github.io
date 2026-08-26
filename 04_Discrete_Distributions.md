# Discrete Random Variables
## Probability Mass Function
$$f(x)_X = P(X=x), \quad x \in \mathbb{N} $$
If a random variable can be mapped to the nonnegative integers, it's discrete. The probability mass function assigns probabilities to the support, or possible values of the RV.
## Some Common Discrete Distributions

| Distribution | Parameters                                                                                       | PMF                                                                                                | Description                                                                                   |
| ------------ | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Bernoulli    | $p$: likelihood of a result                                                                      | $$\cases{p \quad \text{for $x$ = 1} \\ 1 - p \quad \text{for x = 0} \\ 0 \quad \text{otherwise}}$$ | Single event with binary possibilities                                                        |
| Uniform      | $a, b$: the upper and lower bounds of the uniform distribution<br>$n$: $b - a + 1$               | $$\frac{1}{n}$$                                                                                    | Equally likely values                                                                         |
| Binomial     | $n$: the number of trials<br>$p$: the probability of success for an individual trial (Bernoulli) | $$\binom{n}{x}p^x(1-p)^{n-x}$$                                                                     | $n$ trials with $x$ outcomes, each Bernoulli distributed with $p$                             |
| Poisson      | $\lambda$: the expected number of events in an interval                                          | $$P(X = x) = \frac{\lambda^xe^{-\lambda}}{x!}$$                                                    | Likelihood of $x$ events happening in an interval when $\lambda$ is the mean number of events |
| Exponential  | $\lambda$                                                                                        | $$P(X = x) = \lambda e^{-\lambda x}$$                                                              |                                                                                               |


## Related Topics
- [[03_Random_Variables]]
- [[05_Continuous_Distributions]]
- [[07_Frequentist_Statistics]]

#discrete #distributions #probability-mass-function #bernoulli #binomial #exponential