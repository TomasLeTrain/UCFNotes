Recall [[Lecture 11 - Oct 5#^a39303]]
## Review and corrections

A corrected definition of total order:
> [!definition] Linear/Total Order
> A **linear order/total order**I is a partial order where each pair of elements in $X$ is comparable.

> [!definition] Equivalent relation
> a relation is an **equivalent relation** if its reflexive, symmetric, and transitive. Such a relation is denoted with $\sim$ 

> [!remark] Equivalence relation
> If $\sim$ is an equivalent relation on a set $X$, then $\{ [x] : x < X \}$ is a partition of $X$. Similarly, any partition of $X$ yields an equivalent relation on $X$.

An equivalent class is defined as the following:
$$
\begin{align}
\forall x \in X \\
[x] := \{ y \in X | x \sim y \} \\
[x] \neq \emptyset \text{ since } x \in [x] \\
[x] \cap [y] = \emptyset \text{ if } x \nsim y
\end{align}
$$


All the following are defined for a poset (partial order set) $P = (X, \leq)$:
- chain, antichain, maximal chain, maximal antichain

$X$ can be partitioned into chains or antichains, meaning, all elements of $X$ are in exactly one chain/antichain.

Let $P = (X, \leq)$ be a poset, where $X$ is finite. The largest antichain in $P$ has size $m$ and the largest chain in $P$ has size $n$. Let $C_{1},\dots, C_{r}$ be a chain partition of $X$ and $A_{1},\dots,A_{s}$ be an antichain partition of $X$.

**Observation:** 
1. $r \geq m$, since $|C_{i} \cap A| \leq 1$
2. $s \geq n$, since $|C \cap A_{i}| \leq 1$


**Practice Example**
Given poset $P = ([10],|)$
1. Draw the Hasse Diagram
2. Find the largest chain and antichain
3. partition $X$ into as few chain as possible antichains

![[Lecture 13 - Oct 12 2026-10-12 09.29.37.excalidraw]]

> [!theorem] Dilworth Theorem
> Let $P=(X,\leq)$ be a finite poset such that the largest antichain has size $m$ and the largest chain has size $n$. Then, $X$ can be partitined into exactly $m$ chains and $n$ antichains.
^102c9f

**True of False:**
1. Let $(X,\leq)$ be a poset and let $A$ be the set of all minimal elements of $X$. Then for every $y \in X - A$, there exists $x \in A$ such that $x \leq y$. -> **True**. 

`\begin{proof}`@[[#^102c9f]]
We need to construct an antichain partition of $X$ with exactly $n$ antichains.

Let $A_{1}$ be the set of all minimal elements of $P=(X,\leq)$.
$A_{2}$ be the set of all minimal elements of the poset $(X_{1},\leq), X_{1} = X - A_{1}$ 
...
*Remark*: This algorithm eventually stops since it's a **finite** poset.

We continue until the last $p$ such that $X_{p} = X_{p-1} - A_{p-1} \neq \emptyset, X_{p+1} = \emptyset$. Let $X_{p} = A_{p}$.
It remains to show $p = n$. It is known that $p \geq n$.

By the true of false question, $\exists x_{i} \in A_{i}$ such that $x_{1}\leq x_{2} \leq \dots \leq x_{p}$, implying $x_{1},\dots,x_{p}$ is a chain in $P$, implying $p \leq n$.
`\end{proof}`
**Homework problem:** proof of the true or false question -> could be on the test!!!

**Example:** Type of problem that could appear on the exam
$P = (\mathcal{P}([4]),\subseteq)$
1. Draw the Hassel diagram
2. Find all maximal chains and the largest chain
3. Partition $\mathcal{P}([4])$ into as few antichains as possible
4. Find all maximal antichains

Diagram:
![[Lecture 13 - Oct 12 2026-10-12 10.10.40.excalidraw]]
