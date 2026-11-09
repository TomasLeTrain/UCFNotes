Last lecture finished 6.4 - permutations with forbidden positions

# 6.5 - Another forbidden position problem
Suppose a class of eight boys takes a walk every day. The students walk in a line of 8 so that every boy except the 1st one is preceded by another. In order that a boy not see the same person in front of him, on the 2nd day the students decide to switch positions so that no boy is peceeded by the same boy who preceeded him on the 1st day, In how many ways can they switch positions?

Define $Q_{n} =$ \# of permutations of $[n]$ such that the pairs $12,23,\dots,(n-1)n$ are forbidden. 

Define property $A_{1}$ be that the sequence has $12$
Define property $A_{2}$ be that the sequence has $23$
...
Define property $A_{n-1}$ be that the sequence has $(n-1)n$

So, we are looking for $|\bar{A_{1}} \cap \bar{A_{2}} \cap \dots \bar{A_{n-1}}|$. This is special case of IEP:
$$
\begin{align}
|\bar{A_{1}} \cap \bar{A_{2}} \cap \dots \bar{A_{n-1}}| = \alpha_{0} - \alpha_{1} \binom{n-1}{1} + \alpha_{2} \binom{n-1}{2} + \dots (-1)^{n-1} \alpha_{n-1} \binom{n-1}{n-1}
\end{align}
$$
Where $S = \{\text{permutations of } [n]\}$

For each $i \in [n-1], A_{i} = \{ \text{\# permutations of } [n] \text{ such that } i(i=1) \text{ occurs in the permutations} \}$

Same problem has placing A and $B$ in a row to guarantee they end up together, so:
$$
\begin{align}
\alpha_{0} = |S| = n! \\
\alpha_{1} = |A_{1}| = (n-1)! \\
\alpha_{2} = |A_{1} \cap A_{2}| = (n-2)! \\
\dots
\alpha_{n-1} = |A_{1} \cap A_{2} \cap \dots \cap A_{n-1}| = (n-(n-1))! \\
\end{align}
$$

*Remark:* $|A_{1} \cap A_{2}| = |A_{1} \cap A_{3}|$, but the reason is completely different! Consider $|A_{1} \cap A_{2}|$, its the number of permutations of the set $\{ 123,4,\dots,n \}$, However $|A_{1} \cap A_{3}|$ is the \# of permutations of the set $\{ 12,34,5,\dots,n \}$, which is different! The result ends up being the same however so can still use special case of IEP.

So by IEP:
$$
\begin{align}
|\bar{A_{1}} \cap \bar{A_{2}} \cap \dots \bar{A_{n-1}}| = n! - \binom{n-1}{1}(n-1)! \binom{n-2}{2}(n-2)! + \dots + (-1)^{n-1} \binom{n-1}{n-1}1! \\
= (n-1)! \left( n- \frac{n-1}{!} + \frac{n-2}{2} - \frac{n-3}{3} + \dots + \frac{(-1)^{n-1}}{(n-1)!} \right)
\end{align}
$$
The following is a homework problem:
$Q_{n} = D_{n} + D_{n-1}, \forall n \geq 2$

# Chapter 7 - Recurrance relations & Generating Functions
Many combinatorial counting problems depend on an integer $n$. This parameter $n$ often denotes the size of some underlying set or multiset in the problem, the size of subsets, the \# positions in permutations, and so on. Then, a counting problem is often not one individual problem, but a sequence of individual problems.

## Example 1
$h_{n} =$ \# permutations of $[n]$, then:
$$
\begin{align}
h_{0} = 0! \\
h_{1} = 1! \\
h_{2} = 2! \\
\dots \\
h_{n} = n! \\
\dots \\
\to \text{infinite sequence: } \{ h_{n} \}_{n=0}^{\infty}
\end{align}
$$
It can then be seen that $h_{n} = n * h_{n-1}, \forall n \geq 1$

## Example 2
For $n \geq 1,$ $g_{n}$ = \# non-negative integral solutions to 
$$
\begin{align}
x_{1} + x_{2} + \dots + x_{2026} = n, \\
x_{1} \geq 0, x_{2} \geq 0, \dots, x_{n} \geq 0 \\
\end{align}
$$
This is also an infinite sequence $\left\{ g_{n} = \binom{n + 2025}{n} \right\}_{n=1}^{\infty}$

**Goal:** We develop algebraic methods for solving some counting problems for an integer parameter $n$. Our methods lead either to an explicit formula or to a generating function, The coefficient of whose power series give the answers to the counting problem.

# 7.1 - Some Number Sequences

Let $a_{0},a_{1},\dots,a_{n},\dots$ or $\{ a_{n} \}_{n=0}^{\infty}$ Be a sequence of numbers.
We call $a_{n}$ the general term of the sequence, $S_{n} = a_{0} + a_{1} + \dots + a_{n} = n^{\text{th}} \text{partial form}$.

## Types of special sequences
**Arithmetic sequence**
$a_{n} - a_{n-1} = d, \forall n \geq 1$, for some constant $d$.
Then
$$
\begin{align}
a_{n}-a_{n-1} = d \\
a_{n-1} - a_{n-2} = d \\
\dots \\
a_{2} - a_{1} = d \\
a_{1} - a_{0} = d
\end{align}
$$
Adding them all up gives
$$
\begin{align}
dn = (a_{n} - \cancel{ a_{n-1} }) + (\cancel{ a_{n-1} } - \cancel{ a_{n-2} }) + \dots + (\cancel{ a_{1} } - a_{0}) = a_{n} - a_{0} \\
\boxed{ \to a_{n} = dn + a_{0}, \forall n \geq 1 }
\end{align}
$$

**Geometric Sequence**

$$
\begin{align}
\frac{a_{n}}{a_{n-1}} = d, \forall n \geq 1, d \text{ is some constant}
\to \\
a_{n} = \underbrace{ \frac{a_{n}}{a_{n-1}} * \frac{a_{n-2}}{a_{n-1}} * \dots * \frac{a_{2}}{a_{1}} * \frac{a_{1}}{a_{0}} * a_{0} }_{ n \text{ copies} } = \underbrace{ d * d * \dots * d }_{ n \text{ copies} } * a_{0} \\
\to a_{n} = d^{n} * a_{0}, \forall n \geq 1 \\
\to \text{which also means} \\
\to a_{n} = d^{n-1} * a_{1}, \forall n \geq 2 \text{ if } \{ a_{n} \}_{n=1}^{\infty}
\end{align}
$$


## Fibonnaci sequence
A newly born pair of rabbits of opposite sexes is placed into an enclosure at the beginning of the year. Beginning with the second month, the female gives birth to a pair of rabbits of opposite sexes each month. Each new pair also gives birth to a pair of rabbits each month starting with their second month. Determine the \# of pairs of rabbits in the enclosure after one year.
**Solution:**
$$
\begin{align}
f_{n} = \text{\# pairs of rabbits at the beginning of month n (end of month) }  n-1 \\
f_{n} = \text{\# pairs at the beginning of month } n-1 + \text{\# newly born pairs during the month } n-1 \\
f_{n} = f_{n-1} + f_{n-2} ,\forall n \geq 2 \\
\end{align}
$$

**Question:** How to determine $f_{n}$?
**Recall:** 
$f_{n} - f_{n-1} - f_{n-2} = 0$
We are looking for a solution of the form $f_{n} = q^{n}$, where $q$ is a non-zero constant
Then,
$$
\begin{align}
q^{n} - q^{n-1} - q^{n-2} = 0 \\
q^{n-2}(q^{2} - q-1) = 0 \\
\implies q^{2}-q-1= \text{ because } q^{n-2} \neq 0 \\
q=\frac{1\pm \sqrt{ 5 }}{2}
\end{align}
$$

Then, $f_{n} = c_{1} \left( \frac{1+\sqrt{ 5 }}{2} \right)^{n} + c_{2} \left( \frac{1 - \sqrt{ 5 }}{2} \right)^{n}$ 

Where $c_{1}$ and $c_{2}$ are constants. To find these constants we use the initial constants:
$$
\begin{align}
0 = f_{0} = c_{1} + c_{2} \\
1 = f_{1} = c_{1} * \left( \frac{1 + \sqrt{ 5 }}{2} \right)^{1} + c_{2} \left( \frac{1 - \sqrt{ 5 }}{2} \right) ^{1} \\
\implies c_{1} = \frac{1}{\sqrt{ 5 }}, x_{2} = -\frac{1}{\sqrt{ 5 }} \\
\boxed{ \implies f_{n} = \frac{1}{\sqrt{ 5 }}\left( \frac{1-\sqrt{ 5 }}{2} \right) ^{n} - \frac{1}{\sqrt{ 5 }}\left( \frac{1-\sqrt{ 5 }}{2} \right) ^{n}  \forall n \geq 0 }
\end{align}
$$

$$
\begin{align}
h_{n} = h_{n-1} + h_{n-2} \forall n \geq 3
\end{align}
$$


