# # Multiset
**multiset:** set that can include multiple instances of an element (each instance of the element is not distinguished)

**Repetition numbers** can be used to compactly represent a multiset:
$$
\begin{align}
\left\{  n * a, m * b, \dots \right\}, \text{where $n$ can be } \infty
\end{align}
$$

### Symmetric difference
$$
\begin{align}
A \Delta B  & := \left\{ x | x \in A \cap x \not\in B \right\} \\
 & := (A - B) \cup (B - A) \\
 & := (A \cup B) - (A \cap B) \\
\end{align}
$$

## Disjoint

Sets $A$ and $B$ are **disjoint** if $$ A \cap B = \emptyset $$
Meaning they have no elements in common.

## Disjoint Union
The **disjoint union** of A and $B$ is a set that contains all products of both $A$ and $B$, with the elements distinguished by index
$$
\begin{align}
A \ \dot{\cup} \ B = (A \times \{ 0 \}) \cup (B \times \{ 1 \}) \equiv \dot{A} \cup \dot{B}
\end{align}
$$

Cartesian product (pairwise combination of $(a,b)$)
$$
\begin{align}
A \times B := \left\{ \left(a, b\right)\ |\ a \in A \cap b \in B \right\} \\
\text{order matters} \to (n,m) \neq (m,n)\ |\ m \in A, n \in B \\
|A \times B| = |A| * |B|
\end{align}
$$



## Partition
breaks all elements into pairwise disjoint subsets $S_{1},\dots,S_{m}$ of $S$, such that $\cup$-ing all sets together gives the final set. All sets must be disjoint from each other.

General rules for partitions:
1. $S_{i} \in S$ for any $i$
2. $\bigcup {S_{i} = S}$ 
3. any $S_{i} \cap S_{j} = \emptyset$ for any $i \neq j$. Also means all parts are pairwise disjoint.
4. $S_{i}$ may be empty (at least for the purposes of this course)

**parity** $\to$ integer is even or odd

$$
\begin{align}
2 \mid k \implies \text{even}, 2 \nmid k \implies \text{odd}
\end{align}
$$


The set of even and odd integers therefore form a partition of all integers $\mathbb{Z}$:
$$
\begin{align}
\mathbb{Z} = \{ 2 \mid k  \in \mathbb{Z} \} \cup \{ 2k+1 \mid k \in \mathbb{Z} \}
\end{align}
$$
### basic counting rules
#### 1. Rule of Sum / Addition Principle
Suppose that a set $S$ is partition into $S_{1},\dots,S_{m}$.
Then $|S| = |S_{1}| + |S_{2}| + \dots |S_{m}|$
Rule of Sum used for counting subsets of multiset
*Remark:* make sure sets are a partition!
2. partition $S$ into "manageable" parts and know how to count each $S_{i}$.
3. Don't partition $S$ into too many parts.