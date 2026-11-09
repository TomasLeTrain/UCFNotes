# 7.4 - Generating Functions
**Recall:**
Taylor series: $\{ a_{n} \}_{n=0}^{\infty}$
Power series: $a_{0} + a_{1}x + \dots + a_{n}x^{n} = \sum_{n=0}^{\infty}a_{n}x^{n}$

Given $f(x)$, differentiable for all $n \geq 1$, its Taylor series at $x=a$:
$$
\begin{align}
f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!}(x-a)^{n}, x \in \text{Interval of Convergence}
\end{align}
$$


Given $\{ h_{n} \}_{n=0}^{\infty}$, the generating function with respect to the sequence is 
$$
\begin{align}
g(x) = \sum_{n=0}^{\infty} h_{n}x^{n} 
\end{align}
$$
**Fact:** $h_{n}$ is the answer to your counting problem is now the coefficient of $x_{n}$ in $g(x)$.
## Examples
*Determine the generating functions for the following sequences:*
### 1
$\{ h_{n} = a \}_{n=0}^{\infty}, a \in \mathbb{R}$
**Ans:**

$$
\begin{align}
g(x) = \sum_{n=0}^{\infty} h_{n}x^{n} = \sum_{n=0}^{\infty} a x^{n} = a \sum_{n=0}^{\infty} x^{n} \\
= \frac{a}{1-x} \text{ if } |x| < 1
\end{align}
$$
### 2
$$
\begin{align}
h_{n} = \left\{ h_{n} = \binom{\alpha}{n} \right\} _{n=0}^{\infty}, \alpha \text{ in } \mathbb{R} \\
\end{align}
$$
**Ans:**
$$
\begin{align}
g(x) = \sum_{n=0}^{\infty} h_{n}x^{n} \\
= \sum_{n=0}^{\infty} \binom{\alpha}{n}x^{n} \\
= (1 + x)^{\alpha}
\end{align}
$$

### 3
$$
\begin{align}
\left\{ h_{n} = \binom{-k}{n} \right\} _{n=0}^{\infty}, k \in \mathbb{Z}^{+}
\end{align}
$$
**Ans:**
$$
\begin{align}
g(x) = \sum_{n=0}^{\infty}  h_{n}x^{n} \\
= \sum_{n=0}^{\infty}  \binom{-k}{n}x^{n} \\
\boxed{ = (1+x)^{-k} = \frac{1}{(1+x)^{k}} } \\
\end{align}
$$
can also see that
$$
\begin{align}
= \sum_{n=0}^{\infty}  \frac{-k (-k-1)(-k-2)\dots(-k+n-1)}{n!}  x^{n} \\
= \sum_{n=0}^{\infty} (-1)^{n}  \frac{k (k+1)(k+2)\dots(k-n+1)}{n!}  x^{n} \\ \\
= \sum_{n=0}^{\infty} (-1)^{n} \binom{n+k-1}{n} x^{n} \\ \\ \\
\end{align}
$$

### 4
$h_{n}$ is the non-negative integral solution to 
$$
\begin{align}
x_{1} + \dots + x_{k} = n \\
x_{1}\geq_{0}, \dots, x_{k}\geq_{0}
\end{align}
$$
**Ans:**
$$
\begin{align}
h_{n} = \binom{n+k-1}{n} \\
g(x) = \sum_{n=0}^{\infty} \binom{n+k-1}{n} x^{n}  \\
= \sum_{n=0}^{\infty} (-1)^{n} \binom{-k}{n}x^{n} \\
\implies \binom{n+k-1}{n}=(-1)^{n}\binom{-k}{n}
\end{align}
$$
So
$$
\begin{align}
= \sum_{n=0}^{\infty} \binom{-k}{n}(-x)^{n} \\
=(1-x)^{-k} = \frac{1}{(1-x)^{k}}
\end{align}
$$

### 5
Can now use the generating function method to solve more advanced counting problems

**Question:** *Determine the generating unction for the \# of $n$-combinations of apples, bananas, oranges and pairs, where in each $n$-combinations, the \# of apples is even. \# bananas is odd, \# oranges is between 0 and 4, and at least one pear.*

**Recall:** prpoerties of polynomial functions:
$$
\begin{align}
x^{n}*x^{m} = x^{n+m}
\end{align}
$$

$$
\begin{align}
n_{a} + n_{b} + n_{o} + n_{p} = n \\
\implies \\
x_{n_{a}} * x^{n_{b}} * x^{n_{o}} * x^{n_{p}} = x^{n_{a}+n_{b}+n_{o}+n_{p}} = x^{n}
\end{align}
$$

Thus, can find the individual generating function then multiply them together to get teh final result

Generating functions:
$$
\begin{align}
g_{a}(x) = x^{0} + x^{2} + x^{4} + x^{6} + \dots = \frac{1}{1-x^{2}} \\
g_{b}(x) = x^{1} + x^{3} + x^{5} + \dots = \frac{x}{1-x^{2}} \\
g_{o}(x) = x^{0} + x^{1} + x^{2} + x^{3} + x^{4} = \frac{1-x^{5}}{1-x} \\
g_{p}(x) = x^{1} + x^{2} + x^{3}  + \dots = \frac{x}{1-x}
\end{align}
$$

Then, the generating function is: 
$$
\begin{align}
g(x) = \sum_{n=0}^{\infty} h_{n}x^{n} = g_{a}(x) + g_{b}(x) + g_{o}(x) + g_{p}(x) \\
\boxed{ = \frac{1}{1-x^{2}} * \frac{x}{1-x^{2}} * \frac{1-x^{5}}{1-x} * \frac{x}{1-x} }
\end{align}
$$

### 6
*Find the \# $h_{n}$ of bags of fruit that can be made out of apples, bananas, oranges, pears, where ine ach bag, \# apples is even, \# bananas is a multiple of 5, \# oranges $\leq 4$, and \# pears is 0 or 1.*
$$
\begin{align}
g(x) = (x^{0} + x^{2} + x^{4} + \dots)*   \leftarrow \text{apples} \\
(x^{0} + x^{1*5} + x^{2*5} + \dots)*   \leftarrow \text{bananas} \\
(x^{0}+x^{1}+x^{2}+x^{3}+x^{4})*   \leftarrow \text{oranges} \\
(x^{0}+x^{1})*   \leftarrow \text{pairs} \\ \\
= \frac{1}{\cancel{ 1-x^{2} }} * \frac{1}{\cancel{ 1-x^{5} }} * \frac{\cancel{ 1-x^{5} }}{1-x} * \frac{\cancel{ 1-x^{2} }}{1-x} \\
= \frac{1}{(1-x)^{2}} = \sum_{n=0}^{\infty} \binom{n+2-1}{n}x^{n} \\
\implies h_{n} = \text{coeff } x^{n} \text{ in } g(x) \\
\boxed{ = \binom{n+2-1}{n} = \binom{n+1}{1} = n+1 }
\end{align}
$$

### 7
*Determine $h_{n}$, where $h_{n}$ = \# non-negative integral solutions to*
$$
\begin{align}
x_{1}+\dots+x_{k} = n \\
\text{each } x_{i} \text{ is odd}
\end{align}
$$

**Ans:**
$$
\begin{align}
g_{i}(x) = x^{1} + x^{3} + x^{5} +\dots = x(x^{0} + x^{2} + x^{4} + \dots) = \frac{x}{1-x^{2}}
\end{align}
$$
Thus
$$
\begin{align}
g(x) = \left( \frac{x}{1-x^{2}} \right)^{k} = \frac{x^{k}}{(1-x^{2})^{k}} = x^{k} * \frac{1}{(1-x^{2})^{k}} \\
= x^{k} \sum_{m=0}^{\infty}  \binom{m+k-1}{m}(x^{2})^{m} \\ \\
= \sum_{n=0}^{\infty} \binom{m+k-1}{m}  x^{2m+k} \\
n = 2m+k \to n - k = 2m
\end{align}
$$
$h_{n}$ = coeff of $x^{n}$ in $g(x)$
$$
\begin{align}
h_{n} = \left\{\begin{array}{cc}
0 & \text{if } n-k \text{ is odd}
\binom{\frac{n-k}{2} + k -1}{k-1} & \text{if } n-k \text{ is even}
\end{array}\right.
\end{align}
$$

### 8
*Let $h_{n}$ denote the \# solutions to* 
$$
\begin{align}
x_{1} + 3x_{2} + 5 x_{3} + 7x_{4} = n \\
x_{1} \geq 0, x_{2} \geq 0, x_{3} \geq 0, x_{4} \geq 0
\end{align}
$$
*Determine the generating function for*
$$
\begin{align}
\{ h_{n} \}_{n=0}^{\infty}
\end{align}
$$
