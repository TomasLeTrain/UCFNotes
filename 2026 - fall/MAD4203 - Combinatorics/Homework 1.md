# 9
In how many ways can 15 people be seated at a round table if B refuses to sit next to A? What if B only refuses to sit on A's right?

## a
Place a first (1 choice, circular permutation). then you have 12 choices to seat $b$ (not left of a / right of a / place of a). Then you place any other person, have 13 spots to place (not place of a/$b$, no restrictions on placement). By this logic the next person has 12 spots, then the next 11, etc.
$$
\begin{align}
1 * 12 * 13 * 14 * \dots =
\boxed{ 12 * 13! }
\end{align}
$$

## b
Same logic as a, except that $b$ has one more spot where it can sit

$$
\begin{align}
1 * 13 * 13 * 14 * \dots = 
\boxed{ 13 * 13! }
\end{align}
$$

# 16
$$
\begin{align}
\binom{n}{r}= \binom{n}{n-r} \\
\frac{n!}{r!(n-r)!}=\frac{n!}{(n-r)!(n-(n-r))!} \\
=\frac{n!}{(n-r)!(n-n+r)!} \\
=\frac{n!}{(n-r)!r!} \\
=\boxed{ \frac{n!}{r!(n-r)!} }
\end{align}
$$
# 26
*A group of $mn$ people are to be arranged into m teams each with n players.*
## a.
*Determine the number of ways if each team has a different name.*


If we imagine giving out some $t_{k}$ for every player, then every player will be assigned a team. By making a set of all teams with every element having $n$ items, we ensure the resulting teams all have $n$ items. Since the order in which the people get picked doesn't matter (only the position of the items matters, therefore it's a permutation).
$$
\begin{align} \\
S = \{ n * t_{1}, n * t_{2}, \dots, n * t_{m} \} \\
\frac{(nm)!}{n!n!n!n!n!\dots} = \boxed{ \frac{(nm)!}{m * n!} }
\end{align}
$$


## b.
*Determine the number of ways if the teams don't have names.*

In this case we only consider the grouping of people, not the different combinations of teams.
This means that multiple permutations of different team combinations reduce to the same combination of groupings.

There are $m!$ ways to arrange teams, therefore we must reduce by that amount:
$$
\begin{align} \\
\boxed{ \frac{(nm)!}{m*n!*m!} }
\end{align}
$$

# 33

Determine the number of 10-permutations of the multiset $S = \{3* a,4* b,5* c\}$.

Instead of constructing the permutation we can remove 2 elements from $S$ and count the ways to construct the permutation that way.

This reduces the problem to finding permutations of a multiset with length $10$. However, the repetition numbers for each element depend on which numbers get taken out, so all cases have to be done manually. 

$$
\begin{align}
(a,a) \to S = \{ 1* a, 4 * b, 5 * c \} \to \frac{10!}{1!4!5!} \\
(a,b) \to S = \{ 2* a, 3 * b, 5 * c \} \to \frac{10!}{2!3!5!} \\
(a,c) \to S = \{ 2* a, 4 * b, 4 * c \} \to \frac{10!}{2!4!4!} \\
(b,b) \to S = \{ 3* a, 2 * b, 5 * c \} \to \frac{10!}{3!2!5!} \\
(b,c) \to S = \{ 3* a, 3 * b, 4 * c \} \to \frac{10!}{3!3!4!} \\
(c,c) \to S = \{ 3* a, 4 * b, 3 * c \} \to \frac{10!}{3!4!3!} \\ \\
|P| = |P_{a,a}| +  |P_{a,b}| + \dots \\
|P| = 
\frac{10!}{1!4!5!}+
\frac{10!}{2!3!5!}+
\frac{10!}{2!4!4!}+
\frac{10!}{3!2!5!}+
\frac{10!}{3!3!4!}+
\frac{10!}{3!4!3!}

\end{align}
$$


**NOTE:** this was an original attempt at the problem, I confused it for permutations of a multiset with infinite repetition numbers
$$
\begin{align} 
\binom{n+r-1}{r} \to \binom{(12)+(10)-1}{10} = \binom{21}{10} \\
\binom{21}{10} = \boxed{ \frac{21!}{10!11!} }
\end{align}
$$

# 36
Determine the total number of combinations (of any size) of a multiset of objects of $k$ different types with finite repetition numbers $n_{1}, n_{2}, . .. ,n_{k}$, respectively.

For every element we can choose in the range $[0, n_{k}]$ number of objects for the combination. This means the \# of choices for each element is $n_{k}+1$. We can use the product rule to multiply the choices for each element since the choice happens for every element for every combination.
$$
\begin{align}
(n_{1}+1)*(n_{2}+1)* \dots * (n_{k}+1)
\end{align}
$$


# 38
*How many integral solutions of*
$$
\begin{align}
x_{1}+x_{2}+x_{3}+x_{4}=30 \\
\end{align}
$$
satisfy $x_{1}\geq {2},x_{2}\geq {0},x_{3}\geq -5, x_{4}\geq 8$?

$$
\begin{align}
y_{1} = x_{1} - 2,\ y_{2}  = x_{2},\ y_{3} = x_{3} + 5,\ y_{4} = x_{4}-8 \\ \\
y_{1} + y_{2}+y_{3}+y_{4} = 30 -2 +5 -8 \\
y_{1} + y_{2}+y_{3}+y_{4} = 25 \\
y_{1}, y_{2}, y_{3}, y_{4}\geq 0
\end{align}
$$
This becomes the same as combinations of a multiset with infinite repetition numbers:
$$
\begin{align}
\binom{k+r-1}{r} = \binom{4 + 25 - 1}{25} \\
\binom{28}{25} = \frac{28!}{25!(28-25)!} = \boxed{ \frac{28!}{25!3!} }
\end{align}
$$


$$
\begin{align}
S = \{ 2 * c,5 * d \} \\ \\
\end{align}
$$
## 40
There are $n$ sticks lined up in a row, and $k$ of them are to be chosen.
	a. How many choices are there?
	b. How many choices are there if no two of the chosen sticks can be consecutive?
	c. How many choices are there if there must be at least $l$ sticks between each pair of chosen sticks


## A
$$
\begin{align}
\binom{n}{k}=\frac{n!}{k!(n-k)!}
\end{align}
$$
## B
Equivalent to ways of inserting chosen sticks bewteen non-chosen sticks

\# ways to choose non-chosen sticks
$$
\begin{align}
r = n - k \\
\binom{n}{r} = \binom{n}{n-k} = \binom{n}{k}
=\frac{n!}{k!(n-k)!}
\end{align}
$$

now there are $n-k+1$ gaps in which we can place chosen sticks, and there are $k$$% 
$$
\begin{align}
\frac{n-k+1}{k}
\end{align}
$$


Abar is at least 

## C


