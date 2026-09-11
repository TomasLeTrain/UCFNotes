# 1.7 Linear independence
Any non-trivial solution to a homogenious equation gives all solutions to that system:
$$
\begin{align}
A \vec{x} = \vec{0} \\
A (\vec{x} * \alpha) = ? \\
(A \vec{x}) * \alpha = ? \\
(\vec{0}) * \alpha = \boxed{ \vec{0} } \\
\end{align}
$$
So all $\vec{x} * \alpha, \alpha \in \mathbb{R}$ are solutions to the system, given that $\vec{x}$ solves the homogenous.

This also means that if there exist multiple solutions $\vec{x_{1}},\vec{x_{2}},\dots$, then all the following are also solutions:
$$
\begin{align}
A \vec{x_{1}} = \vec{0}, A \vec{x_{2}} = \vec{0}, \dots \\
\to
\boxed{ A(\alpha_{1}* \vec{x_{1}},\alpha_{2} * \vec{x_{1}},\dots) = \vec{0} }
\end{align}
$$



If given relationships such as (arbitrary here, just have to be linear combinations of others):
$$
\begin{align}
\vec{A_{2}} = \alpha_{1} * \vec{A_{1}} + \beta_{1} \vec{A_{3}} \\
\vec{A_{5}} = \alpha_{2} * \vec{A_{1}} + \beta_{2} \vec{A_{4}} \\
\end{align}
$$
Then the following is true:
$$
\begin{align}
\text{Span} \{ \vec{A_{1}}, \underbrace{ \vec{A_{2}} }_{ \text{not neccesary} }, \vec{A_{3}},\vec{A_{4}},\underbrace{ \vec{A_{5}} }_{ \text{not neccesary} } \} = \text{Span} \{ \vec{A_{1}}, \vec{A_{3}},\vec{A_{4}} \}
\end{align}
$$

In other words, $\vec{A_{2}}$ and $\vec{A_{5}}$ are in the span of the others, therefore the span can be reduced to not include them.

## Example
Suppose vectors $\{ \vec{v_{1}}, \vec{v_{2}},\vec{v_{3}},\vec{v_{4}} \}$ satisfy
$$
\begin{align}
\vec{v_{5}} = -2 \vec{v_{2}} \\
\vec{v_{4}} = 5 \vec{v_{1}} - 12 \vec{v_{2}}
\end{align}
$$
1. Find 2 solutions to $A \vec{x} = \vec{0}$ where $A = \left[ \vec{v_{1}},\vec{v_{2}},\vec{v_{3}},\vec{v_{4}} \right]$
2. Find 1000 solutions to $A \vec{x} = \vec{0}$ where $A = \left[ \vec{v_{1}},\vec{v_{2}},\vec{v_{3}},\vec{v_{4}} \right]$


## Linear Independence
**Definion** A set of vectors $\vec{v_{1}}, \vec{v_{2}},\dots,\vec{v_{p}}$ in $\mathbb{R}^{n}$ is said to be *linearly independent* if $c_{1} \vec{v_{1}} + c_{2} \vec{v_{2}} + \dots + c_{p} \vec{v_{p}} = \vec{0}$ implies that $c_{1} = 0, c_{2}= 0 ,.. , c_{p} = 0$, that is, all the $c_{i}$ have to be 0 if a set of vectors is *not linearly independent, it is linearly dependent*. A set of vectors is linearly dependent IFF a non-trivial linear combination of the vectors gives the 0 vector

If not linearly independent, can write some variables as linear combinations of others.