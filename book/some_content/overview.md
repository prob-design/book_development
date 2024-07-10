# Probabilistic Design Lecture Notes P.54


An algebraic expression for the copula distribution function, $C(u,v)$ joining two marginal distributions,$F_{X}(x)$ and $F_{Y}(y)$ could be obtained also from the joint probability density function,$H_{X,Y}(x,y)$ if this one is known. The relationship is given by:
##### 2.159
$$
    C(u,v) = H(F^{-1}(u),G^{-1}(v))
$$




In which $u,v \in [0 \ 1]$ and and $F^{-1}$ and $G^{-1}$ are the inverses of $F$ and $G$, which are the marginal cumulative distribution functions. When the joint cumulative probability distribution function is given by $H_{X,Y}(x,y)$, the marginal distribution functions can be retrieved as:

$$
    F_{X}(x) = \lim_{x\to sup(Y)}{H_{X,Y}(x,y)}
$$ (label1)

$$
    G_{Y}(y) = \lim_{x\to sup(X)}{H_{X,Y}(x,y)}
$$ (label2)

Where $sup(X)$ is the supremum of $X$, which on a closed interval is equal to $max(X)$ and on an open interval is equal to the upper interval boundary, or if there is no boundary, $sup(X) = \infty $. To clarify the procedure, an example will be given.


:::{card} Example 2.25 

Consider two random variables $X$ and $Y$ with a joint probability density function given by:

$$
    h_{X,Y}(x,y)=\frac{4}{5a \cdot b} \left(\frac{x}{a}+\frac{y}{b}+\frac{xy}{a \cdot b } \right)
$$

with $0 \leq x \leq a$ and $0 \leq y \leq b$. First the cumulative function needs to be found.


$$
\begin{align*}
    H_{X,Y}(x,y) & = \int_{0}^{a} \int_{0}^{b} h_{X,Y}(x,y)dxdy\\
    &= \int_{0}^{a} \int_{0}^{b} \frac{4}{5a \cdot b} \left(\frac{x}{a}+\frac{y}{b}+\frac{xy}{a \cdot b } \right) dxdy\\
    &= \frac{4}{5a\cdot b} \int_{0}^{a} \left[\frac{x}{a}+\frac{y}{b}+\frac{xy}{a \cdot b } \right]_{0}^{b}\\
    &= \frac{4}{5a\cdot b} \left[\frac{x^2}{2a}+\frac{xy}{b}+\frac{x^2y}{2a \cdot b } \right]_{0}^{a}\\
    &= \frac{4}{5a\cdot b}xy \left(\frac{x}{2a}+\frac{y}{2b}+\frac{xy}{4a \cdot b } \right)\\
\end{align*}
$$ (label33)

Multiplied with $\cdot \frac{ab}{ab}$, it becomes:
$$
\begin{align*}
    H_{X,Y}(x,y) & = \frac{xy}{5a^2\cdot b^2} \left(2a\cdot y + 2b \cdot x + x \cdot y \right)
\end{align*}
$$ (label34)

Then the marginal distribution functions can be found by obtaining limits of equation \eqref{label33}


:::
