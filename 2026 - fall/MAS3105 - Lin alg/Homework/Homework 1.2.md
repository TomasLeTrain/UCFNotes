
$$
\begin{align}
\begin{bmatrix}
1 & 2 & 4 & -7 \\
2 & 4 & 5 & -11 \\
4 & 5 & 4 & -10
\end{bmatrix} \\ \\

\begin{bmatrix}
1 & 2 & 4 & -7 \\
0 & 0 & -3 & 3 \\
0 & -3 & -12 & 18
\end{bmatrix} \\ \\
 \\
\text{echelon form:} \\
\begin{bmatrix}
1 & 2 & 4 & -7 \\
0 & 1 & 4 & -6 \\
0 & 0 & 1 & -1 \\
\end{bmatrix} \\ \\
 \\
\begin{bmatrix}
1 & 2 & 0 & -3 \\
0 & 1 & 0 & -2 \\
0 & 0 & 1 & -1 \\
\end{bmatrix} \\ \\
 \\
\begin{bmatrix}
1 & 0 & 0 & 1 \\
0 & 1 & 0 & -2 \\
0 & 0 & 1 & -1 \\
\end{bmatrix} \\ \\


 \\ \\

\end{align}
$$

# 2
$$
\begin{align}
\begin{bmatrix}
2 & -5 & 7 & 0 \\
-6 & 15 & -21 & 0 \\
-4 & 10 & -14 & 0
\end{bmatrix} \\
 \\ \\
 
\begin{bmatrix}
2 & -5 & 7 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0
\end{bmatrix} \\
 \\
 \\
2x_{1}-5x_{2}+7x_{3}=0
\boxed{ x_{1}=\frac{5}{2}x_{2}-\frac{7}{2}x_{3} }
\end{align}
$$
# 3
$$
\begin{align}
\begin{bmatrix}
1 & -3 & 0 & -1 & 0 & -9 \\
0 & 1 & 0 & 0 & -7 & 9 \\
0 & 0 & 0 & 1 & 7 & 3 \\
\end{bmatrix} \\
 \\
R_{1}+3R_{2}\to R_{1} \\
\begin{bmatrix}
1 & 0 & 0 & -1 & -21 & 18 \\
0 & 1 & 0 & 0 & -7 & 9 \\
0 & 0 & 0 & 1 & 7 & 3 \\
\end{bmatrix}
 \\
R_{1}+R_{3} \to R_{1} \\
\begin{bmatrix}
1 & 0 & 0 & 0 & -14 & 21 \\
0 & 1 & 0 & 0 & -7 & 9 \\
0 & 0 & 0 & 1 & 7 & 3 \\
\end{bmatrix} \\
x_{1}-14x_{5}=21 \\
x_{2}-7x_{5}=9 \\
x_{4}+7x_{5}=3 \\

x_{1}=21+14x_{5} \\
x_{2}=9+7x_{5} \\
x_{4}=3-7x_{5}
\end{align}
$$

# 5
$$
\begin{align}
\begin{bmatrix}
1 & 0 & -4 & 0 & -8 & 6 \\
0 & 1 & 7 & -1 & 0 & 3 \\
0 & 0 & 0 & 0 & 1 & 0 \\
\end{bmatrix} \\ \\
\begin{bmatrix}
1 & 0 & -4 & 0 & 0 & 6 \\
0 & 1 & 7 & -1 & 0 & 3 \\
0 & 0 & 0 & 0 & 1 & 0 \\
\end{bmatrix} \\
 \\
x_{1}-4x_{3}=6 \\
x_{2}+7x_{3}-1x_{4}=3 \\
x_{5}=0 \\
 \\
x_{1}=6+4x_{3} \\
x_{2}=3-7x_{3}+x_{4} \\
x_{5}=0
\end{align}
$$

# 6
$$
\begin{align}
\begin{bmatrix}
1 & h & 3 \\
-2 & 10 & -9
\end{bmatrix} \\
 \\
\begin{bmatrix}
1 & h & 3 \\
0 & 10+2h & -3
\end{bmatrix} \\
\boxed{ h\neq-5 } 
\end{align}
$$

# 7
$$
\begin{align}
\begin{bmatrix}
1 & h & 5 \\
4 & 8 & k
\end{bmatrix} \\ \\
 \\
\text{no solution:} \\
\begin{bmatrix}
1 & h & 5 \\
0 & 8-4h & k-20
\end{bmatrix} \\ \\
8-4h=0, k-20\neq 0 \\
h = 2, k \neq 20 \\
 \\
\text{unique solution:} \\
\begin{bmatrix}
1 & h & 5 \\
0 & 8-4h & k-20
\end{bmatrix} \\ \\ \\ \\

\begin{bmatrix}
1 & h - g(8-4h) & 5 - g(k-20) \\
0 & 8-4h & k-20
\end{bmatrix} \\ \\ \\ \\
\end{align}
$$