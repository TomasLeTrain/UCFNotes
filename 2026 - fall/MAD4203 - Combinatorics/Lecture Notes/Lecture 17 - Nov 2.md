# 6.3 - Derangements
Recall:
$$
\begin{align}
D_{n} = \# \text{derangements of } [n] \\
D_{n} = n!\left( 1 - \frac{1!}{1!} + \frac{1}{2!} - \frac{1}{3!} + \dots + (n-1)^{n} \frac{1}{n!} \right) \\
\end{align}
$$
**Remark:** $D_{1}, D_{2}, \dots, D_{n},\dots$
Defines a sequence $\left\{D_{n}\right\}_{n=1}^{\infty}$
Goal: deduce a recurrence relation among $D_{n}$'s

> [!theorem] 
> For all $n \geq 3$, $D_{n} = (n-1)(D_{n-1} + D_{n-2})$
^5b80c6

`\begin{proof}`@[[#^5b80c6]]
$D_{n} =$ \# permutations $i,i_{2},\dots,i_{n}$ of $[n]$ such that $i_{1}\neq_{1},i_{2}\neq_{2},\dots,i_{n}\neq n$.

For each $i \in \{ 2,3,\dots,n \},$ define $A_{i} = \{ i_{1},\dots,i_{n} | i_{1} = i, i_{2} \neq 2, \dots, i_{n} \neq n \}$
Then, $A_{2}, A_{3},\dots,A_{n}$ are pairwise disjoint, $|A_{2}| = |A_{3}| = \dots = |A_{n}|$

$$
\begin{align}
D_{n} = |A_{2}| + |A_{3}| + \dots + |A_{n}| \\
= (n-1)|A_{2}| \\
\end{align}
$$
So, how can we find $|A_{2}|$?

Consider the following cases:
![[Lecture 17 - Nov 2 2026-11-02 09.13.25.excalidraw]]

It can be seen that the first sequence has $D_{n-2}$ \# of derangements, since the first two elements are known and all others must be a derangement of elements $\{ 3,4,\dots n \}$

The second case will have $D_{n-1}$ derangements, since it equals the number of derangements of the sequence $\{ 1,3,4,\dots,n \}$.
Thus:
$$
\begin{align}
\boxed{ D_{n} = (n-1)(D_{n-2} + D_{n-1}) }
\end{align}
$$
`\end{proof}`

> [!theorem] 
> For all $n \geq 2$, $D_{n} = n * D_{n-1} + (-1)^{n}$
^af27b4

`\begin{proof}`@[[#^af27b4]]
$$
\begin{align}
D_{n} = (n-1)(D_{n-1} + D_{n-2}) \text{ for all } n \geq 3 \\
= n D_{n-1} - D_{n-1} + (n-1)D_{n-2} \\
\implies D_{n} - nD_{n-1} = (-1)\left( D_{n-1} - (n-1) D_{n-2} \right) \text{ for all } n \geq 3 \\
 \\
D_{n}-nD_{n-1} = \frac{D_{n}-nD_{n-1}}{D_{n-1} - (n-1)D_{n-2}} * \frac{D_{n-1} - (n-1)D_{n-2}}{D_{n-2} - (n-2)D_{n-3}} * \dots * \frac{D_{3} - 3D_{2}}{D_{2}-2D_{1}} * (D_{2} -2 D_{1}) \\ \\
(-1)^{n-2} * (D_{2} - 2 D_{1}) = (1-2*0) = (-1)^{n-2} = (-1)^{n} \\
\to a_{n} = \frac{a_{n}}{a_{n-1}} * \frac{a_{n-1}}{a_{n-2}} * \dots * \frac{a_{2}}{a_{1}} * a_{1} \\
\implies D_{n} = n D_{n-1} + (-1)^{n} \text{ for all } n \geq 3
\end{align}
$$
`\end{proof}`
## Example
$n$ men and $n$ women
Ways to make dancing partners: $n!$
now, everyone must change partners: $D_{n}$


# 6.4 - Another Forbidden Permutations

Goal: Let $X_{1},\dots,X_{n}$ be subsets (possibly empty) of $[n]$. Let $i_{1},\dots,i_{n}$ be a permutation of $[n]$ such that
- first position: $i_{1} \not\in X_{1}$
- second position: $i_{2} \not\in X_{2}$
- ...
- $n$'th position: $i_{n} \not\in X_{n}$

When $X_{i} = \{ i \}$ for $i = 1,\dots,n$, then $i_{1},\dots,i_{n}$ is a derangement

Let  $\mathcal{P}(X_{1},\dots,X_{n})$ be the set of all such permutations $i_{1}, \dots,i_{n}$ of $[n]$.

**Question** How to determine $p(X_{1},\dots,X_{n}) = |\mathcal{P}(X_{1},\dots,X_{n})|$?
**Answer:** No general formula is given. Apply IEP

*Setup:*
Let $S = \{ \text{permutations of }[n] \}$
For each $k \in [n]$, $A_{n} = \{ i_{1},\dots,i_{n} | i_{k} \in X_{k} \}$
Tnen
$$
\begin{align}
p(X_{1},\dots,X_{n}) = |\bar{A_{1}} \cap \bar{A_{2}} \cap \dots \cap \bar{A_{n}}| \\
= |S| - \sum |A_{i}| + \sum |A_{i} \cap A_{j}| - \sum |A_{i} \cap A_{j} \cap A_{k}| + \dots \\
= n! - (n-1)! r_{1} + (n-2)!r_{2} + \dots + (-1)^{n}(n-n)! r_{n}
\end{align}
$$
$$
\begin{align}
|S| = n! \\
|A_{k}| = |X_{k}| * (n-1)!
|A_{j} \cap A_{k}| = |X_{j}| * |X_{k}| * (n-2)!
\end{align}
$$

So
$$
\begin{align}
\sum |A_{i}| = (n-1)!(|X_{1}| + |X_{2}| + \dots) \\ \\

\sum |A_{i} \cap A_{j}| = (n-2)! (|X_{1}||X_{2}| + \dots) \\
\to\text{but, this only works if } A_{i} \cap A_{j} = \emptyset
\end{align}
$$
For each $k \in [n]$, define $r_{k}$ to be the \# of ways to place $k$ non-attacking rooks on an $x \times x$ chessboard where each $r$ rooks is in a forbidden position.
$r_{1} = |X_{1}| + |X_{2}| + \dots + |X_{n}|$
$r_{1} = ?$
So,
$$
\begin{align}
p(X_{1},X_{2},\dots,X_{n}) = n! - (n-1)! r_{1} + (n-2)!r_{2} + \dots + (-1)^{n}(n-n)! r_{n}
\end{align}
$$

Now,
$r_{1},\dots,r_{n}$ are non-trivial to find

## Example
$X = [n] = [4]$
$X_{1} = \{ 1,2 \}, X_{2} = \{ 2,3 \}, X_{3} = \{ 3,4 \}, X_{4} = \{ 1,4 \}$

Each rook has "forbidden" places (only places where they are allowed to be placed) on each of their respective row

**Solution:**
$$
\begin{align}
|S| = 4! \\
r_{1} = |X_{1}| +|X_{2}| + |X_{3}| + |X_{4}| = 8 \\
r_{2} = 5 + 5 + 4 + 3 + 2 + 1 \\
r_{3} = 3 + 2 + 1 + 3 + 2 + 1 + 2 + 1 + 1 \\
r_{4} = 1 + 1 = 2
\end{align}
$$
So,
$P(X_{1}, X_{2}, X_{3}, X_{4}) = 4! - 8 * 3! + 20 * 2! - 16 * 1! * 2 * 0 = 2$  

## Example 2
$X = [n] = [5]$
$X_{1} = \{ 1,4 \}, X_{2} = \{ 3 \}, X_{3} = \emptyset, X_{4} = \{ 1,5 \}, X_{5} = \{ 2,5 \}$
$$
\begin{align}
r_{1} = 2 + 1 + 2 + 2 = 7 \\
r_{2} = 4 + 5 + 4 + 2 + 1 = 16  \\
r_{3} = 3 + 1 + 4 + 2 + 1 + 2 + 1 = 8 + 6 = 14
\end{align}
$$