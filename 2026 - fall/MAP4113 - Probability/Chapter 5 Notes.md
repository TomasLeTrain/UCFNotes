> [!definition] Continuous random variable
> A random variable $X$ is a **continuous random variable** if it is continuous :)

Given a continuous rv $X$ with **probability density function** $f$, then for all $B \subset \mathbb{R}$:
$$
\begin{align}
P(X \in B) = P\{ w \in S : X(w) \in B \}
P(X \in B) = \int_{B} f(t)dt
\end{align}
$$
(basically a summation over all reals $w$ for which $w \in S : X(w) \in B$).


???


# 4.7 - Random process
When random events happen at some random, fixed points in time, the \# of occurances of such events in intervals of time can be modeled as a **Poisson Process**.

For $\lambda > 0 : N(t) =$ \# of events occuring in some interval of time $t$.

So, a Poisson process $N$ with rate $\lambda$ is:
$$
\begin{align}
N = \{N(t) :  t \geq 0 \}
\end{align}
$$

*Remarks:*
- $N(0) = 0$
- $N(t) \approx \text{Poisson}(\lambda t)$
- $N(t) - N(S) \approx \text{Poisson}(\lambda (ts))$ - number of events that happen in interval $(S,t]$
- $N$ has independent increments $0 < t_{1} < t_{2} < \dots < t_{n} \implies N(t_{1}), N(t_{2}) - N(t_{1}),\dots, N(t_{n}) - N(t_{n-1})$ are all independent random variables.

TODO: add theorem from notes

## Example 7e
Suppose that earthquakes occur in the western portion of the United States in accordance with assumptions 1,2, and 3, with $\lambda = 2$ and with 1 week as unit of time. (That is earthquakes occur at a rate of 2 per week).
a. Find the probability that at least 3 earthquakes occur during the next $2$ weeks.
b. Find the probability distribution of time, starting from now, until the next earthquake.

### a

