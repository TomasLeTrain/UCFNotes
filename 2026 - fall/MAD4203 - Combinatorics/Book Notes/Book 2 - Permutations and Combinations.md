**combination**: un-ordered set of elements
**permutation**: ordered set of elements

# 2.2 Permutations of sets
## Permutations
### Example
$$
\begin{align}
S = \{ a, b, c \} \\
\text{three 1-permutations: a b c} \\
\text{six 2-permutations: ab ac ba bc ca cb} \\
\text{six 3-permutations: abc acb bac bca cab cba} \\
\end{align}
$$

The number of permutations can be computed with the function $P(n,r)$:
$$
\begin{align}
P(n,r) = \text{number of $r$ permutations of an $n$-element set}  \\
\text{for $r > n$ (more elements in perm than exist in set): } P(n,r) = 0 \\
\text{for $r = 1$ (one element per perm): } P(n,1) = n \\
\text{for $r = n$: } P(n,n) = n! \\
\end{align}
$$

*A **permutation** of $S$ is a listing of elements from $S$ in some order*.
$$
\begin{align}
P_{r}^{n}=P(n,r) = n \times (n-1) \times \dots \times (n-r+1) \\
P_{r}^{n}=P(n,r) = \frac{n!}{(n - r)!} \\
\end{align}
$$
### formulation
first element can be chosen $n$ times, the next one can be chosen $n-1$ times, etc. until the last element can be chosen $n-r + 1$ times (chose $r$ elements already). These chosen times are multiplied because of the **multiplication principle**.

The factorial version is divided by $n-r$ since that's the number of elements not included in the permutation.

### Linear permutations 
**linear permutations** is a permutation of elements in a "line" (as if they were lined up next to each other).

A **circular permutation** is a permutation in which only the relative order matters (there is no "start" element). This naturally reduces the number of permutations (permutations with different "starts" get reduced to one).
To find the number of circular permutations we can divide by $r$ to account for the duplicated starts ($r$ different possible starts).

*Remark:* This works because each part (circular permutation) contained the same amount($r$) of $r$-permutations so the division principle could be applied to find the number of parts(circular permutations).


# 2.3 - Combinations (Subsets) of Setes
A **Combination** is an unordered selection of elements from set $S$ (selection of some given size).

A combination $A$ is a subset of $S$ since it is unordered: $S: A \subseteq S$.

This means **Combination** and **Subset** are basically interchangeable.

Also have a function to determine number of $r$- combinations for a set $S$ of size $n$.

$$
\begin{align}
C(n,r) = C_{r}^{n}= \binom{n}{r} = \frac{n!}{r!(n-r)!} \\
P_{r}^{n} = P(n,r) = r!\binom{n}{r} \\
\binom{n}{r}=\binom{n}{n-r} \\
= \frac{n!}{(n-r)!(n-(n-r))!}\\
= \frac{n!}{(n-r)!(n-n+r)!}\\
= \frac{n!}{(n-r)!r!}\\
\binom{n}{r}=\binom{n}{n-r} = \frac{n!}{r!(n-r)!}
\end{align}
$$

**Proof:**
A permutation is built by doing two operations:
1. choose $r$ elements from the set
2. order them in some way

we can get combinations from permutations by removing the second step.

The number of ways to order $r$ elements is $r!$, so we can divide that amount from the total permutations to get the formula:
$$
\begin{align}
\binom{n}{r}= \frac{P(n,r)}{r!} = \frac{n!}{r!(n-r)!}
\end{align}
$$


**Pascals formula**:
$$
\begin{align}
\text{for all }1 \leq k \leq n - 1 \\
\binom{n}{r}= \binom{n-1}{r} + \binom{n-1}{r-1} \\
\text{or written another way:} \\
\binom{n+1}{r+1}= \binom{n}{r+1} + \binom{n}{r}
\end{align}
$$

Pascal examples: page 44




$$
\begin{align}
2^{n}=\binom{n}{0}+\binom{n}{1}+\dots+\binom{n}{n}
\end{align}
$$

**Proof**:
We can consider all subsets (the power set) of $S$ as being counted inside the rhs of the function. Since the length of the power set is $2^{n}$, both match.

**Double counting** is an approach where two different ways of coutning the same result are used to prove equality of two different things (such as the example above).

# 2.4 - Permutations of Multisets
## Permutations of multiset with infinite repetition numbers
If $S = \{ \infty * a, \infty * b, \dots \}$, then the number of $r$-permutations becomes $k^{r}$.


**Proof:** for every element in the permutation we can choose from $k$ different options, and we do this $r$ times.

This also holds if all repetition numbers are $\geq r$.


## Counting Permutations for arbitrary multiset

The number of permutations of $S$ (in other words $r$-permutations of $S$, where $n$ is size of $S$ and $r = n$) equals
$$
\begin{align}
\frac{n!}{n_{1}!\,n_{2}!\,n_{3}!\,\dots \, n_{k}!} \\

\end{align}
$$
**Proof:** Let $S = \{ n_{1} a_{1}, n_{2}a_{2},\dots,n_{k}a_{k}\}$.  For the first element we have to place $n_{1}$ number of $a_{1}$ into the permutation. This can be done in
$$ \binom{n}{n_{1}} $$
ways. The next element is the same, except the number of available spots in the permutation is now decreased by $n_{1}$. This means that that the number of ways to place $a_{2}$ is

$$ \binom{n - n_{1}}{n_{2}} $$
Repeating through all elements we can multiply since they are choices made alongside each other, giving:
$$
\begin{align}
\binom{n}{n_{1}}\binom{n-n_{1}}{n_{2}}\binom{n-n_{1}-n_{2}}{n_{3}}\dots \binom{n-n_{1}-n_{2}-\dots-n_{k-1}}{n_{k}} \\
\end{align}
$$
Expanding out this gives
$$
\begin{align}
\frac{n!}{n_{1}!(n-n_{1})!}
\frac{(n-n_{1})!}{n_{2}!(n-n_{1}-n_{2})!}
\frac{(n-n_{1}-n_{2})!}{n_{3}!(n-n_{1}-n_{2}-n_{3})!}
\dots \\
\end{align}
$$
The bottom and top cancel in a chain:

$$
\begin{align}
\frac{n!}{n_{1}!\cancel{ (n-n_{1})! }}
\frac{\cancel{ (n-n_{1})! }}{n_{2}!\cancel{ (n-n_{1}-n_{2})! }}
\frac{\cancel{ (n-n_{1}-n_{2})! }}{n_{3}!\cancel{ (n-n_{1}-n_{2}-n_{3})! }}
\dots \\
\frac{\cancel{ (n-n_{1}-n_{2}-\dots-n_{k-1})! }}{n_{k}!(n-n_{1}-n_{2}-\dots-n_{k})! }
\end{align}
$$
This ends up becoming:
$$
\begin{align}
\frac{n!}{n_{1}!n_{2}!n_{3}!\dots n_{k}!0!}=
\boxed{ \frac{n!}{n_{1}!n_{2}!n_{3}!\dots n_{k}!} }
\end{align}
$$
Here $0!$ comes from the last denominator that doesn't get canceled, however at this point all the spots have been taken, so the number becomes $0!$.


# Combinations of multiset
effectively equal to a **submultiset**, basically selecting repeetiton numbers to be $\leq$ the original ones.

given  $S = \{ \infty* a, \infty * b, \infty * c, \dots \}$, $r$-combinations $A$ can be counted by all the $x_{k}$ that satisfy the equation: 
$$
\begin{align}
A = \{ x_{1} * a, x_{2} * b, x_{3} * c, \dots \} \\
r = x_{1}+x_{2}+x_{3}+x_{4}+\dots, x_{k} \geq 0 \\
\end{align}
$$

Every combination of $x_{k}$ that satisfies the equal corresponds to a submultiset. Therefore to get the answer we must count the number of solutions.

$$
\begin{align}
x_{1} = r, x_{2\dots } = 0 \\
x_{1} = r-1, \sum_{k=2} x_{k} = 1 \\
x_{1} = r-2, \sum_{k=2} x_{k} = 2 \\
x_{1} = r-3, \sum_{k=2} x_{k} = 3 \\
\dots \\
x_{1} = 0, \sum_{k=2} x_{k} = r \\
\end{align}
$$

To solve the problem we can imagine we have $r$-number of "1". We have to distribute all 1's across any of the $x_{k}$'s, and since we keep the number of "1" objects constant all those combinations will sum to $r$. To find all those combinations we can construct another object "\*", whose job is to split the 1's across different $x_{k}$.

For example consider the examples:
$$
\begin{align}
x_{1}+x_{2}+x_{3} = 5 \quad  x_{1} = 1, x_{2}=3, x_{3}=1\quad \to 
1 * 111 * 1 \\
 \\
x_{1}+x_{2}+x_{3} = 5 \quad  x_{1} = 0, x_{2}=0, x_{3}=5\quad \to 
** 11111 \\
\dots
\end{align}
$$


Since the number of "\*" and "1" are fixed can redefine the problem as the number of ways to permute
$$
\begin{align}
T = \{ (k-1) \times *, r \times 1 \}
\end{align}
$$
which becomes:
$$
\begin{align}
\frac{n!}{n_{1}!n_{2}!} =
\frac{(k+r-1)!}{r! * (k-1)! }
\end{align}
$$
This can be simplified down to
$$
\begin{align}
\frac{n!}{n_{1}!n_{2}!} =
\frac{n!}{n_{1}!(n - n_{1})!} = \binom{n}{n_{1}} \\

\frac{(k+r-1)!}{r! * (k-1)! } = \boxed{ \binom{k+r-1}{r} }

\end{align}
$$



# 2.6 Finite probability
