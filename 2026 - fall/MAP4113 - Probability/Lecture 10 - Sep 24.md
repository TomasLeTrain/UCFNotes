# Chapter 4
## 4.1 Random variables
**Definition:** Random variable is a function $S \to \mathbb{R}$, i.e. every outocme in the sample space is given a number (can be many-to-one).

### Example 
$X$ is the product of the value of 2 rolls of a fair die. Find:
1. Possible values that $x$ can be 
2. Probability that $x$ is an odd \#
3. For each value you found in 1., find probability $X=$ that value
4. Find th prob that $x$ is $\leq 13.24$
5. Find the prob that $x \leq 12.95$
6. Graph the function F(a)= $P(X <=a)$ for all $a \in \mathbb{R}$.

#### 1.
All products of pairs $\{ (1,1),(1,2),\dots,(1,6),(2,1),(2,2),\dots, (6,6)\}$

Table with all possible outcomes:
![[Lecture 10 - Sep 24 2026-09-24 12.13.49.excalidraw]]

#### 2. 
Consider the event that the product is 11
$$
\begin{align}
P(X = 11) = P(\text{event that $X=11$}) =P(w \in S : X(w) = 11) = P(\emptyset) = 0 \\
\end{align}
$$

All odd numbers in table:
pattern of every 2 numbers down and every 2 numbers right, total 9 out of all possible 36 outcomes:
$$
\begin{align}

P(\text{X is odd}) = P(\{ w \in S | X(w) \text{ is odd} \} ) =  \boxed{ \frac{9}{36} }
\end{align}
$$
Another way to obtain is 9 is to consider that the product is only odd if both products are odd.
The probability the row/col is odd is 3/6, and both can be considered as independent events, so $P(AB) = P(A)P(B) \to \frac{3}{6} * \frac{3}{6} = \boxed{ \frac{9}{36 }}$

#### 3.
Probability for each pair is $\frac{1}{36}$. If we want to find the probability for some number $n$, we can add the probabilities of all distinct pairs that give that value (all are mutually exclusive to each other).

## General notes
Different notations for same thing:
$$
\begin{align}
P(x) = P(X = x) = P(\{ w \in S: X(w) = x \}) = P_{X}(x)
\end{align}
$$
Basically probability that applying $X$ to $S$ gives some number $x$.


## Cumulative Distribution Function (CDF)
Summation of all probabilities up to $x$.
$$
\begin{align}
CDF_{X}(a) = P(\{ w \in S : X(w) \leq a \}) = \sum_{x \leq a} P(x)
\end{align}
$$

From this we can see that 
$$
\begin{align}
\lim_{ a \to -\infty } CDF_{X}(a) \to 0 \\
\lim_{ a \to \infty } CDF_{X}(a) \to 1
\end{align}
$$
Jumps, in the function only happen at points that are in the range of $S$.

Also, individual probabilities can be found from the CDF by $CFD(a) - CDF(b)$, where $b$ is the element preceding $a$ in $S$.

## 4.2 Discrete random variables
**Definition:** A random variable that can take on at most countably many values is said to be discrete

\# of rolls it takes to get a 6:
$$
\begin{align}
\{ 1,2,\dots,\infty \}
\end{align}
$$
Still discrete even if it can fill an infinite number of values (value is not continuous).

### Probability mass function
**Definition:** probability at any point $x$. In other words, $P(x)$

## Example
The random variable, $X$, given in the example below:
You have a well shuffled deck of cards. You keep all the 52 cards face down in a stack and continue to pick the top card and turn it over one at a time until you see a card that is not a face card (not a $J$, $Q$, or $K$). (You do not replace the turned over cards to the deck.)
Let $X =$ \# of cards you need to turn over to see a card that is not $J$, $Q$, or $K$.

The range of $X$ is $[1,13]$.

# 3.44 example
Let $A,B,C$ be the event that $A,B,C$ gets executed
Let $I$ be the event that $A$ gets told who is getting executed:
$$
\begin{align}
P(A) = P(B) = P(C) = \frac{1}{3} \\
P(A | B^{C}) = \frac{P(AB^{C})}{P(B^{C})} = \frac{P(A)}{P(B^{C})} = \frac{\frac{1}{3}}{\frac{2}{3}} = \frac{1}{2} \\
P(A | C^{C}) = \frac{1}{2} \\
\end{align}
$$

## 3.