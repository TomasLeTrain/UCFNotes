# Permutations of Multisets
$M = \{ n_{1} a_{1}, n_{2} a_{2}, \dots, n_{k} a_{k} \}$, when $a_{1},\dots, a_{k}$ are distinct, $n_{1}, \dots, n_{k}$are repetition \#'s of $a_{1}, \dots, a_{k}$.
*Remark:* $n_{1},\dots,n_{k}$ can have infinite.

Let $r \in \mathbb{Z}^{+}$ .

An *$r$-permtuation of $M$* is an ordered arrangement of $r$ objects in $M$. 
	When $r = n_{1}$ + ... + n_k, $r$-permutation is called a *permutation of $M$*.

## Example
$M = \{ 3 * a_{1}, 2 * a_{2}, \infty * a_{4} \}$
1. give a 4-permutation of $M$
$a_{1} a_{2}a_{4}a_{1}, a_{4}a_{4}a_{4}a_{4}$
2. 2026- permutation of $M$:
$\underbrace{ a_{4},\dots,a_{4} }_{ \text{2026 copies} }$

## **Derivation**
**Question**: How to detremine \# $r$-permutations of $M$? 

## Theorem 2.4.1
Let $M = \{  n_{1} a_{1}, \dots, n_{k}a_{k} \}$
If $r \leq min \{n_{1},\dots n_{k}\}$, then # $r$-permutations of $M = \underbrace{ k * \dots * k }_{ r \text{ times} } = \boxed{ k^{r} }$

## Theorem 2.4.2
Let $M = \{ n_{1} * a_{1}, \dots, n_{k}a_{k} \}$

And let $n := n_{1} + ... + n_k$. Then \# permutation of $M = \frac{n!}{n_{1}!n_{2}!\dots n_{k}!}$

## Scratch work for proof
Consider trying to first place all $n_{1} * a_{1}$. We have $n$ positions to place them in, so we **choose** where to place them (since copies of the same element are not distnguishable from each other):
$$
\begin{align}
\binom{n}{n_{1}} * 1
\end{align}
$$

After placing them we do the same for $n_{2}*a_{2}$, except now we have $n_{1}$ less spots to fill:
$$
\begin{align}
\binom{n}{n_{1}}  \binom{n-n_{1}}{n_{2}}  \dots
\end{align}
$$

### Proof
We have $n$ positions in a row and each positions is occupied by one of the $n$ objects. We 1st pick the positions for $a_{1}$, and then the positions for $a_{2}$, and so on.

Thus, for each type there are 
$$
\begin{align}
\binom{n-n_{1}-n_{2}-\dots-n_{j-1}}{n_{j}}
\end{align}
$$
ways to place element $j, 1 \leq j \leq k$.

By the multiplication principle the \# permutations of $M =$.

$$
\begin{align}
\binom{n}{n_{1}}\binom{n-n_{1}}{n_{2}}\dots \binom{n-n_{1}-n_{2}-\dots - n_{k-1}}{n_{k}} \\
= \frac{n!}{n_{1}!(n-n_{1})!} \frac{(n-n_{1})!}{n_{2}!(n-n_{1}-n_{2})!} \dots \frac{(n-n_{1}-n_{2}-\dots-n_{k-1})!}{n_{k}!(n-n_{1}n-2-\dots-n_{k})!} \\
= \frac{n!}{n_{1}!\cancel{ (n-n_{1})! }} \frac{\cancel{ (n-n_{1})! }}{n_{2}!\cancel{ (n-n_{1}-n_{2})! }} \dots \frac{\cancel{ (n-n_{1}-n_{2}-\dots-n_{k-1})! }}{n_{k}!(n-n_{1}n-2-\dots-n_{k})!} \\
= \frac{n!}{n_{1}!n_{2}!\dots n_{k}!0!} \\
= \boxed{ \frac{n!}{n_{1}!n_{2}!\dots n_{k}!} }
\end{align}
$$

*Remarks* 
1. When  $k=2$, \# permtuation of $M = \{ n_{1}a_{1},n_{2}a_{2} \}$
$$
\begin{align}
\frac{n!}{n_{1}!n_{2}!} = \binom{n}{n_{1}} = \binom{n}{n_{2}}
\end{align}
$$
**Question:** How many bitstrings of length $n$ are there?
$$
\begin{align}
2^{n}= \text{\# $n$-permutation of } M = \{ \infty * 0, \infty * 1 \}
\end{align}
$$
How many bitstrings of length $n$ with exactly $k$ 1's?
$$
\begin{align}
M = \{ (n-k) * 0, k * 1 \} \\
\to \\
\binom{n}{k} = \text{\# permutations of $M$}.
\end{align}
$$

*Remark 2:* From the proof of [[Lecture 4 - Sep 2#Theorem 2.4.2]]: If we have $n = n_{1} + .. + n_{k}$ distinct objects and put $n_{1}$ of them into Box 1, $n_{2}$ of them nito Box 2, $\dots$ , $m_{k}$ of them into Box $k$ (boxes are distinguishable)

*Remark 3:* If boxes are indistinguishable and $n_1$ is equal to $n_{k}$,, then there are 

*Remark 4:* if $min \{ n_{1},\dots,n_{k} \} < r < n$, no formula is given. But in chapter 7 we will use generating functiosn to solve.

# Combinations of Multiset
$M = \{  n_{1} a_{1}, \dots, n_{k} a_{k} \}, n = n_{1} + \dots + n_{k}$
An $r$-combinaton of $M$ is an unordered selection of $r$ of the objects in $M$.
*Remark:* an $r$-combination of $M$ is an $r$-element *multisubset of $M$*.

$$
\begin{align}
A = \{ x_{1}a_{1} x_{2}a_{2},\dots \} \\
\text{all combinations must satsisfy } \\
\boxed{ 0 \leq 1 \leq r, 0 \leq x_{2} \leq r \dots , 0 \leq x_{k} \leq r }\\
\boxed{ x_{1}+x_{2}+\dots+x_{k} = r }
\end{align}
$$

1. Each $r$-combination of $M$ gives an integral solution to $\square$ .
2. Each integral solution to $\square$ yields an $r$-combination of $M$.

\# $r$-combinations of $M$ = \# of integral solutions to $\square$.

**Question:** How to find all integral solutions?

\# permutations of $M = \{ r * \times, (k-1) *1  \}$

$$
\begin{align}
\boxed{ \binom{r+k-1}{r} }
\end{align}
$$
This is also called the **stars-and-bars principle**.

We will use the stars-and-bars principle to find all integral solutions.

## Theorem 2.5.1
\# $r$-combinations of $M = \{ n_{1} a_{1}, \dots, n_{k} a_{k} \}$ is = \# integral solution to ($\square$).

$$
\begin{align}
\binom{r+k-1}{r}
\end{align}
$$


### Proof
Let $X$ be the set ofintegral solutions to ($\square$) and $Y$ be the set of permutation of $\{ r * \times, (k-1) * 1 \}$

It suffices to find a bijection from $X \to Y$.

For each integral solution $x_{1}, \dots, x_{k}$ to ($\square$):
$$
\begin{align}
\underbrace{ \overbrace{ **\dots* }_{ x_{1} } | \overbrace{ **\dots* }_{ x_{2} } | \dots |   \overbrace{ **\dots* }_{ x_{k} } }_{ k-1 \text{ bars} }
\end{align}
$$

For example consider the examples:
$$
\begin{align}
x_{1}+x_{2}+x_{3} = 5 \quad  x_{1} = 1, x_{2}=3, x_{3}=1\quad \to 
* | *** | * \\
 \\
x_{1}+x_{2}+x_{3} = 5 \quad  x_{1} = 0, x_{2}=0, x_{3}=5\quad \to 
|\ | ****\ * \\
\dots
\end{align}
$$

Convertly, for each permutation of $\{ r *, (k-1) * 1 \}$
let
$$
\begin{align}
x_{1} = \text{\# stars to the left of the 1st bar} \\
x_{2} = \text{\# stars between the 1st and 2nd bars} \\
\vdots \\
x_{k} = \text{\# stars to the right of the (k-1)th bar}
\end{align}
$$
Then $x_{1} + \dots + x_{k} = r, 0 \leq x_{i} \leq r$ for all $i$.
$\square$

#### Remarks
1. \# nonnegative integral solution to $x_{1} + \dots +x_{k} = r = \binom{r + k - 1}{r}$
2. Let
$$
\begin{align}
x_{1}+ \dots + x_{k} = r \\
r_{1} \leq x_{1} \leq r, \dots , r_{k} \leq x_{k} \leq r \\
\text{for some } r_{1},r_{2},\dots r_{k}
\end{align}
$$
Can find the number of solutions by using substitution to turn into the normal form:
$$
\begin{align}
y_{1} = x_{1} - r_{1}, y_{2} = x_{2} - r_{2}, \dots y_{k} = x_{k} - r_{k} \\
\to  \\
y_{1}+y_{2}+\dots+y_{k} = (x_{1} - r_{1}) + (x_{2} - r_{2}) + \dots (x_{k} - r_{k}) \\
= (x_{1}+\dots+x_{k}) - (r_{1} + \dots + r_{k}) \\
 \\
\boxed{ y_{1}+\dots+y_{k} = r - (r_{1} + \dots + r_{k}) } \\
\boxed{ 0 \leq y, 0 \leq y_{2}, \dots, 0 \leq y_{k} }
\end{align}
$$

So the number of solutions becomes:
$$
\begin{align}
\binom{r - (r_{1}+\dots + r_{k}) + k - 1}{r - (r_{1}  + \dots + r_{k})}
\end{align}
$$
3. The conditions from $\square$ *must* hold to use the stars and bars principle. In other words, upper bounds like $x_i < r_{i}$ invalidate the use of the principle. The inclusion-exclusion principle in chapter 6 will be applied 
