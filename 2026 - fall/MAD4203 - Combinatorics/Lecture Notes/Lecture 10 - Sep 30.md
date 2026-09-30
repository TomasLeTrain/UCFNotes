# Review
Use combinatorial Proof to prove that for all $n \geq 1$,
$$
\begin{align}
\sum_{k=1}^{n} k \binom{n}{k} = n 2^{n-1} \\
\sum_{k=1}^{n} \binom{n}{k} \binom{k}{1} =  \binom{n}{1} 2^{n-1} \\
\end{align}
$$
$\sum_{k=1}^{n} \binom{n}{k} \binom{k}{1}$: pick a group of $k$ people, and pick one of the $k$ people to be a leader
$\binom{n}{1}2^{n-1}$: pick one person to be a leader, then pick $k-1$ other people to be members only.
## Rigorous Proof
`\begin{proof}`
We have $n$ students. We want to count \# of study-groups such that each group has a chosen leader. On one hand, we have $\binom{n}{1}$ ways to select a leader and $2^{n-1}$ ways ot select remaining group members.

Alternatively, \# ways to select $k$-member study-group with a chosen leader is $\binom{n}{k}\binom{k}{1}, k \geq 1,\dots,n$. By the addition principle, we have $\sum_{k=1}^{n}\binom{n}{k}\binom{k}{1}$ ways in total.

Thereore,
$$
\begin{align}
\binom{n}{k}2^{n-1} = \text{\# study-groups with a chosen leader} = \sum_{k=1}^{n} \binom{n}{k}\binom{k}{1}
\end{align}
$$

`\end{proof}`

## Vandermont's identity
$$
\begin{align}
\sum_{k=0}^{m} \binom{m}{k}\binom{n}{r-k} = \binom{m+n}{r}
\end{align}
$$
`\begin{proof}`
We have a group of $m$ men and $n$ women. We want to select a group of $r$ people.

On one hand, we can select $r$ people from the total $m+n$ people in $\binom{m+n}{r}$ ways.

Alternatively, we can first select $k$ men and $r-k$ women in $\binom{m}{k}\binom{n}{r-k}$ ways, for all $0 \leq k \leq m$. By the addition principle, $\sum_{k=0}^{m} \binom{m}{k}\binom{n}{r-k}$.

Therefore,
$$
\begin{align}
\sum_{k=0}^{m} \binom{m}{k}\binom{n}{r-k} = \text{\# ways to select k people} = \binom{m+n}{r}
\end{align}
$$

`\end{proof}`

## Extension of Pascal's identity

$$
\begin{align}
\frac{P(n,k)}{k!} = \binom{n}{k}= \frac{n!}{k!(n-k)!} = \frac{n(n-1)\dots(n-k+1)}{k!}
\end{align}
$$

For any real \# $\alpha$, integer $k \geq 0$
$$
\begin{align} \\
\binom{\alpha}{k} = alha
\binom{-1}{k} = \frac{(-1)(-2)\dots(-k)}{k!} \\
\frac{(-1 * -1 * \dots -1) * (1 * 2 * 3 *\dots * k)}{k!} \\
\boxed{ = (-1)^{k} }
\end{align}
$$




$$
\begin{align}
\binom{\frac{1}{2}}{k}=\frac{\frac{1}{2} * -\frac{1}{2} * -\frac{3}{2}}{k!} \\
=\frac{1 * -1 * -3 * -5 * \dots * -(2k-3)}{2^{k}*k!} \\
\boxed{ \binom{\frac{1}{2}}{k}=(-1)^{k-1} * \frac{(2k-3)!!}{2^{k}*k!} }
\end{align}
$$

$$
\begin{align} \\
\alpha \in \mathbb{R}, k \in \mathbb{Z} \to \\
\binom{\alpha}{k} = \left\{ \begin{array}{rc}
\frac{\alpha*(\alpha-1)*(\alpha-2)*\dots*(\alpha-k+1)}{k!}  & k \geq 1\\
1 & k = 0 \\
0 & k < 0 \\
\end{array}\right.
\end{align}
$$

Extension of pascal's identity
$$
\begin{align}
\binom{r}{k} = \binom{r-1}{k} + \binom{r-1}{k-1} \\
\binom{r}{k}= \binom{r}{r-k}
\end{align}
$$
verify these algebreically

### applications of pascal's formula
Two identities by repeatedly appplying pascal's identity to itself (one for its first term, one for its second term)

*Remark:* $\binom{r}{r} = \binom{r}{r-k}$ does NOT apply for $r \in \mathbb{R}$.
TODO: prove why? (topic for next lecture)

#### Expanding Second term
$$
\begin{align}
\binom{r}{k} = \binom{r-1}{k} + \binom{r-1}{k-1} \\
= \binom{r-1}{k} + (\binom{r-2}{k-1} + \binom{r-2}{k-2}) \\
= \binom{r-1}{k} + \binom{r-2}{k-1} + \left(\binom{r-3}{k-2}+\binom{r-3}{k-3}\right) \\
\dots \\
= \binom{r-1}{k} + \binom{r-2}{k-1} + \binom{r-3}{k-2} + \dots + \binom{r-k+1}{0}
\end{align}
$$
Now replace $r$ with $r+k+1$

$$
\begin{align}
\binom{r+k+1}{k} = \binom{r+k}{k} + \binom{r+k-1}{k-1} + \dots + \binom{r}{0} \\
\boxed{ \sum_{i=0}^{k} \binom{r+i}{i} = \binom{r+k+1}{k} }
\end{align}
$$

*Remark:* The above formula applies for any $r \in \mathbb{R}$.

For $r \in \mathbb{Z}$ the following applies
$$
\begin{align}
\boxed{ \sum_{i=0}^{k} \binom{r+i}{r} = \binom{r+k+1}{k} }
\end{align}
$$
But NOT for $r \in \mathbb{R}$ since $\binom{r}{k} = \binom{r}{r-k}$ also does not work for $r \in \mathbb{R}$.

#### Expanding first term
$$
\begin{align}
\binom{r}{k} = \binom{r-1}{k} +\binom{r-1}{k-1} \\
= \left( \binom{r-2}{k}+ \binom{r-2}{k-1} \right)  + \binom{r-1}{k-1} \\
= \left( \binom{r-3}{k} + \binom{r-3}{k-1} \right)  + \binom{r-2}{k-1} + \binom{r-1}{k-1} \\
\dots  \\
\binom{r}{k} = \binom{0}{k-1} + \binom{1}{k-1} + \dots +  \binom{r-2}{k-1} + \binom{r-1}{k-1}  \\
\end{align}
$$
Now replace $r$ with $n+1$ and $k$ with $k+1$
$$
\begin{align}
\binom{n+1}{k+1} = \binom{0}{k} + \binom{1}{k} + \dots + \binom{n}{k} \\
\boxed{ \sum_{i=0}^{n} \binom{i}{k} = \binom{n+1}{k+1} \\ }
\end{align}
$$

