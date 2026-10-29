# 6.2 - Combination of Repetitions
Recall the stars and bars principle:
$$
\begin{align}
M = \{ n_{1} * a_{1}, n_{2} * a_{2}, \dots, n_{k}*a_{k}  \}
\end{align}
$$
If $r \leq min \{ n_{1},\dots,n_{k} \}$, then \# r-combiations of $M = \binom{r+k-1}{r} = \binom{r+k-1}{k-1}$.
This also equals the \# of non-negative integral solutions to
$$
\begin{align}
x_{1} + x_{2} + \dots + x_{k} = r \\
x_{1} \geq 0, \dots, x_{k} \geq 0
\end{align}
$$
General case:
$$
\begin{align}
x_{1} + x_{2} + \dots + x_{k} = r \\
x_{1} \geq r_{1}, \dots, x_{k} \geq r_{k}
\end{align}
$$
\# non-negative integral solutions: $\binom{(r-r_{1}-\dots-r_{k}) + k-1}{k-1}$

We will use IEP to find r-combinations of $M$ without any restrictions and repetition numbers $n_{1},\dots,n_{k}$.

## Example 1
*FInd \# 9-combinations of $M = \{ 3 * a, 4 * b, 5 * c \}$*
**Solution:**
Define $x_{1} :=$ \# of a's
Define $x_{2} :=$ \# of b's
Define $x_{3} :=$ \# of c's

Thus,
$$
\begin{align}
x_{1} + x_{2} + x_{3} = 9 \\
\underbrace{ 0 \leq x_{1} \leq 3 }_{ A_{1} }, \underbrace{ 0 \leq x_{2} \leq 4 }_{ A_{2} }, \underbrace{ 0 \leq x_{3} \leq 5 }_{ A_{3} }
\end{align}
$$
and the \# of non-integral solutions to this equation equals the answer we are looking for.

Let $A_{1}$ be the set of non-integral solutions to the equation
$$
\begin{align}
x_{1} +x_{2} + x_{3} = 9 \\
x_{1} \geq 4, x_{2} \geq 0,x_{3} \geq 0
\end{align}
$$

Let $A_{2}$ be the set of non-integral solutions to the equation
$$
\begin{align}
x_{1} +x_{2} + x_{3} = 9 \\
x_{1} \geq 0, x_{2} \geq 5, x_{3} \geq 0
\end{align}
$$
Let $A_{3}$ be the set of non-integral solutions to the equation
$$
\begin{align}
x_{1} +x_{2} + x_{3} = 9 \\
x_{1} \geq 0, x_{2} \geq 0, x_{3} \geq 6
\end{align}
$$
Then, $S$ is
$$
\begin{align}
x_{1} +x_{2} + x_{3} = 9 \\
x_{1} \geq 0, x_{2} \geq 0, x_{3} \geq 0
\end{align}
$$

The desired answer thus becomes
$$
\begin{align} \\
|\bar{A_{1}} \cap \bar{A_{2}} \cap \bar{A_{3}}|
\end{align}
$$

Computing each of the sets:
$$
\begin{align}
|S| = \binom{9+3-1}{3-1} = \binom{11}{2} \\
|A_{1}| = \binom{(9-4) + (3-1)}{3-1} = \binom{7}{2} \\
|A_{2}| = \binom{(9-5) + 2}{2} = \binom{6}{2} \\
|A_{3}| = \binom{(9-6) + 2}{2} = \binom{5}{2} \\
|A_{1} \cap A_{2}| = \binom{0 + 2}{2} =  1 \\
|A_{1} \cap A_{3}| = 0 \\
|A_{2} \cap A_{3}| = 0 \\
|A_{1} \cap A_{2} \cap A_{3}| = 0 \\
\end{align}
$$

By IEP,
$$
\begin{align}
|\bar{A_{1}} \cap \bar{A_{2}} \cap \bar{A_{3}}| \\
= |S| - \sum |A_{i}| + \sum |A_{i} \cap A_{j}| - |A_{1} \cap A_{2} \cap A_{3}| \\
\boxed{ = \binom{11}{2} - \left(\binom{7}{2} + \binom{6}{2} + \binom{5}{2}\right) + \binom{2}{2} }
\end{align}
$$

## Example 2
Find the \# of non-negative integral solutions of the equation 
$$
\begin{align}
x_{1} + x_{2} + x_{3} +x_{4} = 18 \\
1 \leq x_{1} \leq 5, -2 \leq x_{2} \leq 4, 0 \leq x_{3} \leq 5, 3 \leq x_{4} \leq 9
\end{align}
$$
**Solution:**
Let $y_{1} = x_{1} - 1, y_{2} = x_{2} + 2, y_{3} = x_{3},  y_{4} = x_{4} - 3$, then
$$
\begin{align}
y_{1} + y_{2} + y_{3} + y_{4} = (x_{1} - 1) + (x_{2} + 2) + x_{3} + (x_{4} - 3) \\
= x_{1} + x_{2} +x_{3} +x_{4} - 2 \\
= 18 - 2 = 16
\end{align}
$$
So,
$$
\begin{align}
y_{1} + y_{2} + y_{3} + y_{4} = 16 \\
0 \leq y_{1}  \leq 4, 0 \leq x_{2} \leq 6, 0 \leq x_{3} \leq 5, 0 \leq x_{4} \leq 6
\end{align}
$$
The \# of solutions to star (equation above)
$$
\begin{align}
= |\bar{A_{1}} \cap \bar{A_{2}} \cap \bar{A_{3}} \cap \bar{A_{4}}| \\
= |S| - \sum |A_{i}| + \sum |A_{i} \cap A_{j}| - \sum |A_{i} \cap A_{j} \cap A_{k}| + |A_{1} \cap A_{2} \cap A_{3} \cap A_{4}|
\end{align}
$$

Where $S$ is integral solutions to equation:
$$
\begin{align}
y_{1} + y_{2} + y_{3} + y_{4} = 16 \\
y_{1} \geq 0, y_{2} \geq 0, y_{3} \geq 0, y_{4} \geq 0
\end{align}
$$
$A_{1}$ is \# integral solutions to:
$$
\begin{align}
y_{1} + y_{2} + y_{3} + y_{4} = 16 \\
y_{1} \geq 5, y_{2} \geq 0, y_{3} \geq 0, y_{4} \geq 0
\end{align}
$$
$A_{2}$ is \# integral solutions to:
$$
\begin{align}
y_{1} + y_{2} + y_{3} + y_{4} = 16 \\
y_{1} \geq 0, y_{2} \geq 7, y_{3} \geq 0, y_{4} \geq 0
\end{align}
$$
$A_{3}$ is \# integral solutions to:
$$
\begin{align}
y_{1} + y_{2} + y_{3} + y_{4} = 16 \\
y_{1} \geq 0, y_{2} \geq 0, y_{3} \geq 6, y_{4} \geq 0
\end{align}
$$

$A_{4}$ is \# integral solutions to:
$$
\begin{align}
y_{1} + y_{2} + y_{3} + y_{4} = 16 \\
y_{1} \geq 0, y_{2} \geq 0, y_{3} \geq 0, y_{4} \geq 7
\end{align}
$$

# 6.3 - Derangements
**Question:**
*At a party, 10 gentlemen cehck their hats. In how many ways can their hats be returned so that no gentleman gets their that back?*

Given an n-element set $X$ in which each element has a specified location, and we are asked to find the \# of permutation of $X$ in which no element is in its specified position. Snice the actual objects in $X$ is irrelevant, we always use $x = [n] = \{ 1,\dots,n \}$

> [!definition] Derangement
> A **Derangement** of $[n]$ is a  permutation $i_{1},i_{2},\dots,i_{n}$ such that $i_{1} \neq 1, i_{2} = \neq, \dots, i_{n} \neq n$.
> Notation: $D_{n}$ = \# derangements of $[n]$

Cases:
$D_{1} = 0$, since only permutation is $\{ 1 \}$
$D_{2} = 1$, since the permutation $\{ 2,1 \}$ is the only one that is not the natural order
$D_{3} = 2$ $\{ 3,1,2 \}, \{ 2,3,1 \}$
$D_{4} = 9, \dots$

We will use IEP to deduce a formula for $D_{n}$
$S = \{  \text{permutations of } [n] \}$, For each $k \in [n]$
$A_{k} = \{  \text{permutations of [n] suh that k is in its natural position} \}$
Then $D_{n} = |\bar{A_{1}} \cap \bar{A_{2}} \cap \dots \cap \bar{A_{n}}|$
This is a special case of IEP:
$$
\begin{align}
D_{n} = \alpha_{0} - \binom{n}{1} \alpha_{1} + \binom{n}{2} \alpha_{2} + \dots + (-1)^{n}\binom{n}{n}\alpha_{n}
\end{align}
$$
$$
\begin{align}
\alpha_{0} = |S| = n! \\
\alpha_{1} = |A_{1}| = (n-1)! \\
\alpha_{2} = |A_{1} \cap A_{2}| = (n-2)! \\ \\
\dots
\alpha_{n} = (n-n)! = 1 \\ \\
\end{align}
$$

So,

$$
\begin{align}
D_{n} = n! - \binom{n}{1}(n-1)! + \binom{n}{2}(n-2)! + \dots + (-1)^{n}\binom{n}{n}(n-n)! \\
D_{n} = n! - \frac{n! \cancel{ (n-1)! }}{1!\cancel{ (n-1)! }} + \frac{n! \cancel{ (n-2)! }}{2!\cancel{ (n-2)! }} + \dots + (-1)^{n} \frac{n!\cancel{ (n-n)! }}{n!\cancel{ (n-n)! }} \\
D_{n} = n! - \frac{n!}{1!} +\frac{n!}{2!} + \dots + (-1)^{n}\frac{n!}{n!} \\
D_{n} = n! \left( 1 - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \dots + (-1)^{n} \frac{1}{n!} \right)
\end{align}
$$

Recall:
$$
\begin{align}
e^{x} = \sum_{n=0}^{\infty} \frac{x^{n}}{n!}
\end{align}
$$
Let $x = -1 \to$
$$
\begin{align}
\frac{1}{e} = e^{-1} = \left(  1 - \frac{1}{1!} + \frac{1}{2!} + \dots \right) + \underbrace{ \dots }_{ \text{remainder} }
\end{align}
$$
So,
$$
\begin{align}
\boxed{ D_{n} \approx \frac{n!}{e} \text{ or } e \approx \frac{n!}{D_{n}} }
\end{align}
$$