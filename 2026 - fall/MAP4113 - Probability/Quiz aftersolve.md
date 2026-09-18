
other:
4 couples, place so none sit nex to each other

a together, $b$ together, $c$ together, $d$ together, ab, ac, ad, ...


Looking for
$$
\begin{align}
(A \cup B \cup C \cup D)^{C} =  S - (A \cup B \cup C \cup D) \\
S = \frac{8!}{2!2!2!2!}
\end{align}
$$

$$
\begin{align}
(A \cup B \cup C \cup D) = A + B + C + D - AB - AC - AD - BC - BD - CD + ABC + \dots
\end{align}
$$

$$
\begin{align}
\underbrace{ A = B = C = D }_{ \binom{4}{1} } = \frac{7!}{2!2!2!1!} = \frac{7!}{2!2!2!} \\
\underbrace{ AB = AC = \dots = CD }_{ \binom{4}{2} } = \frac{6!}{2!2!1!1!} = \frac{6!}{2!2!} \\
\underbrace{ ABC = ACD = \dots = BCD }_{ \binom{4}{3} } = \frac{5!}{2!1!1!1!} = \frac{5!}{2!} \\ \\
\underbrace{ ABC = ACD = \dots = BCD }_{ \binom{4}{4} } = \frac{4!}{1!1!1!1!} = 4! \\ \\
\to
\binom{4}{1} * \frac{7!}{2!2!2!} - \binom{4}{2} \frac{6!}{2!2!} + \binom{4}{3} \frac{5!}{2!} - \binom{4}{4} 4! \\ \\

\to \binom{4}{1} * \frac{7!}{2!2!2!} - \binom{4}{2} \frac{6!}{2!2!} + \binom{4}{3} \frac{5!}{2!} - \binom{4}{4} 4!
 \\
\sum_{i=0}^{3} \binom{4}{i+1} \frac{(7 - i)!}{2!^{3-i}} \\
= \sum_{i=0}^{3} \frac{4!}{(i+1)!(4-i-1)!} \frac{(7 - i)!}{2!^{3-i}} \\

\binom{4}{1} * \frac{7!}{2!2!2!} - \binom{4}{2} \frac{6!}{2!2!} + \binom{4}{3} \frac{5!}{2!} - \binom{4}{4} 4! \\ \\ \\
\end{align}
$$
Therefore the final answer is:
$$
\begin{align}
\boxed{ \frac{8!}{2!2!2!2!} - \sum_{i=0}^{3} (-1)^{n} \binom{4}{i+1} \frac{(7 - i)!}{2^{3-i}} }
\end{align}
$$
