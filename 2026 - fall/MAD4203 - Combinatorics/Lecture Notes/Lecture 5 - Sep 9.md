
# Quick Review
$$
\begin{align}
M = \{ n_{1} a_{1} , \dots, n_{k} a_{k} \} \\
n = n_{1} + \dots + n_{k} \\
r \leq \min \{ n_{1} , \dots, n_{k} \} \\
\text{\# $r$-permutations of } M = \underbrace{ k * k * \dots * k }_{ \text{$r$ times} } = k^{r} \\
\text{\# permutations of } M = \frac{n!}{n_{1}!\dots n_{k}!}
\end{align}
$$

## Example
$$
\begin{align}
M = \{ 3 * a, 4 * b, 5 * c \} \\ \\

\end{align}
$$
### Answer
$$
\begin{align}
n > r = 11 > \min\{ 3,4,5 \} \\
M_{a} = \{ 2 * a, 4 * b, 5 * c \} \\
M_{b} = \{ 3 * a, 3 * b, 5 * c \} \\
M_{c} = \{ 3 * a, 4 * b, 4 * c \} \\
\end{align}
$$
Therefore the answer is
$$
\begin{align}
\boxed{ \frac{11!}{2!4!5!} + \frac{11!}{3!3!5!} + \frac{11!}{3!4!4!} }
\end{align}
$$

## Multiset Combinations
$$
\begin{align}
M = \{ n_{1} * a_{1}, n_{2} * a_{2}, \dots, n_{k} * a_{k} \} \\
r \leq \min \{ n_{1} ,\dots , n_{k} \} \\
n = n_{1} + \dots + n_{k} \\
\end{align}
$$
\# $r$-combinations of $M$ = \# non--integral solutions to $x_{1} + \dots + x_{k} = r, x_{i} \geq 0 =$

$$
\begin{align}
\text{\# permutations of } M = \{ r * \star, (k-1) * 1 \} \\ \\
= \binom{r+k-1}{r} = \binom{r+k-1}{k-1}
\end{align}
$$


## Example

8 varieties of bagels
Box of dozen bagles (12 bagels)

$$
\begin{align}
M = \{ a * \infty, b * \infty, \dots \}
\end{align}
$$

Define $x_{i}$ = \# bagels of type $i$

$$
\begin{align} \\
x_{1} + x_{2} + \dots + x_{8} = 12 \to \\
\binom{12+8-1}{8}
\end{align}
$$

## Example
What is the \# of non-dereasing sequences of length $r$, whose terms are taken from $1,\dots,k$ (multiple allowed, multiset)?
### Answer without the first condition
\# $r$-permutations of $M = \{  \infty * 1, \dots, \infty * k \}$ is $k_{r}$

### Answer
Let $M = \{ \infty * 1, \dots, \infty*k \}$

Then we can construct a non-de reasing sequenes as follows:
1. Select $r$ numbers from $M$
2. Arrrange the $r$ chosen \#'s into a non-decreasing order

By the multiplication principle, \# of non-decreasing sequences is 
\# ways to carry out step (1) * \# ways to carry out step (2)

There is only 1 way to carry out step (2): all distinct elements have one order compared to the others, the order of equal elements don't matter since its multiset

The \# ways to carry out step (1) is the \# of $r$-combinations of $M$, therefore the answer is:
$$
\begin{align}
\boxed{ \binom{r+k-1}{r} * 1 }
\end{align}
$$

## Example
Find the \# non-negative integral solution to
$$

\begin{align}
\left\{ \begin{array}{r}
x_{1}+x_{2}+\dots+x_{k} = 100\\
x_{1} \leq 5, x_{2} \geq 0, \dots, x_{20} \geq 0
\end{array} \right.
\end{align}
$$

### Answer
\# non-negative integrals solution to 
$x_{1}+ \dots + x_{20} = 100$
$x_{1} \geq  0 , x_{2}\geq 0, \dots , x_{20} \geq 0$

**minus**
\# non-negative integral solutions to 
$$
\begin{align}
x_{1}+\dots+x_{k} = 100 \\
x_{1} \geq 6, x_{2}\geq 0, \dots , x_{20} \geq 0
\end{align}
$$

Therefore, the answer is
$$
\begin{align}
\boxed{ = \binom{100+20-1}{100} - \binom{(100-6) + 20 - 1}{100 - 6} }
\end{align}
$$

# Chapter 3 - The pidgeonhole Principle
This is an *important but elementary* combinatorial principle that can be used to solve a variety of interesting problem.

## PP (Simple form)
If $n+1$ or more objects are placed into $n$ boxes, thne same box msut contain at least two of the same object.
### Proof
Suppose each box contains at most one of the objects. Then we have at most $n$ objects in total, a contradiction $\square$.

*Remark 1:* Neither the statement nor the proof gives any help in finding which box contains two or more of the objects.
### Example
There are $n$ couples. How many of the $2n$ people must be chosen to guarantee that a couple is selected

#### Answer
$n+1$, by pidgeonhole principle 

*Remark 2:* If $n$ objects are plaecd into $n$ boxes and no box is empty, then each box contains exactly one object

*Remark 3:* If $n$ objects are placed into $n$ boxes adn no box contains two or more of the objects, then each box contains exactly one object.



*Remark 4:*
Let $X$,  $Y$ be sets and $f: X \to Y$
- a. If $|X| > |Y|$, then $f$ is not 1-1
- b. If $|X| = |Y|$ and $f$ is onto, then $f$ must be 1-1 (also meaning $f$ is a bijection).
- c. If $|X| = |Y|$ and $f$ is 1-1, then $f$ must also be onto (also meaning $f$ is a bijection).

## Example
Prove that given any 2026 integers $a_{1},\dots,a_{2026} \in \mathbb{Z}$.
$$
\begin{align}
i \neq j,  2025 \mid a_{i} - a_{j} \\
a_{i} - a_{j} \text{is divisible by} 2025
\end{align}
$$

To apply *PP* we must know the pidgeons and boxes.

**Boxes:** There are at most $2025$ different remainders after dividing by $2025$:
$$
\begin{align}
0,1,\dots,2024
\end{align}
$$
**Pidgeons:** We want to place all $a_{i} - a_{j}$ into all the possible remainders (except 0).


$$
\begin{align}
r_{1} = a_{1} \mod 2025 \to \\
a_{1} = c_{1} 2025 + r_{1} \\
a_{2} = c_{2} 2025 + r_{2} \\
\dots \\
a_{2026} = c_{2026} 2025 + r_{2026} \\
\end{align}
$$

$r_{i} \in \{ 0,1,\dots,2024 \}$ For any $i$.
$r_{i},\dots,r_{2026}$ pidgeons
Therefore, $r_{i} = r_{j}, i \neq j$

Then 
$$
\begin{align}
a_{i} - a_{j} = c_{i} * 2025 + r_{i} - (c_{j} * 2025 + r_{j}) \\
= (c_{i} - c_{j}) * 2025 + 0
\end{align}
$$
so  $2025 | a_{i} - a_{j}$, as desired $\square$.
