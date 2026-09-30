# 4.1 & 4.2 continued
## Review
**Random variable** $X$ is defined as a function $X: S \to R$, for some $S$ domain and $R$ codomain.

basically all elements in $\mathbb{R}$ are given a number (multiple could map to the same one), then, we can just care about the individual numbers themselves (which represent more abstractly the events from $\mathbb{R}$). 

Probability mass function (pmf) of $X$, all spots at which $X$ equals some $t$. 
$$
\begin{align}
t \in \mathbb{R}, p(t) = P(X = t) = P(\{ w \in S : X(w) = t \})
\end{align}
$$
### Example 1
*A bin has 5 red balls and 7 black balls. You pick 5 balls at random from the bin. Let $X$ be the difference in the number of red & black balls picked. Find the pmf of $X$*.  

$t \in \mathbb{R}, 1 \leq X(t) \leq 5$.

to find pmf must list all outcomes:


Let $r,b$ denote the \# of red/black balls selected for some outcome:
$$
\begin{align}
X(r,b) = ? \\
X(5,0) = 5 \\
X(4,1) = 3 \\
X(3,2) = 1 \\
X(2,3) = 1 \\
X(1,4) = 3 \\
X(0,5) = 5 \\
\end{align}
$$

| $X$ | $P(X)$                                                                                               |
| --- | ---------------------------------------------------------------------------------------------------- |
| 1   | $\frac{\binom{5}{3} * \binom{7}{2}}{\binom{12}{5}} + \frac{\binom{5}{2}\binom{7}{3}}{\binom{12}{5}}$ |
| 3   | $\frac{\binom{5}{4}\binom{7}{1}+\binom{5}{1}\binom{7}{4}}{\binom{12}{5}}$                            |
| 5   | $\frac{\binom{5}{5}+\binom{7}{5}}{\binom{12}{5}}$                                                    |

# 4.?  - Expected value

> [!definition] Expected value of random variable
> Let $X$ be a random variable. $E[X]$ is defined as the expected value of random variable $X$.
> $$
> \begin{align}
> E[X] = \sum_{x: P(x) > 0} x * P(x) 
> \end{align}
> $$

## Example
A class consists of 3 freshmen and 5 sophomores. Youpick 2 students at random from this class. If $X =$ \# of fresmen picked. Find $E[X]$

All in range:

| x   | P(x)                                                |
| --- | --------------------------------------------------- |
| 0   | $\frac{\binom{5}{2}}{\binom{8}{2}}$<br>             |
| 1   | $\frac{\binom{5}{1}\binom{3}{1}}{\binom{8}{2}}$<br> |
| 2   | $\frac{\binom{3}{2}}{\binom{8}{2}}$                 |


