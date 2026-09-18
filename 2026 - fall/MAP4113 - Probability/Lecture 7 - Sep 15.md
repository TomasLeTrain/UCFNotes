
Suppose that we have 3 cards that are identical in form, except that both sides of the first card are colored red, both sides of the 2nd card are colored black, and one side of the 3rd card is black and one side is red. The three cards are mixed up in a hat, and 1 card is randomly selected and put down on the ground. If the uppoer side of the chosen card is red what is the prob the other side is black?

$$
\begin{align}
R = \text{side of card up is red} \\
B = \text{side of card up is black} \\ \\
D = \text{2 sided red is chosen} \\
N = \text{0 red-card is chosen} \\
O = \text{1 red-card is chosen} \\
   \\
 P(R | N) = 0 \\
 P(R | D) = 1 \\
 P(R | O) = \frac{1}{2} \\ 
 P(N) = P(D) = P(O) = \frac{1}{3} \\ \\
 
 P(O | R) = ? \\ \\ \\
 S = D \cup N \cup O \to \\
 S \cap R  = (D \cup N \cup O) \cap R \to \\
R = RD \cup RN \cup RO \to \\
 P(R) = P(R | N)P(N) + P(R | D)P(D) + P(R | O)P(O) \\ \\
 P(O | R) = \frac{P(R | O) P(O)}{P(R | N)P(N) + P(R | D)P(D) + P(R | O)P(O)} \\
 = \frac{\left( \frac{1}{2} * \frac{1}{3} \right)}{\frac{1}{2} * \frac{1}{3} + 1 + \frac{1}{3} + 0 + \frac{1}{3}}
 = \frac{\frac{1}{6}}{\frac{1}{6} + \frac{1}{3}}
 = \frac{1}{1 + 2} = \boxed{ \frac{1}{3} }
\end{align}
$$



## Example ?
You have 8 different dice in your pocket:
- 4 of them are fair
- 1 of them has 2 1's, 2 2's, and 2 3's
- 3 of them show all odd \#'s with = prob,
	- show all even \#'s with = prob,
	- An odd \# is twice as likely to appear as an even \#.
You pick a die from your pocket & roll it twice.
### A
Find the prob that the sum of the 2 rolls is $= 4$.

Let $T_{1}$ be the event that a type 1 (fair die) die is picked.
Let $T_{2}$ be the event that a type 2 (duplicated $1 \dots 3$) die is picked.
Let $T_{3}$ be the event that a type 3 (3 different types of die) is picked.

$$
\begin{align}
P(i | T_{1}) = \frac{1}{6}, i = 1\dots 6 \\
P(i | T_{2}) = \frac{1}{3}, i = 1\dots 3 \\
P(i | T_{3}) = \frac{1}{9}, i = 2,4,6 \\
P(j | T_{3}) = \frac{2}{9}, j = 1,3,5 \\
 \\ \\
 P(1 \cup 2 \cup \dots \cup 6 | T_{1}) = 1 \\
 P(1 \cup 2 \cup \dots \cup 6 | T_{2}) = 1 \\
 P(1 \cup 2 \cup \dots \cup 6 | T_{3}) = 1 \\
\end{align}
$$

Let $S_{i}$ denote the even that a sum of $i$ after two rolls is achieved. Then, then answer we are looking for is
$$
\begin{align}
P(S_{4})
\end{align}
$$

Thus,
$$
\begin{align}
P(S_{4}) = P(S_{4} | T_{1}) + P(S_{4} | T_{2}) + P(S_{4} | T_{3}) \\ \\

P(S_{4} | T_{1}) = P(1 \cap 3 | T_{1}) * 2 + P(2 \cap 2 | T_{1}) * 2 \\
P(S_{4} | T_{1}) = \frac{2}{36} + \frac{2}{36} = \frac{4}{36} \\ \\
 \\
P(S_{4} | T_{2}) = P(1 \cap 3 | T_{2}) * 2 + P(2 \cap 2 | T_{2}) * 2 \\
P(S_{4} | T_{2}) = \frac{2}{9} + \frac{2}{9} = \frac{4}{9} \\ \\
 \\
P(S_{4} | T_{3}) = P(1 \cap 3 | T_{3}) * 2 + P(2 \cap 2 | T_{3}) * 2 \\
P(S_{4} | T_{3}) = \frac{8}{81} + \frac{2}{81} = \frac{10}{81} \\ \\

\boxed{ P(S_{4}) = \frac{4}{36} + \frac{4}{9} + \frac{10}{81} } \\ \\
\end{align}
$$


### B
Find the prob that the die is fair given that the sum of the 2 rolls is $\leq 4$


# 3.4 Independent Events
Definition: Events $A$ & $B$ are said to be independent iff $P(AB) = P(A)P(B)$

Therefore, if $A$ & $B$ are independent:
$$
\begin{align}
P(EF^{C}) =  P(E) P(F^{C}) \\
P(E^{C}F) =  P(E^{C}) P(F) \\
P(E^{C}F^{C}) =  P(E^{C}) P(F^{C})
\end{align}
$$

Also, if they are independent:
$$
\begin{align}
P(A | B) = P(A) \\
P(A^{C} | B) = P(A^{C}) \\
\end{align}
$$

Meaning if $P(B) > 0$:
$$
\begin{align} \\
P(A|B) = P(A) \\
\frac{P(AB)}{P(B)} = P(A) \Longleftrightarrow P(AB) = P(A)P(B) \\
\end{align}
$$


$$
\begin{align}
P(E_{1})  = \frac{1}{r} \\ \\
P(E_{2}) = \frac{1}{r-1} \to P(E_{1}^{C}E_{2}) = \frac{r-1}{r}* \frac{1}{r-1} = \frac{1}{r} \\
P(E_{3}) = \frac{1}{r-2} \to P(E_{1}^{C}E_{2}^{C}E_{3}) = \frac{r-1}{r}*\frac{r-2}{r-1}* \frac{1}{r-2} = \frac{1}{r} \\
\dots
\end{align}
$$
