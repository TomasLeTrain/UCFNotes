# 5.6 Partially Ordered Sets (Poset)
Recall a **binary relation** from [[Lecture 11 - Oct 5#^a39303]]


The set $X$ is such a binary relation refered as the **ground set** (the "universe")

> [!definition] Partial Order
> A binary relation $R$ on a set $X$ is a **partial order** if it is relfexive, antisymmetric, and transitive.

> [!definition] Linear/Total Order
> A binary relation $R$ on a set $X$ is a **linear order/total order** on $X$ if $R$ is reflexive, symmetric, and transitive.

$X = \mathbb{R}, R = \leq$, or the more than or equal to binary relation, is linear order since any numbers are **comparable**.

If $R$ is a partial order on a set $X$, we use $\preceq$ to denote $R$.

> [!theorem] 
> If $\preceq$ is a partial order on a *finite* set $X$, then $X$ has a minimal element and a maximal element.

`\begin{proof}`
Pick an element $a \in X$. If no $b \in X \to b \leq a$, then we are done ($a$ is a minimal element). Otherwise, continue with $b$. Since $X$ is finite, eventually we stop at the last elemetn of the set, at which point we located the minimum element. Similarly, we find a maximal element.
`\end{proof}`

**Question:** How many minimal and maximal elements does $X$ have if $\preceq$ is a linear order and $X$ is finite?
**Ans:** unique maximal and minimal element
`\begin{proof}`
Proof by contradiction.
Consider two minimal elements $a,b \in X$, then $a \leq b$ or $b \leq a$ must hold for both to be minimal. However, this implies $a = b$, meaning only one unique minimal element exists.
`\end{proof}`


> [!definition] Elements Covering in Binary Relation
> Let $R$ be a binary relation on a set $X$. For $a,b \in X$, we say *a is covered by b* or *b covers a* if $\nexists c \in X \text{ s.t. } a \leq c \leq b$.

For a positive integer $k$, we use $[k] = \{ 1,2,\dots,k \}$.

## Example
Suppose $X = [6]$, and $\preceq = |$ (divisibility)

The following is a **Hasse Diagram**, graphically showing the coverings of a relation

![[Lecture 12 - Oct 7 2026-10-07 09.33.56.excalidraw|50%]]

Consider another example
$X = \mathcal{P}([3]), \preceq = \subseteq$ (subsets relation)
![[Lecture 12 - Oct 7 2026-10-07 09.31.38.excalidraw|50%]]


> [!definition] Partially Ordered Set - Poset
> $P$ is a pair $(X,\preceq)$, where $X$ is a *finite* set and $\preceq$ is a partial order on $X$.
> A poset can be visualized geometrically using a **Hasse Diagram** via cover relations.

> [!definition] Hasse Diagram
> The **Hasse Diagram** for a finite poset $P = (X, \preceq)$ is obtained by taking a piont in the plane for each element in $X$, being careful to put the point for $x \in X$ below $y \in X$ if *$y$ covers $x$* , and connecting $x$ and $y$ by a line segment if and only if $x$ is covered by $y$.

> [!definition] Chain of a Poset
> Let $P = (X, \preceq)$ be a poset.
> A **chain** in the poset $P$ is a set $C \subseteq X$, such that every pair of elements in $C$ are comparable.
> An **antichain** is a set $A \subseteq X$ such that each pair of elements in $A$ are *incomparable*.

> [!question] if $C$ is a chain, what can we say about the new coset $(C, \preceq)$?
> It now forms a linear order!

> [!question] if $P = (X, \preceq)$ is a poset and $\preceq$ is a linear order of $X$, what can we say about its Hasse diagram?
> It forms a straight line since they are all comparable

> [!question] If $C$ is a chain and $A$ is an antichain in a poset $P$, what can we know about $|C \cap A|$?
> $|C \cap A| \leq 1$, since the most they can share is one element

**Observations:** for some poset $P = (X, \preceq)$:
$\{ a \}$ is a chain $\forall a \in X$, since it holds the reflexive property
$\{ a \}$ is an antichain $\forall a \in X$, since there are no two elements to compare
The set of all minimal elements of $X$ form an *antichain*
The set of all maximal elements of $X$ form an *antichain*


> [!definition] Maximal Antichain
> Given a poset $P = (X, \preceq)$, a set $A \subseteq X$ is a **maximal antichain**  if $A$ is an antichain and $\nexists$ an antichain $A^{*}$ such that $A \subseteq A^{*}$.

> [!definition] Maximal Chain
> A set is a maximal chain if $c$ is a chiain in $P$ and $\nexists$ a chain $C^{*}$ such that $C \subseteq C^{*}$

## Example
Consider the poset $(X, \preceq)$, where $X = [8], \preceq = |$ (divisibility)

Find the maximal chains and maximal antichains.
![[Lecture 12 - Oct 7 2026-10-07 10.01.00.excalidraw|50%]]
This forms 6 maximal chains in total:
$\{ 1,7 \},  \{ 1,5 \}, \{ 1,3,6 \}, \{ 1,2,6 \}, \{  1,2,4,8 \}$

Maximal antichains:
$$
\begin{align}
\{ 5,6,7,8 \}, \{ 4,5,6,7 \}, \{ 3,4,5,7 \}, \{ 2,3,5,7 \}, \{ 1 \}, \{ 3,5,7,8 \}
\end{align}
$$


**Questions** can we partition $X$ into chains or antichains?
**Answer:**
Yes, every set $\{ a \}, a \in X$ forms a chain and antichain, therefore forming a partition