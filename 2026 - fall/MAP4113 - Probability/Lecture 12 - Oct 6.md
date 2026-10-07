# 4.? continued

> [!definition] Expected value
> given a random variable $X$ that occurs with probability $p(x), x \in X$, the **expected value** of $X$ is defined as
> $$
> \begin{align}
> E[X] = \sum_{x \in \mathbb{R} : p(x) > 0} x\ p(x) = \sum_{\underbrace{ x }_{ \text{x in range of X} } : p(x) > 0} x\ p(x) 
> \end{align}
> $$

An **indicator random variable** is a random variable that effectively calculates the probability that some event $A$ happens, in other words, $E[I] = P(A)$, if $I$ is an indicator $A$.


# 4.4 - Expectation of a function of a random variable
Say $Y = X^{3}$, then $E[Y] = E[X^{3}]$, and its expected value can be found as
$$
\begin{align}
Y = f(X) \to E[Y] =  \sum f(x)P(x)
\end{align}
$$
*Remark:* if the function sends multiple $x \in X$ to the same value $y \in Y$, it still holds! Consider $g(x_{i}) = g(x_{j}) = y$, then, $g(x_{i})P(x_{i}) + g(x_{j})P(x_{j}) = g(y)(P(x_{i}) + P(x_{j}))$ , and since $P(y) = P(x_{i}) + P(x_{j})$, $g(x_{i})P(x_{i}) + g(x_{j})P(x_{j}) = y P(y)$, so the original sum will still result in the expected value!

## Problem 4.32
$X$ is \# tests neccesary, for each group
So $X = \{ 1,11 \}$

$$
\begin{align}
P(1) = 0.9^{10}, P(11) = 1 - 0.9^{10} \\
1 * P(1) + 11 * P(11)= 0.9^{10} + 11 * (1 - 0.9^{10}) \\ \\
= 0.9^{10} + 11 - 11*0.9^{10} = 11 + 0.9^{10}(1 - 11)=  \boxed{ 11 - 10 * 0.9^{10} }
\end{align}
$$

There is a case where $E[g(x)] = g(E[X])$, which is when $g(x)$ is a linear function. Consider $g(x) = ax + b$, then expanding out the expected result becomes $a E[X] + b$. Basically, since calculating the expected value is done using linear operations, a linear function will be able to be abstracted and simplified.


## problem 4.1
*Two balls are chosen randomly from an urn containing 8 white, 4 black, and 2 orange balls. Suppose that we win $2 for each black ball selected and we lose $1 for each white ball selected. Let X denote our winnings. What are the possible values of X, and what are the probabilities associated with each value?*

bw -> +2 - 1 = 1
bb -> +2 + 2 = 4
ww -> -1 -1 = -2
wo -> -1 +0 = -1
bo -> -1 +0 = 2
oo -> +0 +0 = 0

$X = \{  1, 2,4,-2,-1,0 \}$
$$
\begin{align}
1 * P(wb) +
4 + P(bb) +
-2 + P(ww) +
-1 + P(ow) +
-1 + P(ob) +
0 + P(oo) \\
 \\

P(bw) = \frac{\binom{8}{1}\binom{4}{1}}{\binom{14}{2}} \\
P(bb) = \frac{\binom{4}{2}}{\binom{14}{2}} \\
P(ww) = \frac{\binom{8}{2}}{\binom{14}{2}} \\
P(oo) = \frac{\binom{2}{2}}{\binom{14}{2}} \\
P(wo) = \frac{\binom{8}{1}\binom{2}{1}}{\binom{14}{2}} \\
P(bo) = \frac{\binom{4}{1}\binom{2}{1}}{\binom{14}{2}} \\
\end{align}
$$