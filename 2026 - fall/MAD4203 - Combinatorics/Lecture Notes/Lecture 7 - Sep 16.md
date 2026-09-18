## Pigeonhole Principle (Strong Form)

If $q_{1} + q_{2} + \dots + q_{n} - n + 1$ or more objects are placed into $n$ boxes, then
box 1 has $q_{1}$, or more of the objects, or
box 2 has $q_{2}$ or more of the objects, or 
...
box $n$ has $q_{n}$ or more of the objects.
## Proof by contradiction
Suppose box $i$ contains at most $q_i-1$ of the objects.
For $i=1,\dots,n$. Then we have at most $(q_{1}-1) + (q_{2}-1) + (q_{n}-1)$
$= q_{1}+q_{2}+\dots+q_{n}-n$ objects. In total, a contradiction. $\square$

*Remarks:*
1. If $m$ objects are palced into $n$ boxes, then some box must contain at least $\left\lceil  \frac{m}{n}  \right\rceil$ objects.
2. Given $n$ integers $a_{1},\dots,a_{n}$, If $\frac{a_{1} + a_{2} + \dots + a_{n}}{n} < r$, then $\exists \ i$ such that $a_{i} < r$. Similarly, If $\frac{a_{1} + a_{2} + \dots + a_{n}}{n} > r$, then $\exists \ i$ such that $a_{i} > r$. (and same for $\geq r$).
Another way to look at it:
$$
\begin{align}
\frac{g * n}{n} < r \\
\to g * n < n * r
\to g < r
\end{align}
$$
And $g$ is the smallest number any $a_i$ could possibly be.

# Example 1
Suppose there are $n^{2}  + 1$ people in a straight line. Then it is always possible to choose $n+1$ of them one step forward so that going left to right, their heights are etiher increasing or decreasing.
## Theorem - Erdos-Szekeres 1935.
Every sequence $a_{1},\dots,a_{n^{2}+1}$ of $n^{2}+1$ real numbers, contains either an increasing or decreasing subsequence of length $n+1$.


# Ramsey Theory - Applications of the strong PP
If six or more people, either there are three, each pair of whom are acquainted, or each pair of whom are unacquainted.

**Why six?** 
![[Lecture 7 - Sep 16 2026-09-16 09.31.26.excalidraw|85%]]

## Proof
Let $A,B,C,D,E,F$ be six people.
Single A out. By the Strong PP, at least $\left\lceil  \frac{5}{2}  \right\rceil = 3$ of $B,C,D,E,F$ are either acquainted or unacquainted w/ $A$.
![[Lecture 7 - Sep 16 2026-09-16 09.42.01.excalidraw|40%]]

By symmetry, we may assume that $B,C,D$ know $A$:
![[Lecture 7 - Sep 16 2026-09-16 09.46.19.excalidraw|60%]]

Therefore, there are 2 cases, one where $B,C$, $C,D$ or $B,D$ know each other, in which case a blue triangle forms. In the latter case, none of $B,C,D$ know each other, but in doing so form a red triangle.

Another phrasing: we may assume no two of $B,C,D$ are acquainted. Then $B,C,D$ are mutually unacquinted. $\square$

## Graph theory notation
$k_{n} \to (k_{s},k_{t})$
Among $n$ or more peole, there are $s$ of them that are mutually acquinted or there are $t$ of them that are mutually unacquainted.

### The ramsey number
$R(s,t) = \min \{ n \mid k_{n}\to k_{s},k_{t} \}$

*Remark:* if $k_{n} \to (k_{s},k_{t})$, then $k_{n} \to (k_{t},k_{s})$

$$
\begin{align}
R(3,3) = 6 \Longleftrightarrow \\ \\
\begin{array}
R(3,3) \leq 6 \\
R(3,3) \geq 6
\end{array} \\
\text{because } k_{5} \nrightarrow (k_{3},k_{3})
\end{align}
$$
Other ramsey numbers:
$$
\begin{align}
R(2,2) = 2 \\
 k_{1} \nrightarrow (k_{2},k_{2}) \\ \\
 
R(2,3) = 3 \quad (k_{2} \nrightarrow (k_{2},k_{3})) \\
 \\
\boxed{ R(2,t) = R(t,2) = t }
\end{align}
$$
### proof
For any ramsey number of the form $R(2,t)$ we cannot connect any people (otherwise the 2 condition gets met). Therefore, the minimum number of people must be $t$, since if none are connected then $t$ must be unacquainted.

## Ramsey Theorem
$K(s,t)$ always exists. 
Determining $R(s,t)$ is notoriously different.

There is also a variant with multiple states called *Multicolor Ramsey Theory* $R(s,t,r), R(n_{1},n_{2},\dots, n_{k})$

## Graph theory
A *graph* $G = (V,E)$ is a piar, where $V$ is a set, and $E \subseteq \text{2-element subsets of } V$.
- Elements in $V$ are *vertices* of G
- Elements in $E$ are *edges* of G
- $G$ is *finite* if $|V|$ is finite
- Two vertices $x,y \in V$ are adjacent in $G$ if $\{ x,y \} \in E$, but more used notation is $xy \in E$ or $yx \in E$ 
- The usual way to picture a graph use dots to represent vertices and lines to represent edges. Just how dots and lines are drawn are irrelevant.
$$
\begin{align}
G = (V,E), V = {a,b,c,d,e} \\
E = \{ \{ a,b \}, \{ b,c \}, \{ c,d \}, \{ a,e \} \}
\end{align}
$$

For each $v \in V$, $N(v) := \{ u \in V, \{ u,v \} \in E \}$
Called neighborhood of $v \to$ degree of $v = d(v) = |N(v)|$

$K_{n}$: the complete graph on $n$ vertices