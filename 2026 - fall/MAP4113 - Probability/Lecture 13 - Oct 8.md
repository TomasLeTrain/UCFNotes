# 4.5 - Variance
> [!definition] Variance
> **Variance** is the mean square of the deviation from the mean:
> $$
> \begin{align}
> E[(X - \mu)^{2}] = E[X^{2}] - (E[X])^{2}
> \end{align}
> $$
> Since it is squared it is guaranteed to **always** be positive.

## Example 5a
Find $\text{Var}(x)$ if $x$ represents the outcome when a fair dice is rolled.

$$
\begin{align}
p(x) = \frac{1}{6} \\
E[X] = \mu = \frac{1}{6}1 + \frac{1}{6}2 + \dots + \frac{1}{6} 6 \\
= \frac{1+2+3+4+5+6}{6} = \boxed{ \frac{21}{6} }
E[X^{2}] = \frac{1}{6}1 + \frac{1}{6} 2^{2} + \dots + \frac{1}{6} 6^{2} \\
= \frac{1+2^{2}+3^{2}+4^{2}+5^{2}+6^{2}}{6} \\
\boxed{ = \frac{91}{6} }
\end{align}
$$
So
$$
\begin{align}
E[(X-\mu)^{2}] = E[X^{2}] - E[X]^{2} \\
E[(X-\mu)^{2}] = \frac{91}{6} - \frac{21}{6} = \boxed{ \frac{70}{6} }
\end{align}
$$

## Example 5c
Suppose there are $m$ days in a year, and that each person is independently born on day $r$ with probability $p_{r},r = 1 , \dots , m, \sum_{r=1}^{m}p_{r}=1$. Let $A_{i,j}$ be the event that persons $i$ and $j$ are born on the same day.
a. Find $P(A_{1,3})$
b. Find $P(A_{1,3} | A_{1,2})$
c. Show $P(A_{1,3} | A_{1,2}) \geq P(A_{1,3})$

$$
\begin{align}
P(A_{i,j}) = p_{1}^{2} + p_{2}^{2} + \dots + p_{m}^{2} \\ \\ \\
P(A_{1,3}) = \dots
\end{align}
$$
For $B$, intuitively it should be independent. However, knowing that $A_{1,2}$ happened implies more heavily that, for example, both were born on a common day to be born in. Since the likelyhood of $1$ being born on a  common day increases, the probability of $A_{1,3}$ also increases!

$$
\begin{align}
P(A_{1,3} | A_{1,2}) = \frac{P(A_{1,3} \cap A_{1,2})}{P(A_{1,2})} = \frac{P(A_{1,2,3})}{P(A_{1,2})}
= \boxed{ \frac{\sum_{r=1}^{m} p_{r}^{3}}{\sum_{r=1}^{m} p_{r}^{2}} }
\end{align}
$$
So for c, we must show that
$$
\begin{align}
\frac{\sum_{r=1}^{m} p_{r}^{3}}{\sum_{r=1}^{m} p_{r}^{2}} \geq \sum_{r=1}^{m} p_{r}^{2}  \\ \\
\sum_{r=1}^{m} p_{r}^{3} \geq \left(\sum_{r=1}^{m} p_{r}^{2}\right)^{2} 
\end{align}
$$

Consider the random variable $X = p_{r}$, then by consequence 
$$
\begin{align}
E[X] = \sum_{r=1}^{m}  \underbrace{ P(x=p_{r}) }_{ p_{r} } * p_{r} = \sum_{r=1}^{m}  p_{r}^{2} \\
 \\
E[X^{2}] = \sum_{r=1}^{m} \underbrace{ P(x = p_{r}) }_{ p_{r} } * (p_{r})^{2} = \boxed{ \sum_{r=1}^{m} p_{r}^{3} }
\end{align}
$$

We can therefore figure out the variance:
$$
\begin{align}
0 \leq E[X - \mu] = E[X^{2}] - E[X]^{2} \\
0 \leq \sum_{r=1}^{m} p_{r}^{3}  - \left(   \sum_{r=1}^{m} p_{r}^{2}\right)^{2} \\
\left(   \sum_{r=1}^{m} p_{r}^{2}\right)^{2} \leq \sum_{r=1}^{m} p_{r}^{3}   \\
\boxed{ \sum_{r=1}^{m} p_{r}^{2} \leq \frac{\sum_{r=1}^{m} p_{r}^{3}}{\sum_{r=1}^{m} p_{r}^{2}}  } \\
\boxed{ P(A_{1,3}) \leq P(A_{1,3} | A_{1,2})  }
\end{align}
$$

# 4.6