# Four basic counting principles
## Addition Principle / rule of sum
If choosing from mutually exclusive options, use addition principle

Example:
if $S$ is partitioned into $S_{1},\dots,S_{m}$:
$$
\begin{align}
|S| = |S_{1}| + |S_{2}| + \dots + |S_{m}|
\end{align}
$$

## Multiplication(Product) principle / Rule of Product
choices made at the same time with each other.

Example:
Let $S$ be a set of ordered pairs $(a,b)$ of objects
$$
\begin{align}
A = \{ \dots \},
B = \{ \dots \}, \\
S = A \times B\\
|S| = |A| * |B|
\end{align}
$$
Equal to cartesian product, basically saying there are $|A|$ number of choices to choose from $A$ and $|B|$ choices to choose from $B$.

## Subtract principle / Rule of subtraction
If $A \subseteq S$ then
$$
\begin{align}
|A| = |S| - |\bar{A}|
\end{align}
$$
## Division principle / Rule of Division
if all partitions are of equal size, the size of each part will be
$$
\begin{align}
k = \frac{|S|}{\text{number of elements per part}}
\end{align}
$$

Special case of addition principle:
$$
\begin{align}
|S| = |S_{1}| + |S_{2}| + \dots + |S_{m}| \\
k = |S_{1}| = |S_{2}| = \dots = |S_{m}| \\
|S| = k * m
\end{align}
$$

**Lecture example:**
How many ways are there to select one person from 6 men, 7 women, 5 girls, and 4 boys?
	*Each category is a partition of the set of people, addition principle*
How many ways are there to select a man, a woman, a girl and a boy from, 6 men, 7 women, 5 girls, and 4 boys?
	*Each choice is individual, multiplication principle*


How many positive  factors of $3^{10} \times {5}^{11}\times {7}^{9} \times 11^{2026}$?
	*Each factor has to include a some power of each base (including zero). Therefore, for each base we choose one number from $[0,n]$, for $n$ being the power in the original number.*
	$11 \times 12 \times 10 \times 2027$

Each password consists of a string of 7 symbols form $0-9$ and $a-z$. How many passwords with repeated symbols?
if we define $A$ as being the set of passwords with repeated symbols:
$$
\begin{align}
|S| = 36^{6} \\
|\bar{A}| = 36 * 35  * 34  * 33 * 32 * 31 = \frac{36!}{30!} \\
|A| = |S| - |\bar{A}| = \boxed{ 36^{6}-\left( \frac{36!}{30!} \right) }
\end{align}
$$


How many different non-empty baskets of fruit are possible if there are 2026 peaches and 6 apples?

$M = \{ 2026  * p, 6 * a \}$
all choices are $7 * 2027$, however there is one case that is empty:
$$
\begin{align}
7*2027 - 1
\end{align}
$$
if both fruits are indistunguishable the set becomes
$$
\begin{align}
S =  \{ p_{1},p_{2},\dots,p_{2026} , a_{1},\dots, a_{6} \} \\
\text{\# nonepmty subsets of $S$: } 2^{|S|} - 1
\end{align}
$$

distinct 5-digit #'s can be constructed from $1,1,1,6,8$:
$$
\begin{align}
\frac{5!}{3!}
\end{align}
$$
**Tip:** make most restrictive choice first

## Types of counting problems
many counting problems of the following types:
1. # of ordered arrangements (permutations)
	a. without repeated objects (sets)
	b. with repetition of objects permitted (multiset).
2. # of unordered arrangements (combinations/subsets)
	a. without repeated objects (sets)
	b. with repetition allowed (multisets)
	

if $|S| = n$, then we call $S$ an **$n$-element set** or a **set of $n$ elements**.

number of ways to place people $S =  \{ a,b,c,d,e\}$  at a table where a refuses to set next to b?


**circular permutation**

**way #1:** we first place $a$. Then, we place to its left (3 choices, no a and no b), same to its right (2 choices). At the end we have two spots left and 2 people left, and we can place them in whichever combination $\binom{2}{2} = 2!$, so the total becomes:
$$
\begin{align}
3 * 2 * 2! = \boxed{ 2 * 3! }
\end{align}
$$
**way #2 - subtraction rule:**
We wcan use subtraction rule to find all the ways they can be placed together, then subtract that from all the total ways.

We can find all the ways to place 4 elements (merging a and $b$ into one). Which becomes $\binom{4}{4} = 4!$. Then we must place a and $b$ inside the merged seats $\binom{2}{2}=2! = 2$.

$$
\begin{align}
|U| = 4! \\
|\bar{A}| = \binom{3}{3} * \binom{2}{2} = 3! * 2! = 4! * 2 \\
|A| = |U| - \left| \bar{A} \right|
=  4! - 3! * 2 \\
= 4 * (3 * 2 * 1) - (3 * 2 * 1) * 2 \\
= 3! (4 - 2) \\
= \boxed{ 2 * 3! } \\
\end{align}
$$