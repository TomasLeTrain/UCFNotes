
# Chapter 6 - The inclusion Exclusion Principle
In this chapter, we derive an important counting formula called the inclusion and eclusion principle (IEP): gives a formula for the most general circumstances in which the sets are free to overlap without restriction.

**Recall:**
Subtraction principle:
$$
\begin{align}
|A| = |U| - |\bar{A}|
\end{align}
$$

Addition principle:
$$
\begin{align}
A \cap B = \emptyset \to |A \cup B| = |A| + |B||
\end{align}
$$

DeMorgan's Law
$$
\begin{align}
\overline{A \cup B} = \bar{A} \cap \bar{B}  \\
\overline{A \cap B} = \bar{A} \cup \bar{B}  \\ \\

\overline{A_{1} \cup A_{2} \cup \dots \cup A_{m}} = \bar{A_{1}} \cap \bar{A_{2}} \cap \dots \cap \bar{A_{m}}  \\ \\

\overline{A_{1} \cap A_{2} \cap \dots \cap A_{m}} = \bar{A_{1}} \cup \bar{A_{2}} \cup \dots \cup \bar{A_{m}}  \\
\end{align}
$$
**Questions:**
1. How to compute $|A \cup B|$ if $A \cap B \neq \emptyset$?
2. How about $|A_{1} \cup A_{2} \cup \dots \cup A_{m}|$?

Let $S$ be a set and $P_{1},\dots,P_{m}$ be $m$ properties refering to the objects in $S$. For $i \in [m]$, define $A_{i} = \{ x \in S | x \text{ has property } P_{i} \}$.
Then, $\bar{A_{i}} = \{ x \in S | x \text{ doesn't have property } P_{i} \}$ 

$$
\begin{align}
\bar{A_{i}} \cap \bar{A_{j}} = \{ x \in S | x \text{ doesn't have property } P_{i} \text{ or } P_{j} \} \\
A_{i} \cap A_{j} = \{ x \in S | x \text{ has property } P_{i} \text{ or } P_{j} \} \\
\end{align}
$$
So,
$$
\begin{align}
A_{1} \cup \dots \cup A_{m} = \{ x \in S | x \text{ has at least one of the properties } P_{1},\dots_{P_{m}} \} \\
\bar{A_{1}} \cup \dots \cup \bar{A_{m}} = \{ x \in S | x \text{ has none of the properties } P_{1},\dots_{P_{m}} \}
\end{align}
$$

> [!theorem] Inclusion-Exclusion Principle
> The \# of objects in $S$ that have at least one of the properties $P_{1},\dots,P_{m}$ is given by
> $$
> \begin{align}
> |A_{1} \cup A_{2} \cup \dots \cup A_{m}| = \\
> \sum|A_{i}| - \sum_{i \neq j} |A_{i} \cap A_{j}| + \sum_{i \neq j \neq k} |A_{i} \cap A_{j} \cap A_{k}| - \dots 
> \end{align}
> $$

^842c00

> [!corollary] 
> The \# of objects in $S$ that have none of the properties $P_{1},\dots,P_{m}$ is:
> $$
> \begin{align}
> \bar{A_{1}} \cap \dots \cap \bar{A_{m}} = |S| - |A_{1} \cup \dots \cup A_{m}| \\
 = |S| - \sum |A_{i}| + \sum |A_{i} \cap A_{j}| - \dots
> \end{align}
> $$

**Recall:**
$$
\begin{align}
\binom{n}{0} - \binom{n}{1} + \binom{n}{2} + \dots + (-1)^{n} \binom{n}{n} = 0 \\
\boxed{ \binom{n}{1} - \binom{n}{2} + \dots = \binom{n}{0} = 1 }
\end{align}
$$

`\begin{proof}`@[[#^842c00]]
It suffices to show that each element $a \in A_{1} \cup \dots \cup A_{m}$ is counted exactly once in RHS.
Let $a \in A_{1} \cup \dots \cup A_{m}$ such that $a$ has exactly $n$ of the $m$ properties, say, $P_{1},\dots,P_{n}$, where $n \leq m$. 

Thus, the first sum $\sum |A_{i}|$ counts $a$ $n$ times (for every property $P_{1},\dots,P_{n}$ one count is added in total).
Then, the second sum $-\sum |A_{i} \cap A_{j}|$ subtracts $\binom{n}{2}$ copies of $a$, since it subtracts one copy for every pair of properties.

Generalizing, the total sum for the little $a$:
$$
\begin{align}
\binom{n}{1} - \binom{n}{2} + \binom{n}{3} + \dots + (-1)^{n+1}\binom{n}{n} + 0 + \dots + 0 = \binom{n}{0} = 1
\end{align}
$$
Anything after $\binom{n}{n}$ is zero since $|A_{1} \cap \dots \cap A_{n} \cap A_{n+1}| = 0$, since $a$ does not have the $n+1$'th property.

Since the total sum equals 1, the element $a$ is only counted once after all sums.
`\end{proof}`


## Example 1
How many permutations of the letters $MATHISFUN$ are there such that none of the words are $MATH$, $IS$, $FUN$.
**Ans:**
`\begin{proof}`
Looking for $|\bar{A_{1}} \cap \bar{A_{2}} \cap \bar{A_{3}}|$, which is equivalent to:
$$
\begin{align}
|S| - |A_{1} \cup A_{2} \cup A_{3} |
\end{align}
$$
Where $S =$ the set of permutations of $\{ M,A,T,H,I,S,F,U,N \}$.
$A_{1} =$ the set of permutations of $\{ MATH, I, S, F, U, N \}$.
$A_{2} =$ the set of permutations of $\{ M, A, T, H, IS, F, U, N \}$.
$A_{3} =$ the set of permutations of $\{ M, A, T, H, I, S, FUN \}$.

$$
\begin{align}
|S| = 9! \\
|A_{1}| = 6! \\
|A_{2}| = 8! \\
|A_{3}| = 7! \\
|A_{1} \cap A_{2}| = 5! \\
|A_{1} \cap A_{3}| = 4! \\
|A_{2} \cap A_{3}| = 6! \\
|A_{1} \cap A_{2} \cap A_{3}| = 3!
\end{align}
$$
By IEP,
$$
\begin{align}
|\bar{A_{1}} \cap \bar{A_{2}} \cap \bar{A_{3}}| = |S| - \sum |A_{i}| + \sum |A_{i} \cap A_{j}| - |A_{1} \cap A_{2} \cap A_{3}| \\
= 9! - (6! + 8! + 7!) + (5! + 4! + 6!) - 3!
\end{align}
$$
`\end{proof}`
**Remark:** For full points, give formula and plugged in numbers, but don't go further!!

## Special case of IEP
$$
\begin{align}
\alpha_{0} = |S| \\
\alpha_{1} = |A_{1}| = |A_{2}| = \dots = |A_{m}| \\ 
\alpha_{2} = |A_{1} \cap A_{2}| = \dots = |A_{m-1} \cap A_{m}| \\
\dots \\
\alpha_{m} = |A_{1} \cap A_{2} \cap \dots \cap A_{m}| \\
\to \\
|\bar{A_{1}} \cup \bar{A_{2}} \cup \dots \cup \bar{A_{m}}| = \alpha_{0} - \binom{m}{1} \alpha_{1} + \binom{m}{2} \alpha_{2} - \dots + (-1)^{m} \binom{m}{m} \alpha m
\end{align}
$$


## Example 2
Find the \# of onto functions from $X$ to $Y$, where $|X| = n, |Y| = m$.
**Ans:**
`\begin{proof}`
Let $S$ be the set of functions from $X$ to $Y$.

Let 
$$
\begin{align}
A_{i} = \{ \text{ function $f$ in S such that } y_{i} \text{ has no preimage under $f$} \} \\
= \{ f \in S | y_{i} \not\in f(x)  \}
\end{align}
$$

The \# of onto functions from $X$ to $Y$:
$$
\begin{align}
|\bar{A_{1}} \cap \bar{A_{2}} \cap \dots \cap \bar{A_{m}}| = |S| - \sum |A_{i}| + \sum |A_{i} \cap A_{j}| + \dots + (-1)^{m} |A_{1} \cap \dots \cap A_{m}| \\
\end{align}
$$
This is the special case of IEP, so:
$$
\begin{align}
\alpha_{0} = |S| = m^{n} \\
\alpha_{1} = |A_{1}| = (m-1)^{n} \\
\alpha_{2} = |A_{1} \cap A_{2}| = (m-2)^{n} \\
\dots \\
\alpha_{m} = |A_{1} \cap A_{2} \cap \dots \cap A_{m}| = 0
\end{align}
$$
So, answer is:
$$
\begin{align}
\boxed{ m^{n} - \binom{m}{1}(m-1)^{n} + \binom{m}{2}(m-2)^{n} + \dots + (-1)^{n} \binom{n}{n}(m-m)^{n} }
\end{align}
$$
`\end{proof}`

## Example 3
Determine \# of permutations of $\{ 1,2,\dots,9 \}$ in which at least 1 even integer is in its natural position. 
**Ans:**
`\begin{proof}`
Let $A_{1} =$ \# of permutations of set $\{ 1,3,4,5,6,7,8,9 \}$, since $2$ has only one position it can go in.
Let $A_{2} =$ \# of permutations of set $\{ 1,2,3,5,6,7,8,9 \}$, since $4$ has only one position it can go in.
...
Let $A_{4} =$ \# of permutations of set $\{ 1,2,3,4,5,6,7,9 \}$, since $8$ has only one position it can go in.

This is a special case of IEP, so:
$$
\begin{align}
\alpha_{1} = |A_{1}| = 1 * 8! \\
\alpha_{2} = |A_{1} \cap A_{2}| = 1 * 1 * 7! \\
\alpha_{3} = |A_{1} \cap A_{2} \cap A_{3}| = 1 * 1 * 1 * 6! \\
\alpha_{4} = |A_{1} \cap A_{2} \cap A_{3} \cap A_{4}| = 1 * 1 * 1 * 1 * 5! \\ \\
\end{align}
$$

So answer is
$$
\begin{align}
|A_{1} \cup A_{2} \cup \dots A_{m}| = \sum |A_{i}| - \sum |A_{i} \cap A_{j}| + \dots + (-1)^{m+1} |A_{1} \cap A_{2} \cap \dots \cap A_{m}| \\ \\
= \binom{n}{1} \alpha_{1} - \binom{n}{2} \alpha_{2} + \binom{n}{3} \alpha_{3} - \binom{n}{4} \alpha_{4} \\
\boxed{ = \binom{n}{1} * 8! - \binom{n}{2} 7! + \binom{n}{3} 6! - \binom{n}{4} 5! }
\end{align}
$$

`\end{proof}`
