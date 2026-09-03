1.3 vectors
- multiplying matrices
- - 1.4 matrix equation (?)

identity matrix - square + diagonal full of 1's -> unique solution

# 1.3 Vector

*Definition*: A vector in $\mathbb{R}^{n}$ is an $n\times 1$ matrix.
notation:
$$
\begin{align} \\
\vec{0_{n}}=\text{0 vec on $\mathbb{R}^{n}$}.
\end{align}
$$

Scalar multiplication:
$$
\begin{align}
n * \vec{a} = \begin{bmatrix} a_{1} * n, a_{2} * n, \dots \end{bmatrix}
\end{align}
$$

algebreic properrties:
$$
\begin{align}
\vec{u}+ \vec{v} = \vec{v} + \vec{u} \\
(\vec{u} + \vec{v} ) + \vec{w} = \vec{u} + (\vec{v} + \vec{w}) \\
\vec{u} + \vec{0} = \vec{0} + \vec{u} = \vec{u} \\
\vec{u} + (-\vec{u}) = -\vec{u} + \vec{u} = \vec{0} \\
c(\vec{u} + \vec{v} ) = c \vec{u} + c \vec{v} \\
(c + d) \vec{u} = c \vec{u} + d \vec{v} \\
c(d \vec{u}) = (cd) \vec{u} \\
1 \vec{u} = \vec{u}
\end{align}
$$

## Linear Combinations
Given vectors $\vec{v_{1}},\vec{v_{2}},\dots ,\vec{v_{p}} \in \mathbb{R}^{n}$
Given scalars $c_{1},c_{2},\dots,c_{p} \in \mathbb{R}$  the vector 
$$
\begin{align}
\vec{y}=c_{1} \vec{v_{1}} + c_{2} \vec{v_{2}} + \dots + c_{p} \vec{v_{p}}
\end{align}
$$
Is called a **linear combination** of vectors $\vec{v_{1}},\vec{v_{2}},\dots ,\vec{v_{p}}$ with weights $c_{1},c_{2},\dots,c_{p}$ respectively.

*Remark*: scalars can also be zero

### Span
The set of all linear combinations of $\vec{v_{1}},\vec{v_{2}},\dots ,\vec{v_{p}}$ is called the **span** of that set of vectors.

$$
\begin{align}
\text{Span}\{ \vec{v_{1}},\vec{v_{2}},\dots ,\vec{v_{p}} \} =  \\
\{ c_{1} \vec{v_{1}} + c_{2} \vec{v_{2}} + \dots + c_{p} \vec{v_{p}} \mid  \forall c_{p} \in \mathbb{R} \}
\end{align}
$$

The span is a set of all the vectors that can be made from linear combinations.

with two vectors can reach anywhere so long as they aren't all zero and they aren't all parallel

checking if a vec is in a spsan is the same as seeing if there is a soluton to a system of linear equations problem

# 1.4 Matrix Multiplication
$$
\begin{align}
A_{2 \times 3 } * B_{3 \times 4} = C_{2 \times 4}
\end{align}
$$
Where $M_{n \times m}$ defines a matrix $M$ with \# rows $n$ and \# columns $m$.

Number of columns of $A$ must equal number of rows of $B$.