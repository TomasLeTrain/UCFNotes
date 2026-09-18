# PP (Simple Form)
If $n+1$ or more objects are placed into $n$ boxes, then some box contains two or more of the objects.

## Example 1
GIven $m$ integers $a_{1},\dots, a_{m}$, prove that there exists a consecutive $a_{i}$'s (subsequence) whose sum is divisble by $m$.

That is, $\exists\ 0 \leq h < k \leq m$ s.t. $a_{n+1} + \dots + a_{k}$ is divisible by $m$.

### Scratch work
pigeon holes: remainders -> $0,1,\dots,m-1$
pigeons: $\text{sum} \mod m$, where sum is of the form:
$$
\begin{align}
a_{1}, a_{1} + a_{2} , a_{1} +a_{2}+ \dots + a_{m}
\end{align}
$$

### Proof
Consider the $m$ sums of the form $a_{1}, a_{1} + a_{2}, \dots, a_{1} + a_{2} + \dots + a_{m}$.
Divide these $m$ integers by $m$ and get their remainders:
$$
\begin{align}
a_{1}+\dots+a_{i} = q_{i} m + r_{i},\ 0 \leq r_{i} \leq m-1,\ i=1,\dots,m
\end{align}
$$

If one of the remainders $r_{1},\dots,r_{m}$ is 0, then we are done by taking $h=0$. 
We may assume $1 \leq r_{i} \leq m-1$ for each $i$.
By the PP, $r_{i} = r_{j}$ for some $i <j$.

It follows that 
$$
\begin{align}
\left( a_{1}+\dots+a_{i}+a_{i+1}+ \dots + a_{j} \right) - \left( a_{1} + a_{2}  + \dots + a_{i} \right)  \\ \\
= \left( q_{j}m + r_{j} \right)  - (q_{i}m + r_{i}) \\
= (q_{j}- q_{i})m \\
\end{align}
$$

Let $h = i$ and $k = j$. Then $a_{k+1}+ \dots + a_{j}$ is divisible by $m$.
$\square$

## Example 2
Given the integers
$1, 2, \dots, 200$, we choose $101$ integers. Prove that among the integers chosen, there are two such that one of them is divisble by the other.

### Scratch Work
For each $a_{i} \in \{ 1,\dots,200 \}$.
$a_{i} = n_{i} * a^{k_{i}}$, where $2 \nmid n_{i}$, $k_{i} \geq 0$ integer.
$n_{i}$ is odd (otherwise $k_{i}$ would change to include the $2$).

### Proof
After factoring out as many 2's as possible, each of the chosen integers can be written as 
$2^{k}a$, where $a\geq 1$ is an odd number and $k \geq 0$ is an intgere.
Thus, $S =\{ 1,3,5,\dots, 199\},  a \in S$
Let the 101 chosen integers be 
$$
\begin{align}
2^{k_{1}}a_{1}, 2^{k_{2}}a_{2},\dots, 2^{k_{101}}a_{101}
\end{align}
$$
Where $a_{1},\dots,a_{101} \in S$, and $|S| = 100$.
By the PP, $a_{i}= a_{j}$ for some $i \neq j$

Then $2^{k_{i}}a_{i} \mid 2^{k_{j}} if k_{i} \leq k_{j}$ and $2^{k_{j}} a_{j} \mid 2^{k_{i}} a_{i}$ if $k_{i} > k_{j}$.
$\square$
*Remark:* The 101 number cannot be reduced, because then all numbers between $101,\dots,200$ can get picked, and none can divide each other.
## Example 3
A chesss master who has 11 weeks to prepare for the tournament decided to play at lesat one game every day, but to avoid tiriing himself, he decides not to play more than 12 games during any calendar week. Prove that $\exists$ a number of consecutive days during which the chess master will have played exactly 21 games. 

### Proof
Let $a_{k}$ = total \# of games played on day 1, ..., day $k$, for the 1st $k$ consecutive days.
$$
\begin{align}
a_{1} \geq 1,a_{2} \geq 2, \dots, 7 \leq  a_{7} \leq 12
\end{align}
$$
$a_{1},a_{2},\dots,a_{77}$ is a strictly increasing sequence.
$$
\begin{align}
77 \leq a_{77} \leq 11*12=132
\end{align}
$$

Now create the sequence:
$a_{1},\dots,a_{77},a_{1} + 21, \dots, a_{77} + 21$
154 numbers, $1 \leq a_{1}, \dots, a_{77} + 21 \leq 132+21 = 153$

By the PP, two of them must be the same. Since both sequences $a_{1},\dots,a_{77}$ and $a_{1}+21,\dots,a_{77} + 21$ are strictly increasing, any two elements that are equal must come from a different sequence. Thus, we see that $a_{i} =a_{j} + 21$ for some $i > j$. Then $a_{i} - a_{j} = 21$.

## Example 4 - The Chinese Remainder Theorem
Let $m$, $n$ be relatively prime positive integers $0 \leq a < m$, $a \leq b < n$. Then $\exists$ an integer $x$ such that $x = pm + a = qn+b$ for some integers $p,q$. (In other words, $x \mod m \equiv a, x \mod n \equiv b$)


### Scratch work
Create two sets of numbers: ones that satisfy $x = pm + a$ and another that satisfies $x = pn + b$. Then, use PP to show that they overlap.

### Proof
Consider the $n$ integers $a,m+a, \dots, (n-1) * m + a$. Each has a remainder $a$ when divided by $m$.

Now divide each of the $n$ integers by $n$. We claim that no two have the same remainder, therefore one must be $b$.
Suppose two have the same remainder:
$$
\begin{align} \\
i < j,  \\
im + a  & = q_{i} n + r \\
jm + a  & = q_{j} n + r \\
(j-i)m  & = (q_{j} - q_{i}) n \\
\implies j-i \mid n \\
q_{j} - q_{i} \mid m
\end{align}
$$
A contraction.
$\square$.