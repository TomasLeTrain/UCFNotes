# Question 33
A forest contains 20 elk, of which 5 are captured, tagged, and then released. A certain time later, 4 of the 20 elk are captured, what is the probability that 2 of the 4 have been tagged?

5 captured 15 not captured

$$
\begin{align}
\binom{5}{2} \binom{15}{2}  \\
N = \binom{20}{4} \\
\to \\
\boxed{ \frac{\binom{5}{2} \binom{15}{2}}{\binom{20}{4}} } \\
\frac{15*14 * 5*4 * 4!}{20*19*18*17*2*2} \\
\to \frac{15 * 14 * 5 * 4!}{20*19*18*17} \\
\to \frac{3 * 5 * 2 * 7 * 5 * 4!}{4 * 5 * 19 * 2 * 9 * 17} \\
\to \frac{5 * 7 * 4!}{4 * 19 * 3 * 17} \\
\to \frac{35 * 4!}{12 * 19 * 17} \\
\to \frac{35 * 2}{19 * 17} \\
\boxed{ \to \frac{70}{19 * 17} \\ }
\end{align}
$$

k

# Example 25
A pair of dice is rolled until a sum of either 5 or 7 appeears. Find the probability that a 5 occurs first.
*Hint:* Let $E_{n}$ denote the event that a 5 occurs on the nth roll and no 5 or 7 occurs on the first $n-1$ rolls. Compute $P(E_{n})$ and argue that $\sum_{n=1}^{\infty} P(E_{n})$ is the desired probability.

Let $E_{5}$ be the event that a sum of 5 is rolled and $E_{7}$ be the event that a sum of 7 is rolled: 
$$
\begin{align}
E_{5} = 4 \to (1 + 4, 4 + 1) * 2 \\
E_{7} = 6 \to (1 + 6, 2 + 5, 3 + 4) * 2 \\ \\ \\

P(E_{5}) = \frac{4}{36} \\
P(E_{7}) = \frac{6}{36} \\ \\
 \\ \\
\end{align}
$$

Now let $G_{n}$ be the even that neither 5 or 7 has been rolled in the first $n$ rolls:
$$
\begin{align} \\
G_{1} = (E_{5} \cup E_{7})^{C}  \\
P(G) = 1 - \left( \frac{4}{36} + \frac{6}{36}  \right) \\ \\
= 1 - \frac{10}{36} = \boxed{ \frac{26}{36} } \\ \\

P(G_{1}) = \frac{26}{36} \\
P(G_{2}) = \frac{26 * 26}{36 * 36} \\
P(G_{2}) = \frac{26 * 26 * 26}{36 * 36 * 36} \\ \\
\dots
\boxed{ P(G_{n}) = \frac{26^{n}}{36^{n}} }
\end{align}
$$


Then
$$
\begin{align} \\
P(E_{n}) = P(G_{n-1}) * \frac{4}{36} \\
\end{align}
$$
*Remark:* it is better to think about the possibilities instead of probabilities, so while this is numerically correct the following is better
$$
\begin{align}
E_{n} = G_{n-1} * 4 \\
\boxed{ P(E_{n}) = \frac{26^{n-1} * 4}{36^{n}} }
\end{align}
$$

Then the answer becomes:
$$
\begin{align}
\sum_{n=1}^{\infty} P(E_{n}) =   \sum_{n=1}^{\infty} \frac{26^{n-1} * 4}{36^{n}}  \\ \\
= \frac{4}{36} * \sum_{n=1}^{\infty} \left( \frac{26}{36} \right)^{n-1} \\ \\
\end{align}
$$
Geometric series, where $a = \frac{4}{36}$ and $r = \frac{26}{36}$:
$$
\begin{align}
\sum\dots = \frac{a}{1-r} = \boxed{ \frac{\frac{4}{36}}{1-\frac{26}{36}} } \\
= \frac{4}{36-26}
\end{align}
$$


# Example 17
If 8 rooks (castles) are randomly placed on a chess-board, compute the probability that none of hte rooks can capture any of the others. That is, compute the prbaobility that no row or file contains more than one rook.


For every rook, choose a row/col that is not picked yet and place there
Therefore:
$$
\begin{align}
\text{first rook } = \binom{8}{1} *\binom{8}{1} = 64 \\
\text{second rook } = \binom{7}{1} *\binom{7}{1} = 49 \\
\text{third rook } = \binom{6}{1} *\binom{6}{1} = 36  \\
\dots \\
8^{2} * 7^{2} * 6^{2} * \dots * 1 \\
(8 * 7 * 6 * 5* \dots) * (8 * 7 * 6 * 5* \dots) \\
\text{\# of combinations} = 8! *8! \\
\text{sample space of first rook } = 64 \\
\text{sample space of second rook } = 63 \\
\text{sample space of third rook } = 62 \\ \\
\dots \\
P(E) = \frac{8!8!}{64 * 63 * 62 * \dots * 56} =  \\
\boxed{ P(E) = \frac{8!8!}{\binom{64}{8}} }
\end{align}
$$

# Example 27

An urn contains 3 red and 7 black balls. Players $A$ and $B$ withdraw balls from the urn consecutively until a red ball is selected. Find the probability that $A$ selects the red ball. ($A$ draws the first ball, then $B$, and so on there is no replacement of the balls drawn.)

***Note:*** below is a better derivation using combinatorics instead of direct counting

A first picks + 
A doesn't pick, $B$ doesn't pick, A picks + 
A doesn't pick, $B$ doesn't pick, A doesn't pick, $B$ doesn't pick +  A picks +
...

Let Event $A_{n}$ be the probability that $A$ picks red in the $n$th pick, given none have been taken before
Let Event $B_{n}$ be the probability that $B$ picks red in the $n$th pick, given none have been taken before

$$
\begin{align}
A_{1} = 3, A_{3} = 3, A_{5} = 3 \\
P(A_{1}) = \frac{3}{10}, P(A_{3}) = \frac{3}{8}, P(A_{5}) = \frac{3}{6} \\

B_{2} = 3, B_{4} = 3, B_{6} = 3 \\
P(B_{2}) = \frac{3}{9}, P(B_{4}) = \frac{3}{7}, P(B_{6}) = \frac{3}{5} \\
 \\
P(A_{1}) + P(A_{1}^{C} \cap B_{2}^{C} \cap A_{3}) + P(A_{1}^{C} \cap B_{2}^{C} \cap A_{3}^{C} \cap B_{4}^{C} \cap A_{5}) + \dots \\
 \\
P(A_{1}) = \boxed{ \frac{3}{10} } \\
P(A_{1}^{C} \cap B_{2}^{C} \cap A_{3}) = \left( 1-\frac{3}{10}  \right)* \left( 1 - \frac{3}{9} \right) * \frac{3}{8} = \boxed{ \frac{7}{10} * \frac{6}{9}* \frac{3}{8} } \\ \\
P(A_{1}^{C} \cap B_{2}^{C} \cap A_{3}^{C} \cap B_{4}^{C} \cap A_{5}) = \left( 1-\frac{3}{10}  \right)* \left( 1 - \frac{3}{9} \right) * \left( 1-\frac{3}{8} \right)  * \left( 1 - \frac{3}{7} \right) * \frac{3}{6} \\
= \boxed{ \frac{7}{10}* \frac{6}{9} * \frac{5}{8}* \frac{4}{7} * \frac{3}{6} }
\end{align}
$$

$$
\begin{align}
\frac{3}{10} + \\
\frac{7}{10} * \frac{6}{9} * \frac{3}{8} + \\
\frac{7}{10} * \frac{6}{9} * \frac{5}{8} * \frac{4}{7} * \frac{3}{6} + \\
\frac{7}{10} * \frac{6}{9} * \frac{5}{8} * \frac{4}{7} * \frac{3}{6} * \frac{2}{5} * \frac{3}{4} \\ \\
\to \\
\frac{3}{10}+ \\ \\

\frac{7*6*3}{10*9*8} +  \\ \\

\frac{7*6 * 5 * 4 * 3}{10*9*8 * 7 * 6} +  \\ \\

\frac{7*6 * 5 * 4 * 3 * 2 * 3}{10*9*8 * 7 * 6 * 5 * 4} +  \\
 \\

\end{align}

$$
## Second Derivation
Another way to derive is to think about is
First way is picking a red: 3 choices
Second way is picking 2 black that were chosen as first 2 balls ($A$ and $B$) and number of ways to choose a red: $3 * \binom{7}{2}$ choices
so on and so forth
$$
\begin{align} \\
 P(E) = 
 \frac{\binom{7}{0} * 3}{\binom{10}{1}} +
\frac{\binom{7}{2} * 3}{\binom{10}{3}} +
\frac{\binom{7}{4} * 3}{\binom{10}{5}} +
\frac{\binom{7}{6} * 3}{\binom{10}{7}}
\end{align}
$$



# Example ? - Spinners
3 spinners, player $A$ first chooses a spinner and spins (equal chance of any number), then player $B$ chooses from the leftover spinners. Whoever has a greater number wins. Is it better to pick first or second?

First spinner: $S_{1}= \{ 1,5,9 \}$
Second spinner: $S_{2}= \{ 3,4,8 \}$
Third spinner: $S_{3}= \{ 2,6,7 \}$

If given $A$ chose spinner 1 and $B$ chose spinner 2, all the choices can be represented by the cartesian product $S_{1} \times S_{2}$:
$$
\begin{align}
S_{1} \times S_{2} = \{ \underbrace{ (1,3) ,(1,4), (1,8) }_{ B }, \underbrace{ (5,3), (5,4) }_{ A }, \underbrace{ (5,8) }_{ B }, \underbrace{ (9,3), (9,4), (9,8) }_{ A } \} \\ \\
\end{align}
$$
So in total $A$ wins 5 out of 9 times, and $B$ wins 4 out of 9 times.
This means that in this scenario $A$ is more likely to win.

This means $S_{1}$ is better than $S_{2}$.

Same logic is applied to all combinations of spinners. In the end, each spinner ends being beating and beating another, so for any spinner chosen by $A$, you can choose one that can beat that spinner. Therefore, its most optimal to choose second i.e. player $B$ always wins.

# Example 39
There are 5 hotels in a certain town. If 3 people check into hotels in a day, what is the probability that they each check into a different hotel? What assumptions are making?

Total number of choices is $5^{3}$.
The choice for the first person is 5, then the next  person is 4 (can't pick the first person's), etc.

$$
\begin{align}
\frac{5 *4 * 3}{5^{3}}
\end{align}
$$


# Chapter 3 - Conditional Probability and Independence

## Definition of Conditional probability
Let $E,F$ be events in a sapmle space $S$ 
If $P(F) > 0$, then : $P(E | F) = \frac{P(EF)}{P(F)}$ (read as $E$ given $F$)

Consequently
$$
\begin{align}
\boxed{ P(EF) = P(E | F) P(F) }
\end{align}
$$
Let $E_{1}, E_{2}, \dots,E_{n}$ be events in a sample space
Then
$$
\begin{align}
P(\underbrace{ E_{1} E_{2} E_{3}\dots E_{n} }_{ \text{intersection} }) = P(E_{1}) P(E_{2} | E_{1}) P(E_{3} | E_{1}E_{2})  \dots P(E_{n} | \underbrace{ E_{1}E_{2}\dots E_{n-1} }_{ \text{intersection} }) \\
\end{align}
$$

## Proof

Let $E = E_{n}, F = E_{1}E_{2}\dots E_{n-1}$

Then by expanding the definition $P(EF) = P(E|F) P(F)$:
$$
\begin{align}
 P(E_{n} E_{n_{1}} E_{n_{2}} \dots E_{n-1}) = P(E_{n} | E_{1}E_{2}\dots E_{n-1}) * P(E_{1}E_{2}\dots E_{n-1})
\end{align}
$$
Recursively expanding the second term of the RHS gives the formula for intersction as seen above

