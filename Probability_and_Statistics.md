---
title: "Probability and Statistics"
public: true
published: true
---

# Probability and Statistics

## Table of Contents

1. [The Basics of Probability](#the-basics-of-probability)
2. [Randomness and Paradigms](#randomness-and-paradigms)
3. [Random Variables](#random-variables)
4. [Discrete Distributions](#discrete-distributions)
5. [Continuous Distributions](#continuous-distributions)
6. [Information Theory](#information-theory)
7. [Frequentist Statistics](#frequentist-statistics)
8. [Bayesian Statistics](#bayesian-statistics)
9. [Data Visualization](#data-visualization)
10. [Hypothesis Testing](#hypothesis-testing)
11. [Machine Learning Basics](#machine-learning-basics)
12. [Bayesian Computation](#bayesian-computation)

> "Probability is the most important concept in modern science, especially as nobody has the slightest notion what it means." —Bertrand Russell, 1929 Lecture

---

# The Basics of Probability
From my perspective

## What is Probability?

> "Probability is the most important concept in modern science, especially as nobody has the slightest notion what it means." —Bertrand Russell, 1929 Lecture (cited in Bell 1945, 587)

**![](/assets/image_1.png)****![](/assets/image_2.png)**

• I don't really know
• Probably (ha) made up
• It is useful though!
• [[02_Randomness_and_Paradigms|Randomness]] is everywhere and thus is useful in modeling the world
• Lots of paradigms of probability

## Basic Rules of Probability (regardless of paradigm)
##### Bayes' Rule
$$
P(A|B) = \frac{P(B|A)P(A)}{P(B)} = \frac{P(A\cap B)}{P(B)}
$$

##### Union of Events
$$
P(A \cup B) = P(A) + P(B) - P(A\cap B)
$$
##### Complement of Events
$$
P(A^c) = 1-P(A)
$$

## Related Topics
- [[02_Randomness_and_Paradigms]]
- [[03_Random_Variables]]
- [[07_Frequentist_Statistics]]
- [[08_Bayesian_Statistics]]

#probability #basics #foundations

## Randomness

Its when we don't know what's going to happen (but we might have ideas about how what its shape is)

For example, we expect that coins will land on their heads and tails equally likely, even though we don't know what the actual value of the flip will be beforehand

There are different paradigms in how these shapes are explained

Note: Coin flips in reality are not 50-50, it's more likely that the coin will land on the same side and you could predict what side it would land on if you knew everything about the coin

*https://www.stat.berkeley.edu/~stark/SticiGui/Text/probabilityPhilosophy.htm

## Paradigms of Probability

### Equally Likely Outcomes

**![](/assets/image_3.png)**
Probability is shared between equally likely events, we get to calculate probability by adding up all of the ways that a certain outcome could happen and divide by the number of outcomes (Laplace's Principle of Insufficient Reason)

Ex. coin flips have two equally likely outcomes, ½ = 0.5

This is pretty clearly a bad way to do things, but it works to some extent

Championed by people like Laplace, Bernoulli and Pascal

### Kolmogordov's Probability Calculus
1) (Non-negativity)
$$
P(A) \geq 0 \text{ for all } A \in \mathbb{F}
$$
2) (Normalization)
$$
P(\Omega) = 1
$$
3) (Finite Additivity
$$
P(A \cup B) = P(A) + P(B) \text{ for all } A, B \in \mathbb{F} \text{ such that } A\cup B = \emptyset
$$

Pretty much a good way to think about probability and applies to a lot of the interpretations of probability that we use today. F is a field on Ω, which means its a bunch of nonempty subsets basically and Ω is like everything thats possible

### Frequentism
$$
\lim_{n \rightarrow \infty} \frac{n_0}{n} =  p
$$
Probability is the proportion of observing a given outcome if you repeat the event infinitely

Where $n_0$ is the number of times we observe A, the event we are trying to determine the probability of

### Subjectivism (Bayesianism)

Bayesians think of probability as something that measures the degree of belief that an event will happen. Bayesians make a "best guess" called a [[08_Bayesian_Statistics#The Prior|prior]] and then update it with data according to [[08_Bayesian_Statistics|Bayes' Rule]]

$$
P(\pi|X) = \frac{L(\pi|X)P(\pi)}{P(X)}
$$
$L$, the likelihood, finds the probability of observing the given data based on the value of some parameter, a [[03_Random_Variables#Random Variables|random variable]]

The denominator is often called the normalizing constant. In order to find this, we can integrate the numerator and determine the dividing factor that gives us an area of 1. Finding a closed-form solution for this value is one of the big drawbacks of traditional Bayes and why it had limited popularity for so long. However, notice that:
$$
P(\pi|X) \propto \frac{L(\pi|X)P(\pi)}{P(X)}
$$
## Counting

|                         | **Ordered**                                                                          | **Unordered**                                                       |
| ----------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| **With Replacement**    | $$n^k$$<br>Ex. honestly no idea                                                      | $$\binom{n + k - 1}{k}$$<br>Ex. password length k, n characters<br> |
| **Without Replacement** | $$\binom{n}{k} = \frac{n!}{(n-k)!k!}$$<br>Ex. choosing k from n people for a job<br> | $$\frac{n!}{(n-k)!}$$<br>Ex. choose lines of k people from n people |

#randomness #probability-paradigms #counting #laplace #kolmogorov #frequentism #bayesian
Most of the time we think of the events that might happen as variables. Random variables. This is how things start to get complicated. Random variables model the numbers that appear in all sorts of data. In stats usually they're real numbers ([[05_Continuous_Distributions|continuous]]) or more specifically integers greater than or equal to 0 ([[04_Discrete_Distributions|discrete]]). We can convert them to probabilities with logical operators as follows:

This is the cumulative density function of the random variable, which gives us a probability of observing a result less than the value of $x$ given. This is instantiated differently between real and continuous random variables.
$$F_X(x) = P(X \leq x)$$
Random variables come from measure theory, but I'm not sure how!
## See Also
- [[04_Discrete_Distributions]]
- [[05_Continuous_Distributions]]
- [[01_Probability_Basics]]

#random-variables #statistics #probability
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

$$f(x)_X = P(X=x), \quad x \in \mathbb{R} $$
Continuous random variables can be any real number (sometimes restricted to a range). They are defined by probability density functions (analogous to the discrete case, which we can integrate to find the cumulative density functions describing the probability of ranges

## The Normal Distribution

## Related Topics
- [[03_Random_Variables]]
- [[04_Discrete_Distributions]]
- [[07_Frequentist_Statistics]]

#continuous #distributions #probability-density-function #normal-distribution

![Shannon's entropy diagram](attachments/information_theory_page16.png)

Shannon's Entropy measures the element of surprise for a probability distribution! It is defined as the sum of p ln p over the support of a distribution.

## Related Topics
- [[01_Probability_Basics]]
- [[03_Random_Variables]]

#information-theory #entropy #shannon
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

The art of choosing a way to represent your data. Often observing patterns in data is how we end up forming tests in statistics.

## Types of Plots
Bar chart, line plot, box and whisker, histogram, heatmap, scatter plot, network diagram, pie chart (yuck), barcode plot, violin plot, ridge plot, kernel density estimate (KDE) plot

## Related Topics
- [[07_Frequentist_Statistics]]
- [[10_Hypothesis_Testing]]

#data-visualization #plots #statistics #charts

Specify a null (the assumed distribution of the data prior to this experiment) and alternative hypothesis (what are we testing?). Typically, this takes the form H0: some parameter is equal to some value and HA: some parameter is NOT equal to some value. We then observe some data and based on the result, either reject or do not reject the null. (we do not accept the alternative hypothesis nor do we accept the null).

## P-value
A p-value (in frequentist statistics) is the key part of hypothesis testing. It is the likelihood that under our null we obtain a result which is the same as or more extreme than the observed value. We choose a cutoff called an alpha to determine whether this result is "statistically significant" but in practice this is pretty arbitrarily determined and is often set a 0.05.

## Related Topics
- [[07_Frequentist_Statistics]]
- [[09_Data_Visualization]]

#hypothesis-testing #p-value #null-hypothesis #alternative-hypothesis #significance
Adapted from sean perry

## The Basics of Deep Learning

## Additional topics in computation

## miscellaneous

## Related Topics
- [[07_Frequentist_Statistics]]
- [[08_Bayesian_Statistics]]

#machine-learning #deep-learning #computation

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

