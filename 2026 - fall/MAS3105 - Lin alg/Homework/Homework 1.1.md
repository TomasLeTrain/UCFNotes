# 1
$$
\begin{align}
6x_{1}+12x_{2}=18 \\
4x_{1}x+7x_{2}=14 \\
 \\
\left[\begin{array}{cc|c}
6 & 12 & 18 \\
4 & 7 & 14
\end{array}\right] \\
\frac{R_{1}}{6}\to R_{1} \\
\left[\begin{array}{cc|c}
1 & 2 & 3 \\
4 & 7 & 14
\end{array}\right] \\
R_{2} - 4 * R_{1}\to R_{2} \\
\left[\begin{array}{cc|c}
1 & 2 & 3 \\
0 & -1 & 2
\end{array}\right] \\
R_{1} + 2 * R_{2}\to R_{1} \\
\left[\begin{array}{cc|c}
1 & 0 & 7 \\
0 & -1 & 2
\end{array}\right] \\ \\
\boxed{ x_{1}=7,  x_{2}=-2 }
\end{align}
$$


# 2.

$$
\begin{align}
x_{1} + 3x_{2}=9 \\
x_{1}-x_{2}=1 \\
 \\
\left[\begin{array}{cc|c}
1 & 3 & 9 \\
1 & -1 & 1
\end{array}\right] \\
R_{1} - R_{2} \to R_{1} \\
\left[\begin{array}{cc|c}
0 & 4 & 8 \\
1 & -1 & 1
\end{array}\right] \\
R_{1} * \frac{1}{4} \to R_{1} \\
\left[\begin{array}{cc|c}
0 & 1 & 2 \\
1 & -1 & 1
\end{array}\right] \\
R_{2} + R_{1} \to R_{2} \\
\left[\begin{array}{cc|c}
0 & 1 & 2 \\
1 & 0 & 3
\end{array}\right] \\
\boxed{x_{1}=3,x_{2}=2}
\end{align}
$$

# 3
$$
\begin{align}
\left[\begin{array}{ccc|c}
1 & 5 & 2 & -4 \\
0 & 1 & -1 & 3 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 2
\end{array}\right] \\
\end{align}
$$
No solution
# 4 
$$
\begin{align}
\left[\begin{array}{cccc|c}
1 & -3 & 0 & 0 & -4 \\
0 & 1 & -2 & 0 & -5 \\
0 & 0 & 1 & -1 & 4 \\
0  & 0 & 0 & 1 & 2
\end{array}\right] \\
R_{3}+R_{4}\to R_{3} \\
\left[\begin{array}{cccc|c}
1 & -3 & 0 & 0 & -4 \\
0 & 1 & -2 & 0 & -5 \\
0 & 0 & 1 & 0 & 6 \\
0  & 0 & 0 & 1 & 2
\end{array}\right] \\
R_{3}+2R_{2}\to R_{2} \\
\left[\begin{array}{cccc|c}
1 & -3 & 0 & 0 & -4 \\
0 & 1 & 0 & 0 & 7 \\
0 & 0 & 1 & 0 & 6 \\
0  & 0 & 0 & 1 & 2
\end{array}\right] \\
R_{1}+3R_{2}\to R_{1} \\
\left[\begin{array}{cccc|c}
1 & 0 & 0 & 0 & 17 \\
0 & 1 & 0 & 0 & 7 \\
0 & 0 & 1 & 0 & 6 \\
0  & 0 & 0 & 1 & 2
\end{array}\right] \\
\boxed{(17,7,6,2)}
\end{align}
$$

# 5
$$
\begin{align}
\left[\begin{array}{ccc|c}
1 & 0 & -6 & 10 \\
2 & 4 & 3 & 25 \\
0 & 2 & 5 & 5
\end{array}\right] \\
R_{2} - 2R_{3} \to R_{2} \\
\left[\begin{array}{ccc|c}
1 & 0 & -6 & 10 \\
2 & 0 & -7 & 15 \\
0 & 2 & 5 & 5
\end{array}\right] \\
R_{2} - 2R_{1} \to R_{2} \\
\left[\begin{array}{ccc|c}
1 & 0 & -6 & 10 \\
0 & 0 & 5 & -5 \\
0 & 2 & 5 & 5
\end{array}\right] \\ \\
R_{3}-R_{2} \to R_{3}
\left[\begin{array}{ccc|c}
1 & 0 & -6 & 10 \\
0 & 0 & 5 & -5 \\
0 & 2 & 0 & 10 
\end{array}\right] \\
\frac{R_{2}}{5} \to R_{2},
\frac{R_{3}}{2} \to R_{3}
\left[\begin{array}{ccc|c}
1 & 0 & -6 & 10 \\
0 & 0 & 1 & -1 \\
0 & 1 & 0 & 5 
\end{array}\right] \\
R_{1}+6R_{2} \to R_{1} \\

\left[\begin{array}{ccc|c}
1 & 0 & 0 & 4 \\
0 & 0 & 1 & -1 \\
0 & 1 & 0 & 5 
\end{array}\right] \\ \\

\left[\begin{array}{ccc|c}
1 & 0 & 0 & 4 \\
0 & 1 & 0 & 5 \\
0 & 0 & 1 & -1
\end{array}\right] \\

\end{align}
$$

# 6
$$
\begin{align}
\left[\begin{array}{cccc|c}
2 & 0 & 0 & -8 & -14 \\
0 & 5 & 5 & 0 & 0 \\
0 & 0 & 1 & 8 & 2  \\
-5 & 3 & 5 & 1 & 4
\end{array}\right] \\
\frac{R_{1}}{2} \to R_{1} \\

\left[\begin{array}{cccc|c}
1 & 0 & 0 & -4 & -7 \\
0 & 5 & 5 & 0 & 0 \\
0 & 0 & 1 & 8 & 2  \\
-5 & 3 & 5 & 1 & 4
\end{array}\right] \\ \\
R_{4}+5R_{1}\to R_{4} \\
\left[\begin{array}{cccc|c}
1 & 0 & 0 & -4 & -7 \\
0 & 5 & 5 & 0 & 0 \\
0 & 0 & 1 & 8 & 2  \\
0 & 3 & 5 & -19 & -31 
\end{array}\right] \\ \\ \\
\frac{R_{2}}{5}\to R_{2} \\
\left[\begin{array}{cccc|c}
1 & 0 & 0 & -4 & -7 \\
0 & 1 & 1 & 0 & 0 \\
0 & 0 & 1 & 8 & 2  \\
0 & 3 & 5 & -19 & -31 
\end{array}\right] \\ \\ 

R_{4}-3R_{2} \to R_{4} \\
\left[\begin{array}{cccc|c}
1 & 0 & 0 & -4 & -7 \\
0 & 1 & 1 & 0 & 0 \\
0 & 0 & 1 & 8 & 2  \\
0 & 0 & 2 & -19 & -31 
\end{array}\right] \\ \\ \\

R_{4}-2R_{3} \to R_{4} \\
\left[\begin{array}{cccc|c}
1 & 0 & 0 & -4 & -7 \\
0 & 1 & 1 & 0 & 0 \\
0 & 0 & 1 & 8 & 2  \\
0 & 0 & 0 & -35 & -35 
\end{array}\right] \\ \\ \\ \\

\frac{R_{4}}{-35} \to R_{4} \\
\left[\begin{array}{cccc|c}
1 & 0 & 0 & -4 & -7 \\
0 & 1 & 1 & 0 & 0 \\
0 & 0 & 1 & 8 & 2  \\
0 & 0 & 0 & 1 & 1
\end{array}\right] \\ \\ \\

R_{1}+4R_{4} \to R_{1},
R_{3}-8R_{4} \to R_{3},
\left[\begin{array}{cccc|c}
1 & 0 & 0 & 0 & -3 \\
0 & 1 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 & -6  \\
0 & 0 & 0 & 1 & 1
\end{array}\right] \\ \\ \\ \\
R_{2}-R_{3}\to R_{2}
\left[\begin{array}{cccc|c}
1 & 0 & 0 & 0 & -3 \\
0 & 1 & 0 & 0 & 6 \\
0 & 0 & 1 & 0 & -6  \\
0 & 0 & 0 & 1 & 1
\end{array}\right] \\ \\ \\ \\
 \\
\boxed{(-3,6,6,1)}

\end{align}
$$
The system is consistent (there is a solution)

# 7
Determine the value(s) of h such that the matrix is the augmented matrix of a consistent linear system.
$$
\begin{align}
\begin{bmatrix}
1 & h & 4 \\
5 & 10 & 16
\end{bmatrix} \\ \\ \\

\begin{bmatrix}
1 & h & 4 \\
5 & 10 & 16
\end{bmatrix} \\ \\ \\
R_{2} - 5R_{1} \to R_{2}
\begin{bmatrix}
1 & h & 4 \\
0 & 10 - 5h & -4
\end{bmatrix} \\ \\ \\
\end{align}
$$

# 8
$$
\begin{align}
\begin{bmatrix}
1 & 5 & -5 \\
2 & h & -10
\end{bmatrix} \\
R_{2} - 2R_{1}\to R_{2} \\
\begin{bmatrix}
1 & 5 & -5 \\
0 & h-10 & 0
\end{bmatrix} \\
\end{align}
$$
consistent for all values of h

# 9
$$
\begin{align}
\begin{bmatrix}
-12 & 15 & h \\
4 & -5 & 2
\end{bmatrix} \\
R_{1} + 3R_{2} \to R_{1} \\
\begin{bmatrix}
0 & 0 & h + 6 \\
4 & -5 & 2
\end{bmatrix} \\
\end{align}
$$
$h$ must be -6
# 10
# 11
# 12
$$
\begin{align}
\left[\begin{array}{ccc|c}
1 & -4 & 5 & g \\
0 & 2 & -3 & h \\
-2 & 6 & -7 & k
\end{array}\right] \\ \\

\left[\begin{array}{ccc|c}
1 & -4 & 5 & g \\
0 & 2 & -3 & h \\
0 & -2 & 3 & k+2g
\end{array}\right] \\
\left[\begin{array}{ccc|c}
1 & -4 & 5 & g \\
0 & 2 & -3 & h \\
0 & 0 & 0 & k+2g+h
\end{array}\right] \\

\end{align}
$$