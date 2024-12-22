# Maximum Likelihood Estimation 2

Insert imgage

Welcome to the Maximum Likelihood Estimation 2 module.  At the end of this module, you will be able to calculate the likelihood function for a given probability distribution and use it to find the maximum likelihood estimate of the parameters. Manipulate the distribution parameters to evaluate conditions relevant to Civil Engineering and Geosciences (CEG) applications.

This module is set up with a 3-unit format:

1. The basic theory of a specific concept.
2. Example of how a specific concept is applied to a  CEG problem, through step-by-step explanations and short python code blocks.
3. Introduction of a new problem, to practice using the method from unit 2.

---
## 1. Theory

Refer to module MLE 1 for the summary of the relevant theory.

Recap of steps to follow when finding the maximum likelihood estimate:

1. Define the likelihood function $L(\theta \mid \mathbf{x})$.
2. Take natural logarithm of the likelihood function to get the log-likelihood function $\ln (L(\theta \mid \mathbf{x}))$.
3. Differentiate the log-likelihood function and set it to zero: $\frac{\partial L(\theta \mid \mathbf{x})}{\partial \theta} = 0$.
4. Solve the equation for $\hat{\theta}$.

---


## 2. Wave heights


Insert image? Exercise is from the prob design exam January 2019.    

A group of coastal and offshore engineers is interested in modelling wave heights. They decide to investigate the water level Z as the sum of two random variables:

a) X: Significant wave height in m and \
b) Y: Storm surge also in m

As an initial model, they decide that both X and Y are independent and identically distributed. In fact they model them as exponentially distributed with parameter $\theta$. That is $f_X(x)=\theta e^{-\theta x}$ and $f_Y(y)=\theta e^{-\theta y}$.

:::{card}
**1. Show with clear calculations that $f_Z(z)=\theta^2 z e^{-\theta z}$.**
```{admonition} Solution
:class: tip, dropdown
We know that X and Y are independent, and $Z = X + Y$, so we can write $f_X(x) = f_X(z-y)$ and $$f_Z(z)=\left(f_X \otimes\right. \left.f_Y\right)(z) =\int_{-\infty}^{+\infty} f_X(z-y) f_Y(y) d y=\int_0^z\left(\theta e^{-\theta(z-y)}\right)\left(\theta e^{-\theta(y)}\right) d y 
 =\theta^2 \int_0^z e^{-\theta(z-y)-\theta y} d y=\theta^2 \int_0^z e^{-\theta z} d y=\theta^2 z e^{-\theta z}$$
```
:::

:::{card}
**2. Show with clear calculations an expression for $\hat{\theta}$, the Maximum Likelihood Estimator of $\theta$ based on $f_Z(z)$.**

```{admonition} Solution
:class: tip, dropdown
The likelihood function can be written as: $$L\left(z_1, z_2 \ldots z_n ; \theta\right)=\prod_{i=1}^n f_Z\left(z_i ; \theta\right)=\theta^{2 n} \exp \left(\sum_{i=1}^n-\theta z_i\right) \prod_{i=1}^n z_i$$

Taking natural logarithm of the likelihood function, the log-likelihood is: $$\ln \left(L\left(z_1, z_2 \ldots z_n ; \theta\right)\right)=2 n \ln (\theta)+-\theta \sum_{i=1}^n z_i+\ln \left(\prod_{i=1}^n z_i\right) $$

Setting the derivative of the log-likelihood function equal to zero: $$\frac{d\left(\ln \left(L\left(x_1, x_2 \ldots x_n ; \theta\right)\right)\right)}{d \theta}=\frac{2 n}{\theta}-\sum_{i=1}^n z_i=0$$

Solving for the maximum likelihood estimate $\hat{\theta}$, we obtain $\hat{\theta} = \frac{2n}{\sum_{i=1}^n z_i}$.
```
---
:::
## 3. Buckling of Steel Columns

A structural steel manufacturer company carried out an inspection on the steel beams it's producing. Out of the 100 selected samples, 9 did not meet the buckling requirements.

Assuming that the dataset can be described by the binomial distribution with unknown parameter $\theta$, the PMF is given by:

$p_x(x,\theta)={n \choose x} \theta^x (1 - \theta)^{n-x}$

In this exercise, you can test your understanding of the maximum likelihood estimation of the probability of a flawed observation based on the given data.

1. Is $L(\theta) = \theta^x (1 - \theta)^{n-x}$ a correct likelihood function? T/F \
Could be a fun fact to add that ${n \choose x}$ doesnt depend on $\theta$ so can be omitted.

2. What is the maximum likelihood estimate of the probability of a flawed observation based on the given data? \
0.09, same as x/n wow cool