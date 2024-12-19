# Independence and Conditioning

Insert image

Welcome to the Independence and Conditioning module.  At the end of this module, you will be able to evaluate probabilities for events for a given (joint) probability distribution using knowledge on independence and conditioning. Manipulate the distribution parameters to evaluate conditions relevant to Civil Engineering and Geosciences (CEG) applications.

This module is set up with a 3-unit format:

1. The basic theory of a specific concept.
2. Example of how a specific concept is applied to a  CEG problem, through step-by-step explanations and short python code blocks.
3. Introduction of a new problem, to practice using the method from unit 2.

---
## 1. Theory

Independence:

$F(x, y) = P(x<X \bigcap y<Y ) = P(x<X)P(y<Y) = F(x)F(y)$

Conditioning:

$P(x<X \vert y<Y) = \frac {P(x<X \bigcap y<Y )}{P(y<Y)} = \frac{F(x, y)}{F(y)}$

$ F(x, y) = F(x \vert y)F(y) = F(y \vert x)F(x) $

---


## 2. Lab stuff

:::{card} Exercise: Measurements
Exercise is from prob design exam April 2019

$X$ and $Y$ are two (unitless) quantities that have been measured in the lab in order to investigate certain properties. Theoretical cumulative distribution functions for $X$ and $Y$ have been fitted satisfactorily to data obrained after many years of measurements. These are given by $F$ and $G$ below:

$F(x) =\left\{\begin{matrix}
        0 & \, x < -1 \\
        \frac{x+1}{2} & \, -1 \leq x \leq 1 \\
        1 & \, x >1
    \end{matrix}\right.$

$G(y) =\left\{\begin{matrix}
        0 & \, y < 0 \\
        1-e^{-y} & \, y \geq 0 
    \end{matrix}\right.$

Assume $X$ and $Y$ are independent.

1. What is $P(X \leq -0.1, Y \leq 1)$?
2. What is $P(X > 0.8 \vert Y >10)$?

As it turns out, the joint cumulative distribution function of $X$ and $Y$ (denoted as $H$) has also been approximated from measurements with sufficient accuracy and is given

$H(x, y) =\left\{\begin{matrix}
\frac{(x+1)(e^y-1)}{x+2e^y-1} & \, (x,y)\in [-1, 1] \times [0,\infty] \\
1-e^{-y} & \, (x,y)\in (1, \infty] \times [0,\infty] \\
0 & \, \mathrm{elsewhere}
\end{matrix}\right. $ 


3. What is $P(X \geq 0.8, Y \geq 4.6)$ in the case the joint distribution is as above?
4. What is $P(X \geq 0.8 \vert Y \geq 4.6)$ in the case the joint distribution is as above?

```{admonition} Solution
:class: tip, dropdown

**1. What is $P(X \leq -0.1, Y \leq 1)$?**

Since we assume that $X$ and $Y$ are independent, we have to solve $P(x<X \bigcap y<Y ) = P(x<X)P(y<Y) = F(x)G(y)$.

Substituting the values into this equation, we have:

$F(-0.1)G(1) = \frac{-0.1+1}{2} (1-e^{-1}) = 0.28$

**2. What is $P(X > 0.8 \vert Y >10)$?**

We know that $P(X>x \vert Y>y) = \frac {P(X>x \bigcap Y>y )}{P(Y>y)}$, and with the assumption of $X$ and $Y$ being independent, $P(X>x \bigcap Y>y ) = P(X>x)P(Y>y)$. 

Therefore, $P(X>x \vert Y>y) = \frac {P(X>x)P(Y>y)}{P(Y>y)} = P(X>x)$. 

$P(X>0.8 \vert Y>10) = P(X>0.8) = 1-F(0.8) = 1 - \frac{0.8+1}{2} = 0.1$

We can see that the probability of $X>x$ does not depend on the value of $Y$, since these variables are independent. Now let's see what happens when the variables are no longer independent!

**3. What is $P(X>0.8, Y>4.6)$ in the case the joint distribtution is as above?**

insert pic?

Looking at the solution space, we can rewrite the equation in the following way:

$P(X>x \bigcap Y>y) = 1 - (P(X \leq x) + P(Y \leq y) - P(X \leq x \bigcap Y \leq y)$

Now $X$ and $Y$ are not independent anymore, the joint distribution $P(X \leq x \bigcap Y \leq y)$ is given by $H(x,y)$. The equation then becomes:

$P(X>0.8 \bigcap Y>4.6) = 1 - (F(0.8) + G(4.6) - H(0.8,4.6)) = 1 - (\frac{0.8+1}{2} + 1-e^{-4.6} - \frac{(0.8+1)(e^{4.6}-1)}{0.8+2e^{4.6}-1}) = 0.0019$

**4. What is $P(X>0.8 \vert Y>4.6)$ in the case the joint distribtution is as above?**

Just as in Question 2, $P(X>x \vert Y>y) = \frac {P(X>x \bigcap Y>y )}{P(Y>y)}$, so we have the following problem to solve:

$P(X>0.8 \vert Y>4.6) = \frac {P(X>0.8 \bigcap Y>4.6 )}{P(Y>4.6)} = \frac {P(X>0.8 \bigcap Y>4.6 )}{1-P(Y \leq 4.6)}$.

We know from Question 3 that $P(X>0.8 \bigcap Y>4.6) = 0.0019$, so the equation becomes:

$P(X>0.8 \vert Y>4.6) = \frac{0.0019}{1-0.9899} = 0.1931$

Notice how the probability of $X>0.8$ increased when the variables $X$ and $Y$ are made dependent on each other. This will be important when correlation is discussed in later sections.
```
:::

## 3. 

can this be discrete? eg Q3 Jan 2019