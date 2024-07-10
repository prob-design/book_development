# Probabilistic Design Lecture Notes

## Probability Calculus

### Correlation Influence on Workability at Sea

Given the probabilities:

\[
P((X > 0.705) \cap (X > 0.702)) = 1 - P(X \leq 0.705) - P(X \leq 0.702) + P((X \leq 0.705) \cap (X \leq 0.702)) = 0.629
\]

The correlation between two weather states positively influences the workability at sea, since the probability of occurrence of weather conditions that fall within the acceptable range for a mission to take place has increased from 0.495 to 0.629.

### Copula Distribution Function

The algebraic expression for the copula distribution function can be represented as:

\[
C(u,v) = H(F^{-1}(u), G^{-1}(v))
\]

Where \( u, v \in [0,1] \) and \( F^{-1}, G^{-1} \) are the inverses of the marginal cumulative distribution functions \( F \) and \( G \).

### Example 2.25: Joint Probability Density

Consider two random variables \( X \) and \( Y \) with a joint probability density function given by:

\[
h(x, y) = \frac{x + y}{ab}
\]

Where \( 0 \leq x \leq a \) and \( 0 \leq y \leq b \). The cumulative distribution function is:

\[
H(x, y) = \int_0^x \int_0^y f(x', y') \, dx' \, dy'
\]

### Marginal Distribution Functions

The marginal distribution functions can be obtained from the cumulative distribution function \( H(x, y) \):

\[
F(x) = \lim_{y \to \text{sup}(Y)} H(x, y)
\]
\[
G(y) = \lim_{x \to \text{sup}(X)} H(x, y)
\]
