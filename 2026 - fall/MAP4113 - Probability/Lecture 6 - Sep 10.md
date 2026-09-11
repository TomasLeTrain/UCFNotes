## Homework example
A class has 50 juniors, 70 seniors, 20% of the juniors failed the class, 30% of the seniors failed the class
1. what is the probability that a randomly chosen student passed the class?
2. given that a student passed the class, what is the probabily that the student is a junior?


### Answers 
#### 1
$$
\begin{align}
50 * 0.20 + 70 * 0.3 = 10 + 21 = 31 \text{failed students} \\
\to 120 - 31 = 89 \text{passing students}
\end{align}
$$

#### 2
Let $J$ be the event that a student is a junior, and let $E$ be the event that a student passed the class:
$$
\begin{align}
P(J | E) = \frac{P(EJ)}{P(E)} \\ \\
P(E^{C} | J) = 0.2 \to \text{given} \\
\to P(E | J) = 0.8 \\ \\ \\

P(E | J) = \frac{P(EJ)}{P(J)} \\
P(EJ) = P(E | J) * P(J) \\
P(EJ) = 0.8 * \frac{50}{120} = \boxed{ \frac{40}{120} } \\ \\
\to
P(J | E) = \frac{\frac{40}{120}}{\frac{89}{120}} = \boxed{ \frac{40}{89} }
\end{align}
$$

Another property (can prove from axioms or conditional formula above):
$$
\begin{align}
\boxed{ P(E | J) = 1 - P(E^{C} | J) }
\end{align}
$$

## Example
Cathy decides to take probability on graph theory. She estimates that the prob of getting an A in prob is $\frac{2}{3}$. Of the porb of her getting an $A$ in grap htheory as $\frac{1}{4}$. She flips an unfair coin that is A times as likely to show hands as it is to show tails. If she sees a head she will take probability, tails she will take graph theory. What is the prob she gets an A in probability?

Let $W$ be the event that she takes probability, and let $A$ be the event that she gets an A, and let $G$ be the event that the coin says she takes probability. Therefore:
$$
\begin{align}
P(A | W) = \frac{2}{3} \to \text{given}\\
P(A | W^{C}) = \frac{1}{4} \to \text{given} \\ \\

P(W) = \frac{4}{5} \\
P(W^{C}) = \frac{1}{5} \\ \\
 \\
P(A | W) = \frac{P(A W)}{P(W)} \\ \\
P(A W) = P(A | W) * P(W)  \\ \\
\boxed{ P(A W) = \frac{2}{3} * \frac{4}{5} }  \\ \\


\end{align}
$$

# Bayes Theorem
$$
\begin{align}
E = EF \cup EF^{C} \\
P(E) = P(EF) + P(EF^{C}) \\
= P(E | F)P(F) + P(E | F^{C})P(F^{C}) \\
= P(E | F)P(F)  + P(E | F^{C})(1-P(F)) \\ \\

P(F|E) = ? \\
P(F | E) = \frac{P(EF)}{P(E)} = \frac{P(E | F)P(F)}{P(E | F) P(F) + P(E | F^{C})P(F^{C})}
\end{align}
$$
