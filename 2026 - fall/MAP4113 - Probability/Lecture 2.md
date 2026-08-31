# Chapter 2 - Axioms of Probability
## 2.2
Consider an experiment whose outcome is not known, but you do know the set of all possible outcomes.

**Sample Space** - The set of all possible outcomes of an experiment

**Event** - Any subset of the sample space

Given $n(E)$ denoting the number of times $E$ happens after performing the experiment $n$ times, the probability of $E$ happening can be approximated/found by:
$$
\begin{align}
P(E) = \lim_{ n \to \infty } \frac{n(E)}{n} \\
n(E) = n_{E}
\end{align}
$$

## Axioms of probability
Axiom 1: $0\leq P(E) \leq 1$ (any probability of an event is between 0 and 1).
Axiom 2: $P(S) = 1$ (the probability of the sample space is always 1).
Axiom 3: For any sequence of **mutually exclusive(disjoint)** events $E_{1},E_{2},\dots$
$$
\begin{align}
(E_{i} \cap E_{j}=E_{i}E_{j}=\emptyset \text{if} i \neq j) \\
P\left( \bigcup_{i=1}^{\infty}E_{i} \right) = \sum_{i=1}^{\infty} P(E_{i})
\end{align}
$$
we refer to $P(E)$ as the probability of $E$.



**Example:** prove $P(\emptyset) = 0$:
$$
\begin{align}
E_{1} = S, E_{2} = \emptyset, E_{3}=\emptyset, \dots \\
\bigcup_{i=1}^{\infty}E_{i} = S \cup \emptyset \cup \emptyset \cup \dots = S \\
P\left( \bigcup_{i=1}^{\infty}E_{i} \right) = P(S) = 1 \\
P\left( \bigcup_{i=1}^{\infty}E_{i} \right) = \sum_{i=1}^{\infty} P(E_{i}) \\
1 = \sum_{i=1}^{\infty} P(E_{i}) \\
1 = P(S) + P(\emptyset) + P(\emptyset) + \dots \\
1 = 1 + P(\emptyset) + P(\emptyset) + \dots \\
0 = P(\emptyset) + P(\emptyset) + \dots \\
\boxed{ P(\emptyset) = 0 }
\end{align}
$$


Can extend axiom 3 by appending infinite number of $\emptyset$ after the finite series of events (requires already proving $P(\emptyset) = 0$.

**Example:** Show $P(\bar{A}) = 1-P(A)$:
$$
\begin{align}
\bigcup E_{i} = A \cup \bar{A} = S\\
P(\bigcup E_{i}) = P(S) = 1 \\
P(\bigcup E_{i}) = \sum P(E_{i}) = P(A) + P(\bar{A}) \\

1 = P(A) + P(\bar{A}) \\
\boxed{ P(\bar{A}) = 1 - P(A) }
\end{align}
$$


1. 10 people sit in a row
2. 10 people set at a round table
how many ways to seat people for each room?

for 1 its 10!
for 2 its $\frac{10!}{10}=9!$  (circular permutations)