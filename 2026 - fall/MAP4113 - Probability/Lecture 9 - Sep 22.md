# Example 4g
A system composed of $n$ separate components is aid to be a parallel system fi it functons when at least one of the components functions. FOr such a system, if component $i$, which is independent of other components, functions with probability $p_{i},i=1,\dots,n$ what is the probability that it functions?


# Example 3.74
Tfere is a $50-50$ chance that the queen carries the gene for hemophilia. If she is a carrier, then each pricne has a $50-50$ chance of having hemophilia. If the queen has had three princes without the disease, what is the probability that the queen is a carrier? If there is a fourth prince, what is the probability that he will have hemophilia?

$$
\begin{align}
P(P_{i}^{C} | Q) = 0.5,i \in \{ 1,2,3 \} \\
P(P_{1}^{C} \cap P_{2}^{C} \cap P_{3}^{C} | Q) = P(P_{1} | Q) P(P_{2} | Q) P(P_{3} | Q) =  0.5^{3} \\
P(Q) = P(Q^{C}) = 0.5 \\ \\

P(P_{i}^{C}) = P(P_{i}^{C}|Q)P(Q) + P(P_{i}^{C}|Q^{C})P(Q^{C}) \\
P(P_{i}^{C}) = 0.5P(Q) + 0P(Q^{C}) \\
P(P_{i}^{C}) = 0.5 * P(Q^{C}) = 0.5^{2}  \\ \\

 \\
P(Q \cap (P_{1}^{C} \cap P_{2}^{C} \cap P_{3}^{C})) = P(P_{1}^{C} \cap P_{2}^{C} \cap P_{3}^{C}|Q) P(Q) \\
= 0.5^{3} * 0.5 = 0.5^{4}
 \\

P(Q | P_{1}^{C} \cap P_{2}^{C} \cap P_{3}^{C}) = \frac{P(Q \cap (P_{1}^{C} \cap P_{2}^{C} \cap P_{3}^{C}))}{P(P_{1}^{C} \cap P_{2}^{C} \cap P_{3}^{C})} \\
P(Q | P_{1}^{C} \cap P_{2}^{C} \cap P_{3}^{C}) = \frac{P(Q \cap (P_{1}^{C} \cap P_{2}^{C} \cap P_{3}^{C}))}{0.5^{2}*0.5^{2}*0.5^{2}} \\ \\
= \frac{0.5^{4}}{0.2^{6}} = 0.5^{2} = \boxed{ 0.25 }
\end{align}
$$


# Example 4h
Roll a pair of dice

P(roll a sum of 5 before you roll a sum of 7)

TODO: use conditional probability to solve 

# Example 3.81
$A$ and $B$ play a series of games. Each game is independently won by $A$ with probability $p$ and by $b$ with probability $1-p$. They stop when the total number of wins of one of the players is two greater than that of the other player. The player with the greater number of total wins is declared the winner of the series. 

## A
Find the probability that a total of 4 games are played.
## B
Find the probabilty that A is the winner of the series.


could develop a pattern:
$$
\begin{align} \\
AB\ AB\ AA \\
AB\ BA\ AA \\
BA\ BA\ AA \\
BA\ AB\ AA \\
\end{align}
$$
basically go through all ways to match ab and ba some number of times:
$$
\begin{align}
n \to 2^{n-1} \\ \\
\to \\
\sum_{i=1}^{\infty } \frac{2^{i-1}}{\dots}
\end{align}
$$

But there is an easier method:

$$
\begin{align}
\{ AB,BA,AA,BB \}
\end{align}
$$
Let $W$ = event that $A$ wins 
$$
\begin{align}
P(W) = P(W \cap AB) \cup P(W \cap (BA)) \cup (W \cap (AA)) \cup (W \cap (BB)) \\
= P(W \cap AB) + P(W \cap BA) + P(W \cap AA) + P(W \cap BB) \\
= \underbrace{ P(W|AB) }_{ P(W) }\underbrace{ P(AB) }_{ p(1-p) } + \underbrace{ P(W|BA) }_{ P(W) }\underbrace{ P(BA) }_{ p(1-p) } + \underbrace{ P(W|AA) }_{ 1 }\underbrace{ P(AA) }_{ p^{2} } + \underbrace{ P(W|BB) }_{ 0 }\underbrace{ P(BB) }_{ (1-p)^{2} } \\ \\
\boxed{ P(W) = P(W) * p(1-p) + P(W) * p(1-p) + p^{2} }
\end{align}
$$

