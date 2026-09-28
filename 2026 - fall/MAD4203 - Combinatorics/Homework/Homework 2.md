# Note
I misread and ended up doing some do it for understanding problems instead of the turn in ones, I figured I could include them here since it took me a long time to do them :)

# 12
*Show by example that the conclusion of the Chinese remainder theorem (Application 6) need not hold when $m$ and $n$ are not relatively prime.*

Consider $m = 2, n = 6$
$$
\begin{align}
x = mp + a \\
x = nq + b
\end{align}
$$
consider the sequence:
$$
\begin{align}
a = 1 \to \\
1, 1 + 2, 1 + 4,\dots \\
\{ 1, 3, 5, 7, 9\} \mod 6 = \boxed{ 1, 3, 5 }, \boxed{ 1, 3, 5 } \dots
\end{align}
$$
*Prove that, for any $n + 1$ integers $a_{1},a_{2},a_{n+1}$, there exist two of the integers $a_{i}$ and $a_{j}$ with $i \neq j$ such that $a_{i} - a_{j}$ is divisible by $n$.*

Consider rewriting each $a_{i}$ in the following form:
$$
\begin{align}
a_{i} = n p_{i} + r_{i} \to 0 \leq r_{i} \leq n-1
\end{align}
$$

There are at most $n$ distinct possible values for $r_{i}$, but $n+1$ elements, therefore by the PP, at least two numbers must share the same $r_{i}$:

$$
\begin{align}
r_{i} = r_{j}, i \neq j \\
a_{i}=  n p_{i} + r_{i}, a_{j} = n p_{j} + r_{j} \\
a_{i} - a_{j} = (n p_{i} + r_{i}) - (n p_{j} + r_{j}) \\
= (p_{i} - p_{j})n + (r_{i} + r_{j}) \\
= (p_{i} - p_{j})n \\
\square
\end{align}
$$

# 16
*Prove that in a group of $n > 1$ people there are two who have the same number of acquaintances in the group. (It is assumed that no one is acquainted with oneself).*

Let $x_{i}$ be the number of acquaintances the $i$'th person has.

The most $x_{i}$ can be is $x_{i} \leq n-1$, in the case that one person knows everyone. Similarly, the smallest $x_{i}$ can be is $0 \leq x_{i}$, in the case that one person doesn't know anyone.

However, if any $x_{i} = n-1$, it implies that person know everything, in which case $x_{j} = 0$ can never occur since everyone must know $i$. Conversely, if any $x_{i} = 0$, then no $x_{j} = n-1$ since one person cannot know anyone. Therefore, the \# of distinct $x_{i}$ is at most $n-1$.

Thus, there are $n-1$ possible distinct $x_{i}$, but $n$ people that each have an $x_{i}$ associated with them. Therefore by the PP, $x_{i} = x_{j}, i \neq j$. $\square$

# 20
*Prove that $R(3,3,3) \leq 17.$*
Consider a graph made up of 17 people, where all the connections between people are colored either red, green, or blue. Assume this graph has a coloring such that there exists no group of 3 people who all share the same connection color with each other (so no group of 3 people who all have red/blue/green connections with each other).

First, fix a person $A$. They have 16 connections to everyone else. Each connection must be of a color red, green, or blue.

Consider grouping $A$'s connections based on their assigned color (people whose connection to $A$ is red, people whose connection with $A$ is green, etc.). By symmetry, the argument presented below works for any combination of colors and chosen people.

Let the \# of people whose connection with $A$ is red be denoted by $r$. Similarly, let the \# of people whose connection with $A$ is green be denoted by $g$, and finally the same with the blue group being denoted with $b$. It can be seen that for the graph to have the assumed coloring, $r + g + b = 16$.

IIf any two people $B$ and $C$ in this group have a red connection then a triangle is completed with $A$ ($A$,$B$,$C$ would all form a red triangle). Therefore, all connections in this group must either be green or blue. Since $R(3,3) = 6$, the smallest number of people in the red group, such that no red, blue, or green triangles forms, has to be 5. In other words, $r \leq 5$.

Now consider the green group. Using the same argument used for the red group, no people in this group can be colored green, so the smallest number of people that can be in this group such that no triangles are made is 5, so $g \leq 5$.

Now consider the blue group. Exactly as before, the same argument means that there must be at most 5 people whose connection with $A$ is blue, so $b \leq 5$.

Thus, we can see that $r \leq 5, g \leq 5, b \leq 5$, so $r + b + g \leq 15$ follows. However, for the coloring to be valid $r + g + b = 16$, which as shown is impossible. Therefore by contradiction, $K_{17} \to K_{3},K_{3},K_{3}$, implying $R(3,3,3) \geq 17$. $\square$

# 22
*Prove that*
$$
\begin{align}
R(\underbrace{ 3,3,\dots,3 }_{ k+1 }) \leq (k+1)(R(\underbrace{ 3,3,\dots,3 }_{ k })-1) + 2
\end{align}
$$
*Use this result to obtain an upper bound for*
$$
\begin{align}
R(\underbrace{ 3,3,\dots,3 }_{ n })
\end{align}
$$
Define
$$
\begin{align}
f(k) = R(\underbrace{ 3,3,3\dots,3 }_{ k })
\end{align}
$$
Then we must prove $f(k+1) \leq (k+1)(f(k)-1) + 2$.

$f(k)$ is defined as the smallest number of elements such that a group size $3$ all with equal coloring is guaranteed to exist. Therefore, a graph with $f(k)-1$ elements does not guarantee all colorings satisfy the group size $3$ existing.

Let's now construct a new graph with $k+1$ colors $c_{1},c_{2},\dots,c_{k+1}$.

Consider creating a graph $S$ of size $|S| = (k+1)(f(k)-1)$. We can divide this graph into $k+1$ subgraphs $s_{1},s_{2},\dots,s_{k+1}$, all size $f(k)-1$. For any subgraph $s_{i}$, color all its connections all colors except the color $c_{i}$. This means each subgraph is colored with $k$ colors total. Therefore, each subgraph will not be guaranteed to create a group size $3$ for which all connections are of the same color. 

We now demonstrate that adding 2 elements to this graph guarantees at least one group of size $3$ becomes guaranteed.

Consider first placing an additional element $e_1$ to graph $S$. To avoid creating a $3$ group, we color all its connections to elements from subgraph $s_{i}$ with color $c_{i}$. Since none of the connections inside subgraph $s_{i}$ are colored $c_{i}$, we are guaranteed to not create any $3$ groups.

Now consider placing another element $e_{2}$ to the graph $S + e_{1}$. To avoid creating a $3$ group with any of the $s_{i}$, subgraphs, all connections from $e_{2}$ to the subgraph $s_{i}$ are colored with $c_{i}$. After all such colorings there is one connection left, the one from $e_{1}$ to $e_{2}$. If we color this connection with some color $c_{i}$, we create a $3$ group with any 2 nodes belonging to the $s_{i}$ subgraph:
$$
\begin{align}
A \in s_{i} : e_{1} \underbrace{ \to }_{ c_{i} } A, e_{2} \underbrace{ \to }_{ c_{i} } A, e_{1} \underbrace{ \to }_{ c_{i} } e_{2}
\end{align}
$$
Thus, no matter how the graph of size $(k+1)(f(k)-1) + 2$ gets colored, there is always a group of $3$ whose connections are all the same color. $\square$

Now to obtain the upper bound for $R(\underbrace{ 3,3,\dots,3 }_{ n }) = f(k)$, the recursive formula gets expanded:
$$
\begin{align} \\
f(1) = 3 \\
f(k) \leq k(f(k-1) - 1) + 2 \\
f(k) \leq k((k-1)(f(k-2) - 1) + 2) + 2 \\
f(k) \leq k((k-1)((k-2)(f(k-3) - 1) + 2) + 2) + 2 \\
\to \\
f(k) \leq \dots(\dots((k-(k-2))(f(k-(k-1)) - 1) + 2)\dots)\dots \\
f(k) \leq \dots(\dots((2)(f(1) - 1) + 2)\dots)\dots \\ \\
\to \\
f(k) \leq k((k-1)((k-2)((\dots ((2)(f(1) - 1) + 2) \dots) +2)+2)+2)+2 \\ 
f(k) \leq k((k-1)((k-2)((\dots ((2)(2) + 2) \dots) +2)+2)+2)+2 \\ \\
\to \\

f(k) \leq 2 * k(k-1)(k-2)(k-3)\dots(2) + \\
2 * k(k-1)(k-2)(k-3)\dots(3) + \\
2 * k(k-1)(k-2)(k-3)\dots(4) + \\
\dots + 2k + 2 \\ \\
\to \\
f(k) \leq 2 \left( k! + \frac{k!}{2!} + \frac{k!}{3!} + \dots + \frac{k!}{(k-1)!} + 1 \right) \\ \\
\boxed{ f(k) \leq 2 \sum_{n=1}^{k} \frac{k!}{n!} \\ \\ }
\end{align}
$$

# 23
*The line segments joining $10$ points are arbitrarily colored red or blue. Prove that there must exist three points such that the three line segments joining them are all red, or four points such that the six line segments joining them are all blue (that is, $R(3,4) \leq 10$).*

Consider some element $A$. It has 9 connections to all other elements, and all connections are either red or blue. We can consider the group of all elements with blue connections to $A$ and the group of all elements with red connections to $A$. 

Let $n$ denote the number of elements that have red connections with $A$. All connections inside this group must be blue, since any red connection would complete a triangle with $A$. Therefore, $n \leq 3$, since any larger $n$ will create a group of 4 with all blue connections.

Since $n \leq 3$, at least 6 elements must be connected to $A$ as blue. Now the 6 remaining elements must be connected to avoid creating any red or blue triangles, since a red triangle satisfies the condition, and any blue triangle also creates a 4 group sincec all connections to $A$ are blue. Since $R(6,6) = 3$, any group of 3 people is guaranteed to make either a red or blue triangle, meaning in all graphs size 10 the ramsey condition is satisfied. $\square$

# 24
*Let $q_{3}$ and $t$ be positive integers with $q_{3} \geq t$. Determine the Ramsey number $r_{t}(t,t,q_{3})$.*

Consider a graph of size $n \geq q_{3}$. We must color all $t$-subsets of the graph with colors $c_{1},c_{2},c_{3}$, such that no group of $t$-vertices all colored $c_{1}$ or $c_{2}$ exist, and no group of $q_{3}$-vertices all colored $c_{3}$ exist.

Coloring any $t$-subset with color $c_{1}$ immediately creates a group of $t$ elements, all with color $c_{1}$. In the case that any $t$-subset is colored $c_{2}$, a group of $t$ elements all colored $c_{2}$ is created as well. Therefore, no $t$-subset can be colored either $c_{1}$ or $c_{2}$. However, this implies that every $t$-subset is colored $c_{3}$, meaning all $n$ elements all have their $t$-subsets colored $c_{3}$. Since $n \geq q_{3}$, the condition is still satisfied. Thereore, $r_{t}(t,t,q_{3}) \geq q_{3}$.

In the case that $n < q_{3}$, the group created by coloring all $t$-subsets $q_{3}$ is still $n$ elements in size. However, this size is smaller than $q_{3}$, so the ramsey condition is not satisfied. Therfeore, $r_{t}(t,t,q_{3}) \geq q_{3}$. 

Thus, $r_{t}(t,t,q_{3}) = q_{3}$. $\square$

# 25
*Let $q_{1},q_{2},\dots ,q_{k},t$ be positive integers, where $q_{1} \geq t, q_{2} \geq t, \dots , q_{k} \geq t$. Let $m$ be the largest of $q_{1},q_{2},\dots,q_{k}$. Show that*
$$r
\begin{align}
r_{t}(m,m, \dots, m) \geq r_{t}(q_{1},q_{2},\dots,q_{k})
\end{align}
$$
*Conclude that, to prove Ramsey's theorem, it is enough to prove it in the case that $q_{1}=q_{2}=\dots=q_{k}$.*


Let $M = r_{t}(m,m, \dots, m)$. By definition, all graphs of size $M$ that get colored with $k$ colors become will have a group of at least $m$ elements, whose $t$-subsets are all colored the same. Now instead consider $r_{t}(q_{1},q_{2},\dots,q_{k})$, where $q_{i} \leq m$. Any graph of size $M$ is guaranteed to satisfy the ramsey condition for a group of $m$ size, however any group of $m$ size also satisfies a group of smaller size, say for some $q_{i} \leq m$. Therefore, all graphs that satisfy $r_{t}(m,m, \dots, m)$ also satisfy $r_{t}(q_{1},q_{2}, \dots, q_{k})$. Since $r_{t}$ is minimizing the largest it can equal is $r_{t}(m,m, \dots,m)$:
$$
\begin{align}
r_{t}(m,m, \dots, m) \geq r_{t}(q_{1},q_{2},\dots,q_{k})
\end{align}
$$

Ramsey's theorem states that some $p$ exists such that
$$
\begin{align}
K^{t}_{p} \to K^{t}_{q_{1}},K^{t}_{q_{2}},\dots,K^{t}_{q_{k}}
\end{align}
$$
Consider the case $q_{1} = q_{2} = \dots = q_{k} = m$. In this case, any valid $p$ is also valid for the cases where $m \geq q_{i}$ for any $i$, since a valid group of $m$ also satisfies a group of size smaller than $m$. Therefore, it suffices to prove the case $q_{1} = q_{2} = \dots = q_{k} = m$ to prove for any $q_{i}$. 

# Chapter 11 problems
## A
*Prove that there is no graph with an odd number of vertices of odd degree.*

Each vertex must have at least 1 edge, since having 0 edges would make it of even degree. We can achieve this for any graph of size $k$ by making $\frac{k}{2}$ pairs of connected vertices. This makes the degree of all vertices 1. This only works when $k$ is even.

Consider the case when $k$ is odd. $\left\lfloor  \frac{k}{2}  \right\rfloor$ pairs of vertices are made, and one vertex $a$ is left with no connections. To make it degree 1 it gets connected to some vertex $b$. However, this makes $b$ of degree 2, so to make it odd again $b$ gets connected to another vertex. This process repeats until one node has degree 2 and every other one has degree 3, which is equivalent to the case of $a$ with no connections and every other with 1. Continuing this pattern the graph ends up having every vertex connected to every other. In this case, each vertex has a degree of $k-1$, still resulting in an even degree. $\square$

## B
*Let  $P = (v_{1},v_{2},\dots,v_{k})$ be a path with $k \geq 2$.  Let $\tau : \{ v_{1},v_{2},\dots,v_{k} \} \to \{1,2\}$ be a mapping such that  $t(v_{1}) = 1$ and $\tau(v_{k}) = 2$. Prove that P has an odd number of rainbow edges under $\tau$, where an edge $\{ u,v \}$ of P is rainbow under $\tau$ if $\tau(u)\neq \tau(v)$.* 

Consider $\tau(v_{i}) = 1, i < k$. In this case there is only 1 rainbow edge: the edge $\{v_{k-1},v_{k}\}$. Now consider the case where $\tau(v_{j}) = 2, j < k-1$ and $\tau (v_{i}) = 1, i < k, i \neq j$. In this case there are 3 rainbow edges: $\{ v_{j-1},v_{j} \}, \{ v_{j},v_{j+1} \}, \{ v_{k-1},v_{k} \}$.

In general, coloring some $v_{i}$ either doesn't increase the number of rainbow edges, or it increases the rainbow edges by two.

Consider the case where a rainbow edge is $\{ v_{i},v_{i+1} \}$, and $\tau(v_{i-1}) = \tau(v_{i})$. Let's say $\tau(v_{i}) = 1$ and $\tau(v_{i+1}) = 2$. Now if $v_{i}$ gets changed to now be $\tau(v_{i}) = 2$, the \# of rainbow edges doesn't change, only the edge itself does (changes from  $\{ v_{i}, v_{i+1} \}$ to $\{ v_{i-1}, v_{i} \}$).

Now consider the opposite case where $\tau(i-1) = \tau(i) = \tau(i+1)$.  Changing $\tau(v_{i})$ intiroduces two new rainbow edges: $\{ v_{i-1}, v_{i} \}$ and $\{ v_{i},v_{i+1} \}$.

In other words, changing the color of any $v_{i}$ either doesn't change the \# of rainbow edges, or it increase it by 2. $\tau(v_{1}) \neq \tau(v_{k})$ implies there must be at least 1 rainbow edge. Thus, the \# of rainbow edges is always odd. $\square$

