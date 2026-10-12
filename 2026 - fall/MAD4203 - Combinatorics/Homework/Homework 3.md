# 12
*Let $n$ be a positive integer. Prove that*
$$
\begin{align}
\sum_{k=0}^{n} (-1)^{k}\binom{n}{k}^{2}=\left\{\begin{array}{cc}
0 & \text{if $n$ is odd} \\
(-1)^{m}\binom{2m}{m} & \text{if $n = 2m$}
\end{array}\right.
\end{align}
$$
*(Hint: For $n = 2m$, consider the coefficient of $x^{n}$ in $(1-x^{2})^{n} = (1+x)^{n}(1-x)^{n}$.)*

`\begin{proof}`


$$
\begin{align}
(1-x^{2})^{n} = \sum_{k=0}^{n} \binom{n}{k} (-1)^{k} x^{2k} \\ \\
\end{align}
$$
If $n$ is odd, the coefficient of $x^{n}$ is 0 since $n \neq 2k, \forall k \in \mathbb{Z}$ by definition.
If $n$ is even:
$$
\begin{align}
\text{coefficient of } x^{n}, n = 2m\to \binom{2m}{m} (-1)^{m} \\
\end{align}
$$

Now for the right-hand side:
$$
\begin{align}
(1+x)^{n}(1-x)^{n} = \left( \sum_{k=0}^{n} \binom{n}{k} x^{k}  \right)  \left( \sum_{k=0}^{n} \binom{n}{k} (-1)^{k}x^{k} \right)  \\ \\ \\
\text{coefficient of } x^{i} \to \\
c_{i}x^{i} = \sum_{k=0}^{i} \underbrace{ \binom{n}{k} (-1)^{k}x^{k} }_{ (1-x)^{n} } \underbrace{ \binom{n}{i-k} x^{i-k} }_{ (1+x)^{n} }
\end{align}
$$
In other words, the total \# of ways to get $x_{i}$ is the sum of ways to pick some $k$ copies of $x$ from the right hand side and $i-k$ copies from the left hand side.

$$
\begin{align}
c^{n}x^{n} = \sum_{k=0}^{n} \binom{n}{k} \binom{n}{n-k} (-1)^{k}x^{k}x^{n-k} \\
c^{n}\cancel{ x^{n} } = \sum_{k=0}^{n}  \binom{n}{k} \binom{n}{k} (-1)^{k}\cancel{ x^{n} } \\
 \\
\boxed{ \text{coeff of } x^{n}\to c^{n} = \sum_{k=0}^{n} \binom{n}{k}^{2} (-1)^{k} }
\end{align}
$$

Therefore,
$$
\begin{align}
(1-x^{2})^{n} = (1+x)^{n}(1-x)^{n} \\ \\

n = 2m \to \\
\binom{2m}{m}(-1)^{m} = \sum_{k=0}^{n} \binom{n}{k}^{2}(-1)^{k} \\ \\
n = 2m + 1 \to \\
0 = \sum_{k=0}^{n} \binom{n}{k}^{2}(-1)^{k} \\ \\

\implies \\
\sum_{k=0}^{n} \binom{n}{k}(-1)^{k} = \left\{\begin{array}{cc}
0 & \text{if n is odd} \\
\binom{2m}{m}(-1)^{m} & n = 2m
\end{array}\right.
\end{align}
$$
`\end{proof}`

# 15
*Prove, that for every integer $n >1$,*
$$
\begin{align}
\binom{n}{1} - 2 \binom{n}{2} + \dots + (-1)^{n-1} n \binom{n}{n} = 0
\end{align}
$$

`\begin{proof}`

From the given equation
$$
\begin{align}
\binom{n}{1} - 2 \binom{n}{2} + \dots + (-1)^{n-1} n \binom{n}{n}= \sum_{k=0}^{n} \binom{n}{k} (-1)^{k-1} k = 0 \\
\end{align}

$$

Can obtain by differentiating a polynomial in binomal coefficient form:
$$
\begin{align}
(1-x)^{n} = \sum_{k=0}^{n} \binom{n}{k} (-x)^{n} \\
\frac{d}{dx} (1-x)^{n} = \frac{d}{dx}\left[ \binom{n}{0}(-x)^{0} + \binom{n}{1}(-x)^{1} + \dots + \binom{n}{n}(-x)^{n} \right]  \\ \\

\cancel{ (-1) }(n)(1-x)^{n-1} =  \binom{n}{0}\cancel{ (-1) }(0)(-x)^{-1} + \binom{n}{1}\cancel{ (-1) }(1)(-x)^{0} + \dots + \binom{n}{n}\cancel{ (-1) }(n)(-x)^{n-1} \\
(n)(1-x)^{n-1} =  \binom{n}{0}(0)(-x)^{-1} + \binom{n}{0}(1)(-x)^{1} + \dots + \binom{n}{n}(n)(-x)^{n-1} \\ \\ \\

\boxed{ x=1 \to } \\
(n)(1-1)^{n-1} =  \binom{n}{0}(0)(-1)^{-1} + \binom{n}{0}(1)(-1)^{1} + \dots + \binom{n}{n}(n)(-1)^{n-1} \\ \\
\boxed{ 0 =  \sum_{k=0}^{n} \binom{n}{k}(-1)^{n-1}k  }
\end{align}
$$
`\end{proof}`
# 16
*By integrating the binomial expansion, prove that, for a positive integer $n$,*
$$
\begin{align}
1 + \frac{1}{2} \binom{n}{1} + \frac{1}{3} \binom{n}{2} + \dots + \frac{1}{n+1}\binom{n}{n} = \frac{2^{n+1}-1}{n+1}
\end{align}
$$

`\begin{proof}`
$$
\begin{align}
(1+x)^{n} = \sum_{k=0}^{n} \binom{n}{k} x^{k}1^{n-k} = \sum_{k=0}^{n} \binom{n}{k}x^{k} \\ \\
\int (1+x)^{n} = \int\sum_{k=0}^{n} \binom{n}{k}x^{k} \\
\frac{(1+x)^{n+1}}{n+1} = \int \left[ \binom{n}{0}x^{0} + \binom{n}{1}x^{1} + \dots + \binom{n}{n} x^{n} \right]  + C \\
\frac{(1+x)^{n+1}}{n+1} = \left[ \binom{n}{0} \frac{x^{1}}{1} + \binom{n}{1} \frac{x^{2}}{2} + \dots + \binom{n}{n} \frac{x^{n+1}}{n+1} \right] +C \\ \\
\frac{(1+x)^{n+1}}{n+1} = \sum_{k=0}^{n} \binom{n}{k} \frac{x^{k+1}}{k+1}  +C\\ \\
\end{align}
$$

Can solve for $C$ by $x = 0$:
$$
\begin{align}
\frac{(1+0)^{n+1}}{n+1} = \sum_{k=0}^{n} \binom{n}{k} \frac{0^{k+1}}{k+1} +C \\ \\
\frac{1}{n+1} = 0 + C \to \boxed{ C = \frac{1}{n+1} } \\ \\ \\
\end{align}
$$
Can then solve for $x = 1$:
$$
\begin{align}
\frac{(1+1)^{n+1}}{n+1} = \sum_{k=0}^{n} \binom{n}{k} \frac{1^{k+1}}{k+1} + \frac{1}{n+1}\\ \\
\boxed{ \frac{2^{n+1} - 1}{n+1} = \sum_{k=0}^{n} \binom{n}{k} \frac{1}{k+1} }
\end{align}
$$
`\end{proof}`
# 17
*Prove the identity in the previous exercise (problem 16) by using (5.2) and (5.3).*
`\begin{proof}`
$$
\begin{align} \\
k\binom{n}{k} = \binom{n-1}{k-1}n \\
(k+1)\binom{n+1}{k+1} = \binom{n}{k}(n+1) \\
\binom{n+1}{k+1} \frac{1}{n+1} = \binom{n}{k} \frac{1}{k+1} \\
\sum_{k=0}^{n}  \binom{n+1}{k+1} \frac{1}{n+1} =  \sum_{k=0}^{n} \binom{n}{k} \frac{1}{k+1} \\ \\
\end{align}
$$

Simplifying the left-hand side:
$$
\begin{align}
=  \frac{1}{n+1} \sum_{k=0}^{n}  \binom{n+1}{k+1} \\
=  \frac{1}{n+1} \sum_{k=1}^{n+1}  \binom{n+1}{k} \\
= \frac{1}{n+1} \left(\sum_{k=0}^{n+1}  \binom{n+1}{k} - \binom{n+1}{0} \right)  \\
= \frac{1}{n+1} \left(2^{n+1} - 1 \right) = \frac{2^{n+1}-1}{n+1} \\
\end{align}
$$

So,
$$
\begin{align}
\boxed{ \sum_{k=0}^{n} \binom{n}{k} \frac{1}{k+1} = \frac{2^{n+1}-1}{n+1} }
\end{align}
$$
`\end{proof}`

# 26
*Let $n$ and $k$ be integers with $1 \leq k \leq n$. Prove that*
$$
\begin{align}
\sum_{k=1}^{n} \binom{n}{k}\binom{n}{k-1} = \frac{1}{2} \binom{2n+2}{n+1} - \binom{2n}{n}
\end{align}
$$
`\begin{proof}`

Must prove
$$
\begin{align}
2 \sum_{k=1}^{n} \binom{n}{k}\binom{n}{k-1} = \binom{2n+2}{n+1} - 2\binom{2n}{n} \\ \\
\end{align}
$$
First, consider picking $n+1$ elements in total, where the elements belong to either set $A$ or $B$. Both sets are size $n$, so the total number of ways to count picking $n+1$ elements is:
$$
\begin{align}
\binom{2n}{n+1}
\end{align}
$$
Another way to count the \# of ways is by picking $k$ elements from $A$, then picking $n-k+1$ elements from $B$. Doing this over all $1 \leq k \leq n$ gives the same result:
$$
\begin{align}
\sum_{k=1}^{n} \binom{n}{k}\binom{n}{n-k+1}
\end{align}
$$

Therefore:
$$
\begin{align}
\boxed{ \binom{2n}{n+1} = \sum_{k=1}^{n} \binom{n}{k}\binom{n}{n-k+1} = \sum_{k=1}^{n} \binom{n}{k}\binom{n}{k-1} }
\end{align}
$$

Substituting this into the original equation:
$$
\begin{align}
2 \binom{2n}{n+1} = \binom{2n+2}{n+1} - 2\binom{2n}{n} \\
2 \binom{2n}{n+1} + 2\binom{2n}{n} = \binom{2n+2}{n+1} \\
2 \left(\binom{2n}{n+1} + \binom{2n}{n}\right) = \binom{2n+2}{n+1} \\
\end{align}
$$
By pascal's identity:
$$
\begin{align}
2 * \binom{2n+1}{n+1} = \binom{2n+2}{n+1} \\ \\
\end{align}
$$
To prove this equality we use pascal's identity on the left-hand side:
$$
\begin{align}
\binom{2n+1}{n+1} =  \binom{2n+1}{(2n+1)-(n+1)} =  \binom{2n+1}{n} \\ \\ \\
\to
 2 * \binom{2n+1}{n+1} = \binom{2n+1}{n+1} + \binom{2n+1}{n+1} \\ \\
 = \binom{2n+1}{n+1} + \binom{2n+1}{n} \\ \\
\boxed{ = \binom{2n+2}{n+1} }
\end{align}
$$
`\end{proof}`

# 27
*Let $n$ and $k$ be positive integers. Give a combinatorial proof of the identity (5.15):*
$$
\begin{align}
n(n+1)2^{n-2}=\sum_{k=1}^{n} k^{2}\binom{n}{k}
\end{align}
$$

`\begin{proof}`
Consider selecting a study group $k$, selected from a bigger group of size $n$. For the group of size $k$, the positions of president and vice-president are each assigned to a person in the group (both positions could go to the same person). The \# of ways to choose a study group of $k$ people with said positions is:
$$
\begin{align}
\underbrace{ \binom{n}{k} }_{ \text{choose k people} } * \underbrace{ \binom{k}{1} }_{ \text{choose president} } *\underbrace{ \binom{k}{1} }_{ \text{choose vp} } = \binom{n}{k}k^{2}
\end{align}
$$
Counting the number of ways to choose a study group of any size:
$$
\begin{align}
\boxed{ \sum_{k=1}^{n} \binom{n}{k}k^{2} }
\end{align}
$$

Now, consider picking the president first, then the vice president, and then the rest of the people.

Consider the case where the president and vice president are different people. There are $n$ ways to select a president, $n-1$ ways to select a vp, and $2^{n-2}$ ways to select the rest of the people in the study group:
$$
\begin{align}
\underbrace{ n }_{ \text{president} } * \underbrace{ (n-1) }_{ vp } * \underbrace{ 2^{n-2} }_{ \text{rest of study group}}
\end{align}
$$

Now, consider the case when the president and vp are the same person. Then, $n$ ways to pick the president, one way to pick the vp (has to be the same person as the president) and $2^{n-1}$ people left to include in the study group:
$$
\begin{align}
n * 1 * 2^{n-1}
\end{align}
$$
Since both of these cases are mutually exclusive, the total \# of study groups can be found by the addition principle:
$$
\begin{align}
n*(n-1) * 2^{n-2} + n * 2^{n-1} \\
n * ((n-1) * 2^{n-2} + 2^{n-1}) \\
n * ((n-1) + 2) *2^{n-2} \\
\boxed{ n (n+1) 2^{n-2} }
\end{align}
$$
`\end{proof}`

# 31
*Prove that there are only two antichains of $S=\{1, 2, 3, 4, 5\}$ of size 10 (10 is maximum by Spemer's theorem), namely, the antichain of all 2-subsets of $S$ and the antichain of all 3-subsets.*

`\begin{proof}`

By Spemer's theorem, the maximum size of any antichain is 
$$
\begin{align}
\binom{n}{\left\lfloor  \frac{n}{2}  \right\rfloor } \to \binom{5}{\left\lfloor  \frac{5}{2}  \right\rfloor } = \frac{5!}{2!3!} = 10
\end{align}
$$

Namely, both the antichains of all 2-subsets and all 3 subsets both are of size 10:
$$
\begin{align}
\binom{5}{3} = \binom{5}{2} = 10
\end{align}
$$
`\end{proof}`

# 33
*Construct a partition of the subsets of $\{ 1,2,3,4,5 \}$ into symmetric chains.*
$$
\begin{align}
\emptyset \subset \{ 1 \} \subset \{ 1,2 \} \subset \{ 1,2,3 \} \subset  \{ 1,2,3,4 \} \subset  \{ 1,2,3,4,5 \}, \\ \\
\{ 2 \} \subset \{ 2,3 \} \subset \{ 2,3,4 \} \subset  \{ 2,3,4,5 \}, \\ \\
\{ 3 \} \subset \{ 1,3 \} \subset \{ 1,3,4 \} \subset  \{ 1,3,4,5 \}, \\ \\
\{ 4 \} \subset \{ 1,4 \} \subset \{ 1,2,4 \} \subset  \{ 1,2,4,5 \}, \\ \\
\{ 5 \} \subset \{ 1,5 \} \subset \{ 1,2,5 \} \subset  \{ 1,2,3,5 \}, \\ \\

\end{align}
$$
Can construct partitions for larger $n$ from smaller $n$, where $n$ denotes the number of elements.
$$
\begin{align} \\
n = 1 \to  \\ 
\emptyset \subset \{ 1 \} \\ \\

n = 2\to \\ 
\emptyset \subset \{ 1 \} \subset \{ 1,2 \} \\
\{ 2 \} \\ \\

n = 3\to \\ 
\emptyset \subset \{ 1 \} \subset \{ 1,2 \} \subset \{ 1,2,3 \} \\
\{ 2 \} \subset \{ 2,3 \} \\
\{ 3 \} \subset \{ 1,3 \} \\ \\
\end{align}
$$
For $n =4$:
$$
\begin{align}
\emptyset \subset \{ 1 \} \subset \{ 1,2 \} \subset \{ 1,2,3 \} \subset \{ 1,2,3,4 \} \\
\{ 4 \} \subset \{ 1,4 \} \subset \{ 1,2,4 \} \\
\{ 2\} \subset \{ 2,3 \} \subset \{ 2,3,4 \} \\
\{ 2,4 \} \\
\{ 3 \} \subset \{ 1,3 \} \subset \{ 1,3,4 \} \\
\{ 3,4 \}
\end{align}
$$
So for $n = 5$:
$$
\begin{align}
\emptyset \subset \{ 1 \} \subset \{ 1,2 \} \subset \{ 1,2,3 \} \subset \{ 1,2,3,4 \} \subset \{ 1,2,3,4,5 \} \\
\{ 5 \} \subset \{ 1,5 \} \subset \{ 1,2,5 \} \subset \{ 1,2,3,5 \}  \\
\{ 4 \} \subset \{ 1,4 \} \subset \{ 1,2,4 \} \subset \{ 1,2,4,5 \} \\
\{ 2\} \subset \{ 2,3 \} \subset \{ 2,3,4 \} \subset \{ 2,3,4,5 \} \\
\{ 3\} \subset \{ 1,3 \} \subset \{ 1,3,4 \} \subset \{ 1,3,4,5 \} \\
\{ 4,5 \} \subset \{ 1,4,5 \}  \\
\{ 2,5\} \subset \{ 2,3,5 \} \\ 
\{ 3,5\} \subset \{ 1,3,5 \} \\
\{ 3,4 \} \subset \{ 3,4,5 \} \\
\{ 2,4 \} \subset \{ 2,4,5 \} \\
\end{align}
$$

# 34
*In a partition of the subsets of $\{ 1,2,\dots,n \}$ into symmetric chains, how many chains have only one subset in them? Two subsets? $k$ subsets?*
All chains with one subset must have a subset of size $\frac{n}{2}$. Let $k$ be the size of the single subset. Then, $k = \left\lfloor  \frac{n}{2}  \right\rfloor$, and since it's a symmetric chain, $k + k = n$. If $n$ is even this checks out, however if $n$ is odd then $\left\lfloor  \frac{n}{2}  \right\rfloor * 2 \neq n$, so it does not form a symmetric chain.

Now consider the partitions with two subsets in them. Let $k$ denote the size of the smallest subset. Then the size of the larger subset must be $n - k$ for the chains to be symmetric.

Consider a partition whose smallest subset is size $r$ and whose number of subsets equals $k$. Then, the size of the largest subset must equal $r + k -1$, and since it's a symmetric chain $r + (r+k - 1) = n \to 2r + k - 1 = n$.
Since its symmetric chains $r + k = n$, and the number of subsets in this partition is $k - r + 1$.


# 36
*Prove the identity 
$$
\begin{align}
\sum_{k=0}^{n} \binom{m_{1}}{k}\binom{m_{2}}{n-k} = \binom{m_{1}+m_{2}}{n}
\end{align}
$$
using the binomial theorem and the relation*
$$
\begin{align}
(1+x)^{m_{1}}(1+x)^{m_{2}} = (1+x)^{m_{1}+m_{2}}
\end{align}
$$
`\begin{proof}`
For the right-hand side:
$$
\begin{align}
(1+x)^{m_{1}+m_{2}} = \sum_{k=0}^{m_{1}+m_{2}} \binom{m_{1}+m_{2}}{k}x^{k} \\
\boxed{ \text{coefficient of } x^{n} \to \binom{m_{1}+m_{2}}{n} }
\end{align}
$$
For the left-hand side:
$$
\begin{align}
(1+x)^{m_{1}}(1+x)^{m_{2}} =\left(  \sum_{k=0}^{m_{1}} \binom{m_{1}}{k} x^{k} \right)  * \left( \sum_{j=0}^{m_{2}} \binom{m_{2}}{j} x^{j} \right) \\

\text{coefficient of } x^{n} \to \\
j + k = n \to j = n - k \\ \\
\boxed{\to  \sum_{k=0}^{m_{2}} \binom{m_{1}}{k} \binom{m_{2}}{n-k} }
\end{align}
$$
`\end{proof}`
# 43
*Prove by induction on $n$ that, for $n$ a positive integer,*
$$
\begin{align}
\frac{1}{(1-z)^{n}} = \sum_{k=0}^{\infty} \binom{n+k-1}{k}z^{k}, |z|<1
\end{align}
$$
*Assume the validity of*
$$
\begin{align}
\frac{1}{1-z} = \sum_{k=0}^{\infty} z^{k}, |z| < 1
\end{align}
$$
`\begin{proof}`
Consider the base case $n = 1$:
$$
\begin{align}
\frac{1}{(1-z)^{1}} = \sum_{k=0}^{\infty} \binom{1+k-1}{k}z^{k} \\
\frac{1}{1-z} = \sum_{k=0}^{\infty} z^{k}
\end{align}
$$
Which is assumed to be valid. Thus, the base case is also valid.

Now assume the equality holds for some $n$. Then, we prove the equality also holds for $n+1$:
$$
\begin{align}
\frac{1}{(1-z)^{n+1}} = \sum_{k=0}^{\infty} \binom{(n+1)+k-1}{k}z^{k} \\ \\
\frac{1}{(1-z)} * \frac{1}{(1-z)^{n}} = \sum_{k=0}^{\infty} \binom{n+k}{k}z^{k} \tag{$\ast$}  \\
\end{align}
$$

^862409

Expanding the left-hand side with the inductive hypothesis and the base case:
$$
\begin{align}

\frac{1}{1-z} * \frac{1}{(1-z)^{n}} = \sum_{k=0}^{\infty} z^{k} * \sum_{j=0}^{\infty} \binom{n+j-1}{j}z^{j}  \\
\end{align}
$$
Can find the final coefficient for some $z^{i}$ by finding all the terms for which $k + j = i$:
$$
\begin{align}
c_{i}\cancel{ x_{i} } = \sum_{k=0}^{i} \binom{n+k-1}{k} \cancel{ z^{k} * z^{i-k} } \\
c_{i} = \sum_{k=0}^{i} \binom{n+k-1}{k} = \boxed{ \binom{m+i}{i} }
\end{align}
$$
This coefficient matches the coefficient of the right-hand side of [[#^862409]]. By induction, the statement is true for all $n$.
`\end{proof}`
# 48
*Use Theorem 5.6.1 to show that, if $m$ and $n$ are positive integers, then a partially ordered set of $mn + 1$ elements has a chain of size $m+1$ or an antichain of size $n+1$.*
`\begin{proof}`
Let $(X,\leq)$ be a finite partial order on $X$, with $|X| = mn + 1$.

Suppose that $X$ has no chain of size $m+1$ and no antichain of size $n+1$.

Let $r$ denote the largest size of a chain. Then, $r \leq m$, since there is no chain of size $m+1$. By theorem 5.6.1, $X$ can be partitioned into $r$ antichains.

Let $X$ be partitioned into $r$ antichains: $A_{1},A_{2},\dots,A_{r}$.

Since it was assumed no antichain was of size $n+1$, $A_{i} \leq n$. Therefore:
$$
\begin{align}
|X| = |A_{1}| + |A_{2}| + \dots + |A_{n}| \to \\
|X| \leq n + n + \dots + n = n * r \\
\end{align}
$$
Since $r \leq m$:
$$
\begin{align}
|X| \leq n * m
\end{align}
$$
However, it is given that $|X| = n * m + 1$, a contradiction. Thus, there must be a chain of size $m+1$ or an antichain of size $n+1$.
`\end{proof}`
# 51
*Let $R$ and $S$ be two partial orders on the same set $X$. Considering $R$ and $S$ as subsets of $X \times X$, we assume that $R \subseteq S$ but $R \neq S$. Show that there exists an ordered pair $(p, q)$, where $(p, q) \in S$ and $(p, q) \not\in R$ such that $R' = R \cup {(p, q)}$ is also a partial order on $X$. Show by example that not every such $(p, q)$ has the property that $R'$ is a partial order on $X$*

`\begin{proof}`

A partial order of a set $X$ must be a reflexive, antisymmetric, and transitive relation. Both $S$ and $R$ satisfy those properties, so it must be shown that adding some $(p,q) \in S, (p,q) \not\in R$ to $R$ makes an $R'$ that still satisfies the properties of partial order.

Instead, consider removing pairs from $S$ to make $R$, given that $R$ must still be a partial order. Removing $(p,p), p \in X$ would break the reflexive property, so all pairs of that form are in both $S$ and $R$. 

Now consider some pair $(p,q) \in S, p \neq q \to p\ S\ q$. Since $S$ is a partial order, $q \cancel{ S } p$ by the antisymmetry property. This means that removing $(p,q)$ from $S$ does not break the antisymmetry property either. However, removing this pair can break the transitive property.

By the transitive property, if $p\ S\ q$ and $q\ S\ n$, then $p\ S\ n$. If the pair $(p,n)$ is removed, then the transitive property would be broken. Therefore, removing $(p,n)$ also implies removing $(p,q)$ and $(p,n)$ from $S$ to keep it a partial order.

Given all this, consider a set $R \subseteq S, R \neq S$. Since $R \neq S$, there must be at least one ordered pair that is in $S$ and not in $R$. As shown before, this pair must be of the form $(p,q) \in S, p \neq q$. Now, consider any $p,q,n$ for which the transitive property applies in $S$. In other words, $p\ S\ q, q\ S\ n,p\ S\ n$. Then, $R$ can contain any subset of them except $(p,q)$ and $(q,n)$, since in that case the transitive property would be broken.

In the case that none of these pairs are in $R$, then $R'$ can be formed by picking any such pairs. If one of the 3 pairs is in $R$, then another can be picked such that both $(p,q)$ and $(q,n)$ are not in $R$. The last case is if $(p,q)$ and $(p,n)$ are in $R$, in which case $(q,n)$ can be added which keeps the transitive property.

Thus, for any partial orders $R$ and $S$ on $X$, such that $R \subseteq S, R\neq S$, there is always a pair that can be added to $R$ that still forms a partial order. Also, in the case that $p\ R\ q$ and $p\ \cancel{ R }\ n$, adding the pair $(q,n)$ to $R$ causes the transitive property to break, making $R'$ not a partial order.
`\end{proof}`
# Ramsey number problem
*Use Pascal's Identity and induction to prove that  $R(m,n)\leq \binom{m+n-2}{m-1}$ for all $m \geq 2$ and $n\geq2$.*
`\begin{proof}`
 $R(2,2) = 2$, and $\binom{2+2-2}{1} = 2$, so the statement is true for the base case $m = 2, n = 2$.

Assume the statement holds for all $m,n$ whose sum is $m + n < k$ for some $k > 4$.

Ramsey numbers follow the inequality $R(m,n) \leq R(m-1,n) + R(m,n-1)$. It can be seen that all parameters of $R$ sum to $< k$, so the inductive hypothesis can be used:
$$
\begin{align}
R(m,n) \leq R(m-1,n) + R(m,n-1) \\
R(m,n) \leq \binom{m+n-3}{m-2} + \binom{m+n-3}{m-1}
\end{align}
$$

Now consider pascal's identity:
$$
\begin{align}
\binom{j}{r} = \binom{j-1}{r-1} + \binom{j-1}{r}
\end{align}
$$
Using $j = m+n-2$ and $r = m-1$:
$$
\begin{align}
\binom{m+n-2}{m-1} = \binom{m+n-3}{m-2} + \binom{m+n-3}{m-1}
\end{align}
$$

Substituting into the inequality above:

$$
\begin{align}
R(m,n) \leq \binom{m+n-3}{m-2} + \binom{m+n-3}{m-1} \\
\boxed{ R(m,n) \leq \binom{m+n-2}{m+1} }
\end{align}
$$
Thus, the statement holds for $n \geq 2,m \geq 2$.
`\end{proof}`
