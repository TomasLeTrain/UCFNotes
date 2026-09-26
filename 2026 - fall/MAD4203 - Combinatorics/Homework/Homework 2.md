# 12
*Show by example that the conclusion of the Chinese remainder theorem (Application 6) need not hold when $m$ and $n$ are not relatively prime.*

Consider $m = 2, n = 6$
$$
\begin{align}
x = mp + a \\
x = nq + b
\end{align}
$$
consider the sequence:
$$
\begin{align}
a = 1 \to \\
1, 1 + 2, 1 + 4,\dots \\
\{ 1, 3, 5, 7, 9\} \mod 6 = \boxed{ 1, 3, 5 }, \boxed{ 1, 3, 5 } \dots
\end{align}
$$
The remainders repeat infinitely, meaning the argument based on the PP does not work.  In particular, the values $b = 0, 2, 4$ for $a = 1$ never have a shared $x$.

# 15
*Prove that, for any $n + 1$ integers $a_{1},a_{2},a_{n+1}$, there exist two of the integers $a_{i}$ and $a_{j}$ with $i \neq j$ such that $a_{i} - a_{j}$ is divisible by $n$.*

Consider rewriting each $a_{i}$ in the following form:
$$
\begin{align}
a_{i} = n p_{i} + r_{i} \to 0 \leq r_{i} \leq n-1
\end{align}
$$

There are at most $n$ distinct possible values for $r_{i}$, but $n+1$ elements, therefore by the PP, at least two numbers must share the same $r_{i}$:
$$
\begin{align}
r_{i} = r_{j}, i \neq j \\
a_{i}=  n p_{i} + r_{i}, a_{j} = n p_{j} + r_{j} \\
a_{i} - a_{j} = (n p_{i} + r_{i}) - (n p_{j} + r_{j}) \\
= (p_{i} - p_{j})n + (r_{i} + r_{j}) \\
= (p_{i} - p_{j})n \\
\square
\end{align}
$$

# 16
*Prove that in a group of $n > 1$ people there are two who have the same number of acquaintances in the group. (It is assumed that no one is acquainted with oneself).*
### Proof

TODO: weird?
Consider a fixed person $A$. They have $n-1$ connections, for which they can know or not know. Then for each $n-2$ connections,

Each person has $n-1$ connections of either knowing or not knowing a person. Thus, there are up to $n$ distinct \# of \# of known people that each person could have.

first person has n-1 connections, the next n-1 people have n-2 connections, ...

There are $n$ people, and $n$ distinct ways to have a \# of known people, so by the PP, two must share the same number of knowing people.


# 