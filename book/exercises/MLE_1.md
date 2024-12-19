# Maximum Likelihood Estimation

Insert image

Welcome to the Maximum Likelihood Estimation module.  At the end of this module, you will be able to calculate the likelihood function for a given probability distribution and use it to find the maximum likelihood estimate of the parameters. Manipulate the distribution parameters to evaluate conditions relevant to Civil Engineering and Geosciences (CEG) applications.

This module is set up with a 3-unit format:

1. The basic theory of a specific concept.
2. Example of how a specific concept is applied to a  CEG problem, through step-by-step explanations and short python code blocks.
3. Introduction of a new problem, to practice using the method from unit 2.

---
## 1. Theory
Maximum Likelihood Estimation (MLE) is a statistical method used to estimate the parameters of a probability distribution based on observed data $\mathbf{x} = x_1, x_2, ..., x_n$. Evaluating the joint density of the data given a parametric family $\theta$ gives the likelihood function, which is a function that measures how well the observed data fits the probability distribution with the given parameters:

$L(\theta \mid \mathbf{x}) = f(\mathbf{x} \mid \theta) = \prod_{i=1}^{n} f(x_i \mid \theta)$ 

The goal of MLE is to find the values of the parameters that maximize the likelihood function. The maximum likelihood estimate $\hat{\theta}$ is the set of parameters for which the observed data is the most probable with the assumed probability distribution:

$\hat{\theta} = \arg \max _{\theta} L(\theta \mid \mathbf{x})$ 

In practice, it is more common to use the log-likelihood, which is the natural logarithm of the likelihood function:

$\ln (L(\theta \mid \mathbf{x})) = \ln (\prod_{i=1}^{n} f(x_i \mid \theta))$ 

To find the maximum likelihood estimate $\hat{\theta}$, the following steps should be taken:

1. Define the likelihood function $L(\theta \mid \mathbf{x})$.
2. Take natural logarithm of the likelihood function to get the log-likelihood function $\ln (L(\theta \mid \mathbf{x}))$.
3. Differentiate the log-likelihood function and set it to zero: $\frac{\partial L(\theta \mid \mathbf{x})}{\partial \theta} = 0$.
4. Solve the equation for $\hat{\theta}$.

Note that the maximum can also occur at the boundary of the domain.

---


## 2. Exponential Distribution

The exponential PDF is given by:

$f_X(x, \lambda) = \lambda e^{-\lambda x}$ for $x>0$

with $\lambda$ being the parameter that has to be estimated. There dataset consists of $n$ observations. Find the maximum likelihood estimate $\hat{\lambda}$ following the four steps defined above:

:::{card}
**1. Define the likelihood function $L(\lambda \mid \mathbf{x})$.**
```{admonition} Solution
:class: tip, dropdown
According to the definition, the likelihood function is given by:

$L(\lambda \mid \mathbf{x}) = \prod_{i=1}^{n} f(x_i \mid \lambda)$

For the exponential distribution, $f(x_i \mid \lambda) = \lambda e^{-\lambda x}$.

Therefore, the likelihood function for the exponential distribution is given by:

$L(\lambda \mid \mathbf{x}) = \prod_{i=1}^{n} \lambda e^{-\lambda x_i} = \lambda^n e^{-\lambda \sum_{i=1}^{n} x_i} = $
```
:::

:::{card}
**2. Take natural logarithm of the likelihood function to get the log-likelihood function $\ln (L(\lambda \mid \mathbf{x}))$.**
```{admonition} Solution
:class: tip, dropdown
Taking the natural logarithm of the likelihood function to obtain the log-likelihood function:

$\ln (L(\theta \mid \mathbf{x})) = \ln (\lambda^n e^{-\lambda \sum_{i=1}^{n} x_i} ) = n \ln (\lambda) -\lambda \sum_{i=1}^{n} x_i $
```
:::

:::{card}
**3. Differentiate the log-likelihood function and set it to zero: $\frac{\partial L(\lambda \mid \mathbf{x})}{\partial \lambda} = 0$**

```{admonition} Solution
:class: tip, dropdown
Taking the derivative of the log-likelihood function with respect to $\lambda$ and setting it to zero:

$\frac{\partial \ln (L(\lambda \mid \mathbf{x}))}{\partial \lambda} = \frac{\partial (n \ln (\lambda) -\lambda \sum_{i=1}^{n} x_i )}{\partial \lambda} = \frac{n}{\hat \lambda} - \sum_{i=1}^{n} x_i = 0$
```
:::

:::{card}
**4. Solve the equation for $\hat{\lambda}$.**
```{admonition} Solution
:class: tip, dropdown
We have the following equation to solve:

$\frac{n}{\hat \lambda} - \sum_{i=1}^{n} x_i = 0$

which results in the maximum likelihood estimate:

$\hat \lambda = \frac{n}{\sum_{i=1}^{n} x_i} = \frac{1}{\bar x}$

where $\bar x = \frac{\sum_{i=1}^{n} x_i}{n}$ is the sample mean of the obsrved data.

This means that the maximum likelihood estimate of the exponential distribution is the inverse of the sample mean.
```
:::


---

## 3. Example of MLE of Exponential Distribution 

The following dataset describes the time elapsed between consecutive arrivals of passengers at a bus stop (in minutes):

$\mathbf{x} = [1.2, 0.5, 3.7, 2.3, 0.9, 1.5, 2.1, 3.0, 1.8, 2.5]$

Assume that the observations can be described by the exponential distribution, for which the PDF is given by:

$f_X(x, \lambda) = \lambda e^{-\lambda x}$ for $x>0$

with $\lambda$ being the parameter that has to be estimated. Find the maximum likelihood estimate $\hat{\lambda}$ following the four steps defined above:

1. Define the likelihood function $L(\lambda \mid \mathbf{x})$.
2. Take natural logarithm of the likelihood function to get the log-likelihood function $\ln (L(\lambda \mid \mathbf{x}))$.
3. Differentiate the log-likelihood function and set it to zero: $\frac{\partial L(\lambda \mid \mathbf{x})}{\partial \lambda} = 0$.
4. Solve the equation for $\hat{\lambda}$.