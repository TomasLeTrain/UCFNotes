## Example 4a
*$J$ is taking two books along on her holiday vacation. With probability .5 she will like the first book; with probability, 4 she will like the second book; and with probability .3 she will like both books. What is the probability that she likes neither book?*

Let $A$ be the event that she likes the first book. Let $B$ be the event that she likes the second book

We are finding $P((A \cup B)^{C})$, which we can derive from $P(A \cup B)$.
$$
\begin{align}
P(A) = 0.5 \\
P(B) = 0.4 \\
P(A \cap B) = 0.3 \\ \\
\end{align}
$$
We use inclusion-exclusion to solve now:
$$
\begin{align}
P(A \cup B) = P(A) + P(B) - P(A \cap B) \\
P(A \cup B) = 0.5 + 0.4 - 0.3 \\
P(A \cup B) = 0.6 \\
\boxed{ P((A \cup B)^{C}) = 1 - P(A \cup B) = 0.4 }
\end{align}
$$



Inclusion-exclusion for 3 elements
$$
\begin{align}
P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C)
\end{align}
$$

Example 5b???

## Poker example
P(straight)?

Lets consider only the case for a straight starting at $A$ ($A,2,3,4,5$).

The number of ways to build it is
$$
\begin{align}
\underbrace{ 4 * 4 * 4 * 4 * 4 }_{ \text{4 suit choices per card} } - \underbrace{ 4 }_{ \text{no straight flush} }
\end{align}
$$

Lets then consider doing this exact approach but instead starting at $2$, then $3$, etc.

This leads to
$$
\begin{align}
9 * (4^{5}-4)
\end{align}
$$
To get the probability we divide by total sample space, which is all ways to take 5 cards:
$$
\begin{align} \\
\boxed{ \frac{9*(4^{5}-4)}{\binom{52}{5}} }
\end{align}
$$

**NOTE:** this might be wrong, should double check