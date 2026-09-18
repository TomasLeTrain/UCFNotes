*Remark:* Independence != disjoint. Two events can happen at the same time and be independent of each other.


### Example - different chess problem solve
*problem:*  probabilityof rolling a sum of 5 before a sum of 7

combinatorial approach counted all valid states over sample space.

with independent probabilities it can be solved as well:
$$
\begin{align}
P(\text{1st is not either}) = \frac{26}{36} \\
P(\text{2st is not either}) = \frac{26}{36} \\
\dots
P(\text{$(i-1)$st is not either}) = \frac{26}{36} \\ 
P(\text{i is 5}) = \frac{4}{36} \\ \\
\end{align}
$$
Since all these events are independent:
$$
\begin{align} \\
P(\text{1st not either} \cap \text{2st not either} \cap \dots \cap \text{i is 5})  \\
= P(\text{1st not either}) * P(\text{2st not either})*\dots*P(\text{i is 5})  \\
= \frac{26}{36} * \frac{26}{36} * \dots * \frac{4}{36} \\
\to \boxed{ \left( \frac{26}{36} \right)^{i-1}* \frac{4}{36} }
\end{align}
$$

# Conditioning in a probability
$P(\cdot | F)$ is a probability:
1. $P(S | F) = 1 \to P(S) = 1$
2. $P(E^{C} | F) = 1 -  P(E | F) \to P(E_{C}) = 1 - P(E)$
3. $E_{i} \cap E_{j} = \emptyset, i \neq j, P\left( \bigcup_{i=1}^{\infty} E_{i} | F \right) = \sum_{i=1}^{\infty} P(E_{i}|F) \to \dots$

All rules apply same as before (consider if $F = S$, then all conditionals collapse to being without conditioning). 

## Proofs
Assume $P(F) > 0$
### Proof 1
$$
\begin{align} \\
P(SF) = F \to \\
P(S|F) = \frac{P(SF)}{P(F)} = \frac{P(F)}{P(F)} = 1
\end{align}
$$
### Proof 2
$$
\begin{align}
P(E^{C} | F) =  \frac{P(E^{C}F)}{P(F)} =  \frac{P(E-EF)}{P(F)} = \frac{ P(F) - P(EF)}{P(F)} \\
= \frac{P(F)}{P(F)} - \frac{P(EF)}{P(F)} = \boxed{ 1- P(E|F) }
\end{align}
$$

### Proof 3
Given $E_{1},E_{2},\dots$ are disjoint events:
$$
\begin{align}
P(E_{1} \cup E_{2} \cup \dots | F) = \frac{P((E_{1} \cup E_{2} \cup \dots ) F )}{P(F)} \\
= \frac{P(E_{1} F \cup E_{2} F \cup E_{3} F \cup \dots )}{P(F)} \\
= \frac{P(E_{1} F) + P(E_{2}F) + \dots}{P(F)} \\
= \frac{P(E_{1} F)}{P(F)} + \frac{P(E_{2}F)}{P(F)} + \dots 
\boxed{ = P(E_{1}| F) + P(E_{2}|F) + \dots  }
\end{align}
$$

### Example
Suppose $P(AB) = P(A) P(B)$. Show that $P(AB | F) = P(A | F) P(B | F)$

$$
\begin{align}
P(AB| F) = \frac{P(ABF)}{P(F)} \\
\text{by distribution of intersection} \to  \\
= \frac{P((AF)(BF))}{P(F)}
\end{align}
$$


## Examples
### Example ?
*In answering a question on a multiple-choice test, a student either knows the answer or guesses. Let $p$ be the probability that the student knows the answer and $1-p$ be the probability that the student gueses. Assume that a student who guesses at the answer will be correct with probability $\frac{1}{m}$ where $m$ is the number of multiple-choice alternatives. What is the conditional probability that a student knew the answer to a question given that he or she answered it correctly?*

*Part 2: What is the conditinoal probability that the student guessed given that they answered correctly?*

Let $K$ be the event that the student knows the answer.
Let $C$ be the event that the question was answered correctly.

$$
\begin{align} \\
P(K) = p \\
P(K^{C}) = 1-p \\
P(K | C) = ? \\
P(C | K) = 1 \\
P(C | K^{C}) = \frac{1}{m} \\
 \\
P(K | C) = \frac{P(KC)}{P(C)} \\
P(C) = P(CK) = P(CK^{C}) = P(C | K)P(K) + P(C | K^{C})P(K^{C}) \to \\
P(K | C) = \frac{P(C | K)P(K) + P(C | K^{C})P(K^{C})} \\ \\
P(KC) = P(C | K)P(K) = 1 * p = p \to \\
P(K | C) = \frac{p}{P(C | K)P(K) + P(C | K^{C})P(K^{C})} \\ \\
P(K | C) = \frac{p}{1 * p + \frac{1}{m} * (1-p)} \\ \\ 
\boxed{ P(K | C) = \frac{p}{ p + \frac{1}{m} * (1-p)} \\ \\ }
\end{align}
$$
This is just direct application of bayes theorem.



### Example 4.28 (10th ed)
*5% of men + 0.25% of  women are color blind. A colorblind person is chosen at random. Whats the probability of this person being male? Assume = \# of males = females. What if the population had twice as many males as females.*

Let $C$ be the event that a person is colorblind.
Let $M$ be the even that a person is male.

$$
\begin{align} \\
P(M) = \frac{1}{2}, P(M^{C}) = \frac{1}{2} \\
P(C | M) = 0.05 \quad P(C | M^{C}) = 0.0025 \\
p(M | C) = ? \\ \\

P(M | C) = \frac{P(C|M)P(M)}{P(C|M)P(M) + P(C|M^{C})P(M^{C})} \\ \\

\boxed{ P(M | C) = \frac{0.05 \frac{1}{2}}{0.05 \frac{1}{2} + 0.0025 * \frac{1}{2} } \\ }
\end{align}
$$

### Example 4f
*An infinite sequence of independent trials is to be performed. Each trial results in a success with probability $p$ and a failure with probability $1-p$. What is the probability that* 
*A. at least 1 success occurs in the first $n$ trials;*
*B. Exactly $k$ successes in the 1st $n$ tirals*
*C. all trials result in success*

Let $S_{i}$ be the event the $n$th trial was successful.

#### 1
$$
\begin{align} \\
P(S_{1} \cup S_{2} \cup \dots \cup S_{n}) = 1 - P((S_{1} \cup S_{2} \cup \dots \cup S_{n} )^{C}) \\
= 1 - P(S_{1}^{C} \cap S_{2}^{C} \cap \dots \cap S_{n}^{C}) \\ \\
= 1 - (P(S_{1}^{C}) * P(S_{2}^{C}) * \dots * P(S_{n}^{C}) ) \\
P(S_{i}) = p, 0 \leq i \leq n  \to \\
P(S_{i}^{C}) = 1-p, 0 \leq i \leq n  \to \\
= 1 - ((1-p) * (1-p) * \dots * (1-p)) \\
\boxed{ = 1 - (1-p)^{n} }
\end{align}
$$

#### 2
$$
\begin{align}
p^{n}
\end{align}
$$

### Example 4j
Independent trials resulting in a success with probability $p$ and a failure with probabilty $1-p$ are performed. What is the probabilty that $n$ successes occur before $n$ failures? If we think of $a$ and $b$ as playing a game such that A gains 1 point when a success occcurs and $B$ gains 1 point when a failure occurs, then the desired probability is the probability with A

$$
\begin{align}
P(A\text{ wins}) = P(A \text{ wins $n$ matches in $n+m-1$ matches})
\end{align}
$$