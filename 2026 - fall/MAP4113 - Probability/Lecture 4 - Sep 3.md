w### Example
3 couples (6 people total) are placed in a row, what is the prob that no two adjacent people are a couple?

4 people case:
$$
\begin{align}
A B A B \to 1 * 2! * 2! \\
B A B A \to 1 * 2! * 2! \\
\to 2 * 2 * 2 = \boxed{ 8 }
\end{align}
$$

## Induction approach
Insert between already chosen people from 4 people case
$$
\begin{align}
8 * \binom{5}{2} * 2
\end{align}
$$
However after insertion there are new choices, so it doesn't work!

## Complement/Inc-Exc approach
Let each couple be labed $A,B,C$, and let some $G_{i}$ to mean the $i$th person frmo the  $G$th couple.

Let $A$ be the event that couple A is seated together, similarly let $B$ be the event that couple $B$ is seated together, and same for $C$.

Therefore, the solution to the problem is
$$
\begin{align}
P((A \cup B \cup C)^{C}) \\
= 1 - P(A \cup B \cup C)
\end{align}
$$
$$
\begin{align}
P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(AB) - P(AC) + P(ABC)
\end{align}
$$


$$
\begin{align}
|A| = |B| = |C| = 5! * 2 \to \text{merge couple, can swap} \\
|AB| = |AC| = |BC| = 4! * 2 * 2 \to \text{merge couples, can swap each} \\
|ABC| = 3! * 2 * 2 * 2 \to \text{merge couples, can swap each} \\ \\ \\
\end{align}
$$
Therefore

$$
\begin{align}
|A \cup B \cup C| = 3 * (5! * 2) - 3 * (4! * 4) + 3! * 8 \\ \\
\boxed{ P(A \cup B \cup C) = \frac{3 * (5! * 2) - 3 * (4! * 4) + 3! * 8}{6!} }
\end{align}
$$


## Hat problem
*Suppose that each of $N$ men at a party throws his hat into the center of the room. The hats are first mixed up, and then each man randomly select a hat. What is the probability that none of the men selects his own hat?*

Let's fix the order of the men.
Let $H_{i}$ be the event that the $i$th man got their hat back.

The answer then becomes
$$
\begin{align}
P((H_{1} \cup H_{2} \cup H_{3} \cup  \dots H_{n} )^{C})
= 1 - P(H_{1} \cup H_{2} \cup H_{3} \cup  \dots H_{n})
\end{align}
$$

$$
\begin{align}
P(H_{1} \cup H_{2} \cup H_{3} \cup  \dots H_{n}) = \\
\sum_{i=1}^{N} P(H_{i})
- \sum_{1 \leq i_{1} < i_{2} \leq N} P(H_{i_{1}}H_{i_{2}})
+ \sum_{1 \leq i_{1} < i_{2} < i_{3} \leq N} P(H_{i_{1}} H_{i_{2}} H_{i_{3}}) 
- \dots \\
\end{align}
$$
$$
\begin{align}
P(H_{i}) = \frac{1}{N} \\
\end{align}
$$
Therefore
$$
\begin{align}
\sum_{i=1}^{N} P(H_{i}) = N * \frac{1}{N} \to \text{$n$ number of way to pick one } \\
\sum_{1 \leq i_{1} < i_{2} \leq N} P(H_{i_{1}}H_{i_{2}}) = \binom{n}{2} * \frac{1}{n(n-1)}
\end{align}
$$

Until the last element is
$$
\begin{align}
\binom{n}{n} * \frac{1}{n(n-1)(n-2)\dots(1)} \\
= 1 * \frac{1}{n!}
\end{align}
$$


So the final sum becomes:
$$
\begin{align}
\sum_{i=1}^{N} P(H_{i}) = N * \frac{1}{N} = 1 \\
\sum_{1 \leq i_{1} < i_{2} \leq N} P(H_{i_{1}}H_{i_{2}}) = \binom{n}{2} * \frac{1}{n(n-1)} = \frac{\cancel{ n(n-1) }}{2!} * \frac{1}{\cancel{ n(n-1) }} = \frac{1}{2!} \\ \\

\dots = \binom{n}{r+1} * \frac{1}{n(n-1)\dots(n-r-1)} \\
= \frac{\cancel{ n(n-1)(n-2)\dots(n-r) }}{r!} * \cancel{ \frac{1}{n(n-1)\dots(n-r) }} \\
= \boxed{ \frac{1}{r!} }
\end{align}
$$
Note: whole sum is basically $\frac{1}{n!}$ written out with signs, and it approaches $e^{-1}$.



## 20
*Suppose that you are playing blackjack against a dealeer. In a freshly shuffled deck, what is the probability that neither you nor the dealer is dealt a blackjack?*

To make a blackjack you need a 10/jack/queen/king (16 choices) and an ace (4 choices)


Let $Y$ be the event that I get blackjack. Let $D$ be the event that the dealer gets a blackjack. Then
$$
\begin{align}
P(Y^{C}D^{C}) = P((Y \cup D) ^{C}) = 1 - P(Y \cup D) \\
\end{align}
$$
$$
\begin{align}
P(Y \cup D) = P(Y) + P(D) - P(YD) \\
P(Y) = \frac{4 * 16}{\binom{52}{2}} \\
P(D) = \frac{4 * 16}{\binom{52}{2}} \\
P(YD) = \frac{4 * 16 * (3 * 15)}{\binom{52}{2} \binom{50}{2}}
\end{align}
$$
