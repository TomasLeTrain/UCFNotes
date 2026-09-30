# Chapter 5 - Binomial Coefficients
Pascal's Identity - proved before:
$$
\begin{align}
\binom{n}{k}=\binom{n-1}{k-1} + \binom{n-1}{k}
\end{align}
$$

Can construct Pascal's triangle using this identity:
$$
\begin{align}
\binom{0}{0} \\
\binom{1}{0}, \binom{1}{1} \\
\binom{2}{0}, \binom{2}{1}, \binom{2}{2} \\
\dots \\
\binom{n}{0}, \binom{n}{1}, \dots, \binom{n}{n} \\

\end{align}
$$
## 5.2 - The binomial Theorem
> [!theorem] Binomial theorem
> For positive integer $n$:
> $$
> \begin{align}
> (x+y)^{n}=\sum_{k=0}^{n} \binom{n}{k}x^{k}y^{n-k}= \sum_{k=0}^{n} \binom{n}{k}x^{n-k}y^{k}=\sum_{k=0}^{n} \binom{n}{n-k}x^{n-k}y^{k} \\ \\
> 
> = \binom{n}{0}y^{n}+\binom{n}{1}xy^{n-1}+\binom{n}{2}x^{2}y^{n-2}+\dots+\binom{n}{n-1}x^{n-1}y+\binom{n}{n}x^{n} \\
> \end{align}
> $$
^bf3678

When going from left to right its *expansion*, when it's going from right to left its *evaluating the sum*.

$$
\begin{align}
(x+y)^{n}= \binom{n}{0}y^{n}+\binom{n}{1}xy^{n-1}+\binom{n}{2}x^{2}y^{n-2}+\dots+\binom{n}{n-1}x^{n-1}y+\binom{n}{n}x^{n} \\
\longrightarrow \text{expansion}  \\
\longleftarrow \text{evaluating the sum} 
\end{align}
$$

### Proof
#### Scratch work

Write $(x+y)^{n}=\underbrace{ (x+y)(x+y)\dots(x+y) }_{ n \text{ times} }$

We completely expand this product, using the distributive law, and group like terms. ^5491fe

When expanding the right side, we know there must be $2^{n}$ in the final expansion. This is because for any term, for every $(x+y)$ either the term gets multiplied by $x$ or by $y$.

Now consider the term
$$
\begin{align}
\boxed{ \text{??} }\ x^{k}y^{n-k}
\end{align}
$$
Here we know we must have "taken" (multiplied) by $x$ $k$ times, and the rest of the times($n-k$) it got multiplied by $y$.

Therefore, the number coefficient is the number of different ways get to this term, or in other words, the number of ways to pick $k$ from $n$ total elements. 

Another way to think about it is to consider a string made of $x$ and $y$ only. Consider a string with exactly $k$ copies of $x$:
$$
\begin{align}
x\ y\ y\ x\ x\ y\ x\ y\ y\ x\ y\ x \\
k = 6
\end{align}
$$
We coul say this string could represent one way to get $x^{k}y^{n-k}$, by taken $x$ on the first $(x+y)$ term, then taking $y$ on the second $(x+y)$ term, and so on. If we consider any string with exactly $k$ copies of $x$, it represents one way to get $x^{k}y^{n-k}$ from the $(x+y)$ factors. Since each of these ways adds exactly one to the coefficient, the value of the coefficient becomes the number of ways to pick exactly $k$ copies of $x$, which is $\binom{n}{k}$.


*Remark:* This argument assumes terms are being grouped by $x$, but same argument applies for $y$ by just swapping both.

#### Proof
`\begin{proof}`@[[#^bf3678]]

Write $(x+y)^{n}=\underbrace{ (x+y)(x+y)\dots(x+y) }_{ n \text{ times} }$

We completely expand this product, using the distributive law, and group like terms.

Since, for each factor $(x+y)$, we either pick $x$ or we pick $y$. There are $2^{n}$ terms in total, and each can be arranged as $x^{k}y^{n-k}$ for $k=0,1,\dots,n$. We obtain the term $x^{k}y^{n-k}$ by choosing $x$ in $k$ of the $n$ factors and by default, choosing $y$ in $n-k$ of the remaning factors. There are $\binom{n}{k}$ ways to do so. Thus, $(x+y)^{n}=\sum_{k=0}^{n}\binom{n}{k}x^{k}y^{n-k}$. 
`\end{proof}`

*Remarks:*
1. $(1+x)^{n} = \sum_{k=0}^{n}\binom{n}{k}x^{k}$
2. $\binom{n}{0} + \binom{n}{1} + \dots + \binom{n}{n} = 2^{n} = \underbrace{ (1+1)^{n} }_{ \text{binomial theorem} }$

3. $(1-x)^{n}=\sum_{k=0}^{n}(-1)^{k}\binom{n}{k}x^{n-k}$
4. $\binom{n}{0}-\binom{n}{1}+\binom{n}{2}-\binom{n}{3} + \dots = (1-1)^{n}= 0$

A consequence of this is:
$$
\begin{align}
\binom{n}{0}+\binom{n}{2}  + ... = \binom{n}{1} + \binom{n}{3} + \dots = \frac{2^{n}}{2} = 2^{n-1}
\end{align}
$$
Which states that the number of even subsets (left side) is equal in number to the number of odd subsets (right side)

## Example 1
$$
\begin{align}
\sum_{k=0}^{n} 2^{k}\binom{n}{k} = 3^{n}
\end{align}
$$
### Proof
$$
\begin{align}
3^{n}=(1+2)^{n}=\sum_{k=0}^{n} \binom{n}{k}2^{k}\quad \square
\end{align}
$$

## Example 2
Prove that
$$
\begin{align}
\sum_{k=1}^{n} k \binom{n}{k}  = n 2^{n-1} \\
\end{align}
$$
### Proof
Let $f(x) = (1+x)^{n}=\sum_{k=0}^{n}\binom{n}{k}x^{k}=\binom{n}{0}+\binom{n}{1}x+\binom{n}{2}x^{2}+\dots+\binom{n}{n}x^{n}$

Differentiate all sides of the equation:
$$
\begin{align}
f'(x)=n*(1+x)^{n-1} = 0+\binom{n}{1}+2\binom{n}{2}x + 3 \binom{n}{3} x^{2} + \dots + n\binom{n}{n}x^{n-1} \\
= \sum_{k=1}^{n} k\binom{n}{k}x^{k-1} \\
\end{align}
$$
Let $x=1$. Then $n * 2^{n-1} = \sum_{k=1}^{n} k\binom{n}{k} \quad \square$.

**Note:** Must expand out sum to account for the $k=0$ term missing on the equation from the question to not lose points! 

## Example 3
Prove that
$$
\begin{align}
\sum_{k=1}^{n} k^{2}\binom{n}{k}=n(n+1)2^{n-2}
\end{align}
$$
### Proof
Same first step as example 2:
$$
\begin{align}
n(1+x)^{n-1} = \sum_{k=1}^{n} k\binom{n}{k}x^{k}
\end{align}
$$

After, multiply both sides by $x$:
$$
\begin{align}
n(1+x)^{n-1}*x = \sum_{k=1}^{n} k\binom{n}{k}x^{k+1}
\end{align}
$$
Now differentiate both sides:
$$
\begin{align}
n\underbrace{ (1+x)^{n-1} }_{ 2^{n-1} } + n(n-1)\underbrace{ (1+x)^{n-2}x }_{ 2^{n-2} } = \sum_{k=1}^{n} k^{2}\binom{n}{k}x^{k-1}
\end{align}
$$
Let $x=1$:
$$
\begin{align}
n 2^{n-1} + n (n-1) 2^{n-2} = n*2^{n-2}(2+(n-1)) = \sum_{k=1}^{n} k^{2}\binom{n}{k}
\end{align}
$$

# Combinatorial proof
In mathematics, a *combinatorial proof* means the following:
- A proof by double counting e.g. $\binom{n}{k}=\binom{n-1}{k}+\binom{n-1}{k-1}$
- a bijective proof e.g. $\binom{n}{k} = \binom{n}{n-k}$

## Example 4
Use a combinatorial proof to prove that
$$
\begin{align}
k\binom{n}{k}= n \binom{n-1}{k-1}, k\geq k\geq 1 \\
\Longleftrightarrow
\binom{n}{k}\binom{k}{1}=\binom{n}{1}\binom{n-1}{k-1}
\end{align}
$$
### Proof
Given $n$ people, we choose $k$ members, and one gets designated as the leader. We have $\binom{n}{1}$ ways to 1st select the chair and $\binom{n-1}{k-1}$ ways to select the remaining members. Alternatively, we have $\binom{n}{k}$ ways to select a $k$ members, and them $\binom{k}{1}$ ways to select the leader from the $k$ chosen members. 


Therefore,
$\binom{n}{1}\binom{n-1}{k-1}$ = \# of ways to form a group of $k$ members with a leader = $\binom{n}{k}\binom{k}{1}\quad \square$.

## Example 5
Give a combinatorial proof that $\sum_{k=0}^{n}\binom{n}{k}^{2}=\binom{2n}{n}, n \geq k \geq 0$.

$$
\begin{align}
\sum_{k=0}^{n} \binom{n}{k}\binom{n}{n-k} = \binom{n+n}{n}
\end{align}
$$
Picking $n$ elements total ($k + (n-k) = k$), but from 2 different piles.
\# of ways to pick exaxctly $n$ people, that can be either boys or girls. So, can either pick $k$ boys and $n-k$ girls, or pick any person by combining both $n$ sized groups of boys and girls.


## Example 6
Give a combinatorial proof that $\sum_{k=0}^{r}\binom{m}{r-k}\binom{n}{k}=\binom{m+n}{r}$.

Can deduce from example 5 by $m = n = r$