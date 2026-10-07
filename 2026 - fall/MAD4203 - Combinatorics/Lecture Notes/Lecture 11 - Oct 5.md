## Continuation from last lecture

$$
\begin{align}
\binom{\alpha}{k} = \left\{\begin{array}{cc}
\frac{\alpha(\alpha-1)\dots(\alpha-k+1)}{k!} & k \geq 1 \\
1  & k = 0 \\
0 & k < 0
\end{array}\right.
\end{align}
$$

$$
\begin{align}
\boxed{ \binom{\alpha}{k} \neq \binom{\alpha}{\alpha-k} }
\end{align}
$$

The bottom must always be integer, and by definition $\alpha - k$ will not be an integer. This means the identity only holds if $\alpha \in \mathbb{Z}$.

# 5.4 - The multinomial Theorem
> [!theorem] The multinomial Theorem
> For positive integers $n$, $x_{1},\dots,x_{k}$, where $t\geq 2$:
> $$
> \begin{align}
> (x_{1} + x_{2} + \dots + x_{t})^{n} = \sum \underbrace{ \binom{n}{n_{1},n_{2},\dots,n_{k}} }_{ \text{multinominal coeff.} } x_{1}^{n_{1}}\  x_{2}^{n_{2}}\  \dots \ x_{t}^{n_{t}} 
> \end{align}
> $$
> where
> $$
> \begin{align}
> \binom{n}{n_{1},n_{2},\dots,n_{t}} = \frac{n!}{n_{1}!n_{2}!\dots n_{t}!}
> \end{align}
> $$
^54cd01

`\begin{proof}`@[[#^54cd01]]
$$
\begin{align}
(x_{1}+\dots x_{t})^{n}= \underbrace{ (x_{1}+\dots+x_{t}) \dots (x_{1}+\dots +x_{t}) }_{ \text{n factors} }
\end{align}
$$

It can be seen that there are $t^{n}$ terms in total (must choose some $x_{i}$ for all $n$ factors).
It can also be seen that the \# of different terms is $\binom{n+t-1}{n}$, since it's the \# of integral solutions to $n_{1} + n_{2} + \dots + n_{t} = n \quad n_{1},n_{2},\dots,n_{t} \geq 0$ (only the amounts of each $x_{i}$ matter to find distinct terms).

So, let's group like terms for all $t^{n}$ terms.

The coefficient of $x_{1}^{n_{1}},x_{2}^{n_{2}},\dots,x_{t}^{n_{t}} =$ \# ways to select $n_{1}$ copies of $x_{1},\dots, n_{t}$ copies of $x_{t}$:
$$
\begin{align}
= \binom{n}{n_{1}} * 1 * \binom{n-n_{1}}{n_{2}}* 1 * \dots* \binom{n-n_{1} - \dots - n_{t-1}}{n_{t}} * 1 \\
\boxed{ = \frac{n!}{n_{1}!n_{2}!\dots n_{t}!} = \binom{n}{n_{1},n_{2},\dots n_{t}} }
\end{align}
$$
`\end{proof}`

## Examples
### 1 
 *$(x_{1} + \dots + x_{5})^{7}$ is expanded*
*A. How many terms are there?*
*B. *How many different terms are there?*
*C. *What is the coeff. of $x_{1}^{2}\ x_{2}\ x_{4}^{3}\ x_{5}$*

#### Solutions
There are $5^{7}$ different terms.
There are $\binom{7+5-1}{5-1} = \binom{11}{4}$ different terms

*Remark:* there is no $x_{3}$ explicitly defined in the question, so it is implicit that the degree of $x_{3}$ is $0$, so the total expression is $x_{1}^{2}\ x_{2}^{1}\ x_{3}^{0}\ x_{4}^{3}\ x_{5}^{1}$.
So, the coefficient is 
$$
\begin{align}
\boxed{ \frac{7!}{2!1!3!1!} = \frac{7!}{2!3!} }
\end{align}
$$


### 2
$(2x_{1} - 3x_{2} + 5x^{3})^{6}$
*a. \# terms*
*b. \# of different terms* 
*c. coeff of $x_{1}^{3}\ x_{2}\ x_{3}^{2}$* 
#### solution
terms: $3^{6}$
different terms: $\binom{6+3-1}{3-1} = \boxed{ \binom{8}{2} }$

For $c$:
$$
\begin{align}
(2x_{1})^{3}(-3x_{2})^{1}(5 x_{3})^{2} \\
= \boxed{ 2^{3} * (-3)* 5^{2} }\ \boxed{  x_{1}^{3}\ x_{2}\ x_{3}^{2} }
\end{align}
$$
So,
$$
\begin{align}
\text{coeff. of}\ x_{1}^{3}\ x_{2}\ x_{3}^{2} = \frac{6!}{3!2!} * (2^{3} (-3)\ 5^{2}) \\
= \boxed{ -6! * 2 * 5^{2} }
\end{align}
$$
*Remark:* The final coefficient will be the multinomial coefficient \* the coefficient from expanding the coefficients of them individually

# 4.5 - Partially Ordered Sets
$a | b$: $a$ is a divisor of $b$, or $b$ is a divisible by $a$. 

So, if we imagine the "operation" of divisibility on all integers, we can conclude the following:
$$
\begin{align}
\mathbb{Z}, | : \forall a,b \in \mathbb{Z}, a | b,  b | a, a \nmid b, b \nmid a 
\end{align}
$$
In other words, for any integers $a,b$, we can see that at least one of the 4 conditions shown must occur

Given a set $S$, $\mathcal{P}(S)$ denotes the powerset of $S$.
$$
\begin{align}
\forall A,B \in \mathcal{P}(S), A \in B, B \in A, A \not\in B, B \not\in A \\
\end{align}
$$

Basically given some "universe" (set in which elements exist), we can find some guarantees about those elements

> [!definition] Binary relation
> A **Binary Relation** on a set $X$ is just a subset $R$ of the cartesian product $X \times X = \{ (x,y) | x \in X, y \in X \}$

^a39303

> [!definition] Comparable and Incomparable
> We say $a,b \in X$ are **comparable** if $(a,b) \in R \text{ or } (b,a) \in R$
> We say $a,b \in X$ are **incomparable** if $(a,b) \not\in R \text{ and } (b,a) \not\in R$
> We write $a\ R\ b$ if $(a,b) \in R$, or in other words, if $a,b$ are comparable.

## Example
let $X = \{ 1,2,3,4,5,6 \}$
Define $R$ to be "$\mid$" the divisibility among integers.
Or $R \subseteq X \times X$ with
$$
\begin{align}
R = \left\{\begin{array}{c}
(1,1) , (1,2) , (1,3) , (1,4) ,  (1,5) , (1,6) \\
(2,2) ,  (2,4), (2,6) \\
(3,3)(3,6), (4,4)(5,5),(6,6) \\
\end{array}\right\}
\end{align}
$$
for example
$3 \mid 6 \Longleftrightarrow$ 3 and 6 are comparable
$3 \nmid 5 \Longleftrightarrow$ 3 and 6 are incomparable

A binary relation $R$ on $X$ is 
- **reflexive** if $\forall x \in X, (x,x) \in R$
- **symmetric** if $(x,y) \in R \implies (y,x) \in R$
- **antisymetric** if $(x,y) \in R$ and $(y,x) \in R \implies x = y$
- **transitive** if $(x,y) \in R$ and $(y,z) \in R \implies (x,z) \in R$

## Example
"$\mid$" on $X = \{  1,2,3,4,5,6 \}$
is reflexive ($x$ divides x),
antisymmetric (if $a | b$ and $b | a$, then $a = b$),
and transitive (if $a |b$ and $b | c$, then $a | c$).

Another exapmle:
$X = \mathcal{P}(S)$, "$\subseteq$" relation on $X$
Then "$\subseteq$" is reflexive, antisymmetric, and transitive

> [!definition] Partial Order
> A binary relation $R$ on a set $X$ is a **partial order** if it is relfexive, antisymmetric, and transitive.

Other definitions we won't cover right now:
**Total order/linear order** if it is reflexive, symmetric, and transitive.

> [!definition] Minimal Element
> Let $R$ be a binary relation on $X$. Then 
> $a \in X$ is a **minimal element** with respect to $R$ if $(b,a) \in R$ implies that $b = a$ that is, there is no element $b \in X$ with $b \neq a$ such that $(b,a) \in R$

### Examples
Minimal elements for divisiblity relation: only 1 (only 1 divides 1, everything else gets divided by 1)

Minimal elements for subset relation: only $\emptyset$ (only $\emptyset \subseteq \emptyset$ and $\forall A \subseteq S, \emptyset \subseteq A$).

> [!definition] Maximal Element
> $a \in X$ is a **maximal element** with respect to $(a,b) \in R$ implies $b = a$, that is, there is not $b \in X$ such that $(a,b) \in r$

Maximal elements for divisibility relation: 4,5,6 (they dont divide anything else)
Maximal elements for subset relation: only whole subset $S$ (it is only a subset of itsel)

