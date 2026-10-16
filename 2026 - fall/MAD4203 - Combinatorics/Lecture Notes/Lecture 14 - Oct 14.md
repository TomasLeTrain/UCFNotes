# 5.3 Unimodality of Binomial Theorem
**Goal:**
$$
\begin{align}
\binom{n}{0},\binom{n}{1},\dots,\binom{n}{n}
\end{align}
$$
which term is the largest?

Equivalent to asking if $P = (\mathcal{P}(S),\subseteq)$ is a poset.
So, what is the largest size of an antichain in $P$?

Consider the Hassel diagram of $P$:
![[Lecture 14 - Oct 14 2026-10-14 09.09.33.excalidraw]]

Each level is an antichain


> [!definition] Unimodal sequence
> The sequence $S_{1},\dots,S_{n}$ is **unimodal** provided that there exists an integer $t, 0 \leq t \leq n$, such that 
> $$
> \begin{align}
> S_{0} \leq S_{1} \leq \dots \leq S_{t} \geq S_{t+1} \geq \dots S_{n}
> \end{align}
> $$
> The possible choices for the value of $t$ is $\binom{n+1}{1}$ since $0 \leq t \leq n$.

> [!theorem] 5.3.1 - Binomal Coefficients Unimodality
> Let $n$ be a positive integer. The sequence of binomal coefficients $\binom{n}{0}, \binom{n}{1},\dots,\binom{n}{n}$ is unimodal. More precisely, 
> $$
> \begin{align}
> \binom{n}{0} < \binom{n}{1} < \dots < \binom{n}{\left\lfloor  \frac{n}{2}  \right\rfloor } \geq \binom{n}{\left\lceil  \frac{n}{2}  \right\rceil } > \dots > \binom{n}{n} \\
> \text{n is even, } \binom{n}{\left\lfloor  \frac{n}{2}  \right\rfloor } = \binom{n}{\left\lceil  \frac{n}{2}  \right\rceil } \\
> \text{n is odd, } \binom{n}{\frac{n-1}{2}} = \binom{n}{\frac{n+1}{2}} \\
> \binom{n}{k} = \binom{n}{n-k}
> \end{align}
> $$
^aa41f9

Recall the [[Lecture 12 - Oct 7#^ec5d82]].
For the poset $P = (\mathcal{P}(S),\subseteq)$, it can be seen that there are $n!$ possible maximal chains:
$$
\begin{align}
\emptyset, \{1\}, \{1,2\}, \dots , \{ 1,2,\dots n \}
\end{align}
$$
At each step an element must get picked, and the order in which they get picked matters, making there be $n!$ possible such chains. All maximal chains must be of this form, meaning of size $n+1$.

> [!theorem] Sperner 1928
> Let $S = [n]$. Then, every antichain in $P=(\mathcal{P}(S),\subseteq)$ contains at most $\binom{n}{\left\lfloor  \frac{n}{2}  \right\rfloor}$ subsets of $S$.

**Question:** If $A$ is a subset of $[n]$ and $P = (\mathcal{P}([n]), \subseteq)$, How many maximal chains in $P$ containing A?
is it $\leq |A|$?

`\begin{proof}`@[[#^aa41f9]]
$$
\begin{align}
\frac{\binom{n+1}{k}}{\binom{n}{k}} = \frac{\frac{n!}{(k+1)!(n-k-1)!}}{\frac{n!}{k!(n-k-1)!}} \\
= \frac{n-1}{k+1}
\end{align}
$$
So, we must find when this ratio $<1, = 1, > 1$, Which would give an indication of which are bigger.
TODO: finish proof?
`\end{proof}`

# 5.6 - Symmetric chain partition
for Sperner's theorem
Let $S = [n], P = (\mathcal{P}(S), \subseteq)$.
> [!definition] Symmetric chain partition
> A chain partition of $P$ is a **symmetric chain partition** if for each chain $C_{1},C_{2},\dots,C_{m}$ in the partition:
> 1. $C_{1} \subseteq C_{2} \subseteq \dots \subseteq C_{m}$ 
> 2. $|C_{i}| = |C_{i+1}| - 1 \Longleftrightarrow |C_{i}| +1 = |C_{i+1}|$ for all $1 \leq i \leq m-1$
> 3. $|C_{1}| + |C_{m}| = n$

## Example
Find a symmetric chain partition of $P = (\mathcal{P}(S), \subseteq)$, where $S = \{1,2,3\}$

**Ans:**
$n=3$, odd, so $\binom{n}{\left\lfloor  \frac{n}{2}  \right\rfloor} = \binom{3}{1} = 3$. So, we must have 3 chains in the partition.
$$
\begin{align} \\
\emptyset, \{ 1 \}, \{ 1,2 \}, \{ 1,2,3 \} \to \text{maximal chain} \\
\{ 2 \}, \{ 2,3 \} \\
\{ 3 \}, \{ 1,3 \}
\end{align}
$$
*Remark:* For the symmetric chain partition, the $\emptyset$ must be part of the maximal chain in order to make the partition symmetric.

## Finding symmetric chain partitions
**Question:** How many chains are there in a symmetric chain partition?
**Ans:**
Sperner's Theorem: at most $\binom{n}{\left\lfloor  \frac{n}{2}  \right\rfloor}$.
Dilworth's Theorem: at least $\binom{n}{\left\lfloor  \frac{n}{2}  \right\rfloor}$ because the level $|L_{\left\lfloor  \frac{n}{2}  \right\rfloor}| = \binom{n}{\left\lfloor  \frac{n}{2}  \right\rfloor}$.
So,
$$
\begin{align}
\binom{n}{\left\lfloor  \frac{n}{2}  \right\rfloor } = \binom{n}{\left\lceil  \frac{n}{2}  \right\rceil }
\end{align}
$$

**Question:** How to obtain a symmetric chain partition for $P = (\mathcal{P}([n]), \subseteq)$?
**Answer:** Obtained inductively from a symmetric chain partition for $(\mathcal{P}([n-1]), \subseteq)$.

For each chain $C_{1},\dots,C_{m}$ from the poset with $S = [n-1]$, it is known that
$$
\begin{align}
C_{1} \subset C_{2} \subset \dots \subset C_{m}, \\
|C_{1}| + |C_{m}| = n-1 \\
|C_{i}| + 1 = |C_{i+1}|, 1 \leq i \leq n-2
\end{align}
$$

We create one/two new chains for the $[n]$ partition from the chain of the $[n-1]$ partition.
If $m \geq 2$, then two get created:
$$
\begin{align}
C_{1} \subset C_{2} \subset \dots \subset C_{m-1} \subset C_{m} \cup  \{ n \} \\
 \to |C_{1}| + |C_{m} \cup \{ n \}| = n = |S| \\ \\
 
C_{1} \cup \{ n \}, C_{2} \cup \{ n \}, \dots , C_{m-1} \cup \{ n \} \\
\to |C_{1} \cup \{ n \}| + |C_{m-1} \cup \{ n \}| = |C_{1}| + |C_{m-1}|+2 = n \\
\end{align}
$$

The $m = 1$, is a bit different
$$
\begin{align}
m = 1 \to
|C_{m}| + |C_{m}| = n-1 \\
2|C_{m}| = n-1 \implies n \text{ is odd} \\
= |C_{m}| = \frac{n-1}{2}
\end{align}
$$
So, to create a new chain:
$$
\begin{align}
C_{m} \subset C_{m} \cup \{ n \} \\
|C_{m}| + |C_{m} \cup \{ n \}| = 2|C_{m}| + 1 = (n-1)+1 = n
\end{align}
$$

## Example
Find a symmetric chain partition of $P = (\mathcal{P}(S), \subseteq)$, where $S = \{ 1,2,3,4 \}$
We know for $S = \{ 1,2,3 \}$:
$$
\begin{align}
\emptyset \subset \{ 1 \} \subset \{ 1,2 \} \subset \{ 1,2,3 \} \\
\{ 2 \} \subset \{ 2,3 \} \\
\{ 3 \} \subset \{ 1,3 \}
\end{align}
$$
For $S = [4]$, we can find the expected \# of chains with Sperner's:
$$
\begin{align}
n=4, \binom{4}{\left\lfloor  \frac{4}{2}  \right\rfloor} = \binom{4}{2} = 6
\end{align}
$$
The chains become:
$$
\begin{align}
\emptyset \subset \{ 1 \} \subset \{ 1,2 \} \subset \{ 1,2,3 \} \subset \{ 1,2,3,4 \}  \\
\{ 4 \} \subset \{ 1,4 \} \subset \{ 1,2,4 \} \\ \\

\{ 2 \} \subset \{ 2,3 \} \subset \{ 2,3,4 \} \\
\{ 2,4 \} \\ \\

\{ 3 \} \subset \{ 1,3 \} \subset \{ 1,3,4 \} \\
\{ 3,4 \} \\
\end{align}
$$

For $S = [5]$, 
$$
\begin{align}
n=5, \binom{5}{\left\lfloor  \frac{5}{2}  \right\rfloor } = \binom{5}{2} = \frac{5!}{2!3!} = 10
\end{align}
$$
So the chains are:
$$
\begin{align}
\emptyset \subset  \{ 1 \} \subset \{ 1,2 \} \subset \{ 1,2,3 \} \subset \{ 1,2,3,4 \} \subset \{ 1,2,3,4,5 \} \\
\{ 5 \} \subset \{ 1,5 \} \subset \{ 1,2,5 \} \subset \{ 1,2,3,5 \} \\
 \\
\{ 4 \} \subset \{ 1,4 \} \subset \{ 1,2,4 \} \subset \{ 1,2,4,5 \} \\
\{ 4,5 \} \subset \{ 1,4,5 \} \\ \\
 
\{ 2 \} \subset \{ 2,3 \} \subset \{ 2,3,4 \} \subset \{ 2,3,4,5 \} \\
\{ 2,5 \} \subset \{ 2,3,5 \} \\
 \\
\{ 2,4 \} \subset \{ 2,4,5 \} \\
 \\
\{ 3 \} \subset \{ 1,3 \} \subset \{ 1,3,4 \} \subset \{ 1,3,4,5 \} \\
\{ 3,5 \} \subset \{ 1,3,5 \} \\ \\

\{ 3,4 \} \subset \{ 3,4,5 \}
\end{align}
$$
