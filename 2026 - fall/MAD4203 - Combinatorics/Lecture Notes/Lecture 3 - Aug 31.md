# Permutations Practice Problems
## Practice 1
How many ways are there to arrange 26 lowercase letters so that no two vowels are consecutive?

### Answer 
$$
\begin{align}
S = \{ a, b, \dots \} \\
\end{align}
$$
\# permutations of $S$ such that vowels don't share spaces

First arrange 21-non vowels: $21!$ ways.

Basically finding \# ways of inserting vowels between non-vowels (guarantees no consecutive). In this case 21 positions are filled, meaning 22 open spaces to insert into:
$$
\begin{align}
21! * P(22,5) = \boxed{ 21! * \frac{22!}{(22-5)!} }
\end{align}
$$
## Practice 2
How many ways are there to seat $A,B,C,D,E,F$ around a circular table, if A refuses to sit next to $B$?

### Method 1: Subtraction principle
\# ways to place 6 people: $\frac{6!}{6} = 5!$
\# ways to place A and $B$ together:
- First merge $A$ and $B$ into one person: $\frac{5!}{5} = 4!$
- Then, account for both combinations $A,B$ and $B,A$: $4! * 2$
$$
\begin{align}
\frac{6!}{6} - 2 * \frac{5!}{5} = 5! - 2 * 4! = \boxed{ 3 * 4! }
\end{align}
$$
### Method 2: Direct counting \#1
First sit $A$ as head of the table (1 way). Then, place on the left and right of $A$ (4 choices and 3 choices, respectively). Then we are left with 3 seats that can be filled in any ways, linear permutation:

$$
\begin{align}
1 * 3 * 4 * 3! \\
\boxed{ 3 * 4! }
\end{align}
$$
### Method 3: Direct counting \#2
First sit $A$ as head of the table (1 way). Then, place down $B$, 3 choices (not next to A or on top of A). Then, place the rest (linear permutation):

$$
\begin{align}
1 * 3 * 4! \\
\boxed{ 3 * 4! }
\end{align}
$$

### Method 4: Direct counting \#3
\# ways to seat only $B,C,D,E,F \to$ circular permutation:
$$
\begin{align}
\frac{5!}{5}=4!
\end{align}
$$

Now place $A$ in one of the gaps, but cannot place in the gaps next to $B$, so 3 gaps to place in:
$$
\begin{align}
\boxed{ 3 * 4! }
\end{align}
$$

# Combinations
Let $r\geq 0, r \in \mathbb{Z}$ and let $S = \{ \dots \}, |S| = n \geq r$.
An $r$-combination of $S$ is an unordered selection of $r$ objects of the $n$ elements in $S$.

An unordered collection of elements from a set is also the definition of a **subset** $\to$ Combinations and subsets are equivalent.

*Remark:* An $r$-combination is an $r$-element subset of $S$ 
$$
\begin{align}
\binom{n}{r} := \text{\# r-combinations of $S$}
\end{align}
$$

## Combination Identities / Special cases
$$
\begin{align}
\binom{n}{0}  & = 1, \text{ only one way to pick zero elements: $\emptyset$} \\
\binom{n}{n} & = 1, \text{ only one way to pick the whole set} \\
\binom{n}{n-1}  & = \binom{n}{1} = n, \text{ taking/choosing one element from $S$} \\
r > n \to \binom{n}{r} &= 0,  \text{ no way of choosing more elements than exist}
\end{align}
$$

**Combinatorial proof**: a proof that uses counting arguments to prove a theorem or a statement.

## Theorem 1
For $0 \leq r \leq n$,
$$
\begin{align}
\binom{n}{r}= \frac{P(n,r)}{r!}= \frac{n!}{r!(n-r)!}
\end{align}
$$

**Proof:** We only have to prove that 
$$
\begin{align}
P(n,r) = r! * \binom{n}{r}
\end{align}
$$

Let $S$ be an $n$-element set. Each $r$-permutation of $S$ arises in exactly one way as a result of carrying out the following two steps: 
1. choose/select $r$ elements of from $S$
2. arrange the chosen $r$ elements

\# ways to carry out 1. is $\binom{n}{r}$ (by definition)
\# ways to carry out 2. is $r!$ (number of ways to permute $r!$ elements).

By multiplication principle,
$$
\begin{align}
P(n,r)= \binom{n}{r} * r! \\
\end{align}
$$
## Theorem 2.3.2:
For $0 \leq k \leq n$.
$$
\binom{n}{k}= \binom{n}{n-k}
$$
### Proof Method 1: Algebraic proof (not allowed on tests!)
$$
\begin{align}
\frac{n!}{n!(n-k)!} = \frac{n!}{(n-k)!(n-(n-k))!} \\
= \frac{n!}{n!(n-k)!}\\

\end{align}
$$

### Proof Method 2: Combinatorial proof

Let $S = \{ a_{1},\dots,a_{n} \}$, be an $n$-element set
For any $A \subseteq S$ w/ $|A|=k$

$$
\begin{align} \\
X = \left\{ A \subseteq S\ |\ |A| = k \right\} \\ \\

|\bar{A}| = |S| - |A| = n - k \\
Y = \left\{ B \subseteq S\ |\ |A| = n - k \right\} \\ \\

\text{Then } |X| = \binom{n}{k}, |Y| = \binom{n}{n-k} \\
\end{align}
$$

*Define* $f: x \to y$ as follows:
$$
\begin{align}
\forall A \in X, f(A) = \bar{A} \in Y. \\
\end{align}
$$
Then $f$ is a bijection from $X$ to $Y$: only one compliment of a set.
It follows that
$$
\begin{align}
\binom{n}{k}= |X| = |Y| = \binom{n}{n-k} \\ \\
\square
\end{align}
$$


## Theorem 2.3.3
For $1 \leq k \leq n-1$:
$$
\begin{align}
\binom{n}{r}k & =\binom{n-1}{k}+ \binom{n-1}{k-1}
\end{align}
$$
*Remark: This is called **Pascal's identity***.

### Intuition
For every element $a$ we have two choices: whether to choose it or not
1. if we *don't* choose $a$, then we still have to fill $k$ choices, however now we have one less element to choose form ($a$). 
2. if we *do* choose $a$, then we only have to fill $k-1$ choices, and since we took $a$ we also have one less element to choose from.

### Proof
Let $S$ be an $n$-element set and pick $a \in A$. *Count \# $k$-element subsets of $S$:* 
$$
\begin{align}
\text{Define } X := \{ A \in S \mid\ |A| = k \} \\
\text{Then } |X| = \binom{n}{k}
\end{align}
$$
>[!spoiler]- Note for understanding
Here $X_{1}$ is all subsets (size $k$) that include the element $a$, and $X_{2}$ is all the subsets that *don't* include element $a$. Together they form a partition of $X$.

Now partition $X$ into $X_{1}\ \&\ X_{2}$:

$$
\begin{align}
X_{1} = \{ A \subseteq S \mid\ \left| A \right|  = k \cap a \in A \} \\
X_{2} = \{ A \subseteq S \mid\ \left| A \right| = k \cap a \not\in A \}
\end{align}
$$

>[!spoiler]- Note for understanding
 In $X_{2}$ we have to fill $k$ spots, however we know $a \not\in A$ meaning we cannot consider $a$ as an option in our subset.

Then $|X_{2}| =$ \# $k$-element subsets of $S - \{ a \} = \binom{n-1}{k}$.

>[!spoiler]- Note for understanding
 In $X_{1}$ we have to fill $k$ spots as well, however we are guaranteed one of them will be filled with $a$, so we only really need to fill $k$. We also dont have access to $a$ as a choice since it was already chosen, so $n$ gets reduced by one here as well

Then $|X_{1}| =$ \# $(k-1)$-element subsets of $S - \{ a \} = \binom{n-1}{k-1}$.

By the addition principle:
$$
\begin{align}
|X| = |X_{2}| + |X_{1}| = \binom{n-1}{k} + \binom{n-1}{k-1}.
\end{align}
$$
