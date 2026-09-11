# 1.4 (continued)
can reuse solutions in certain cases:
$$
\begin{align}
A \vec{x} = \vec{b} \to \\
A_{1} \vec{x_{1}} + A_{2} \vec{x_{2}} + \dots = \vec{b} \\
\end{align}
$$

Same solution to the system $A_{1} \vec{x_{1}} + A_{2} \vec{x_{2}} + \dots = \vec{b}$  is  $A_{1} \vec{x_{1}} + A_{2} \vec{x_{2}} + \dots = \vec{0}$, except  replace the constants on the right for zeroes when its in the RREF form.

# Example 3

$$
\begin{align}
A=\begin{bmatrix}
0 & 3 & -6 & 6 & 4 \\
3 & -7 & 8 & -5 & 8 \\
3 & -9 & 12 & -9 & 6
\end{bmatrix}, B = \begin{bmatrix}
-4 \\
9 \\
15
\end{bmatrix} \\
 \\
A \vec{x} = \vec{b}
\end{align}
$$

1. solve $A \vec{x} = \vec{0}$
2. solve $A \vec{x} = \vec{b}$
3. Write your solution to 1. and 2. as vector eqs


We do 2nd first since solution to 1 becomes free

## 2
$$
\begin{align} \\
\left[\begin{array}{ccccc|c}
0 & 3 & -6 & 6 & 4 & -4 \\
3 & -7 & 8 & -5 & 8 & 9 \\
3 & -9 & 12 & -9 & 6  & 15 \\
\end{array}\right] \\ \\
\text{swap $R_{1}$ and $R_{2}$} \to \\

\left[\begin{array}{ccccc|c}
3 & -7 & 8 & -5 & 8 & 9 \\
0 & 3 & -6 & 6 & 4 & -4 \\
3 & -9 & 12 & -9 & 6  & 15 \\
\end{array}\right] \\ \\
\end{align}
$$


$$
\begin{align}
\left[\begin{array}{ccc|c}
1 & 3 & -3 & -15 \\
-2 & -2 & 2 & 26 \\
-3 & -7 & 3 & 27
\end{array}\right] \\
 \\

\left[\begin{array}{ccc|c}
1 & 3 & -3 & -15 \\
0 & 4 & -4 & -4 \\
0 & 2 & -6 & -3
\end{array}\right] \\
 \\
\left[\begin{array}{ccc|c}
1 & 3 & -3 & -15 \\
0 & 1 & -1 & -1 \\
0 & 0 & 1 & \frac{1}{4}
\end{array}\right]
 \\ \\
\left[\begin{array}{ccc|c}
1 & 3 & 0 & -12 \\
0 & 1 & -1 & -1 \\
0 & 0 & 1 & \frac{1}{4}
\end{array}\right]
 \\ \\
 
\left[\begin{array}{ccc|c}
1 & 3 & 0 & -12 \\
0 & 1 & 0 & -\frac{3}{4} \\
0 & 0 & 1 & \frac{1}{4}
\end{array}\right] \\

\left[\begin{array}{ccc|c}
1 & 0 & 0 & -10 + \frac{1}{4} \\
0 & 1 & 0 & -\frac{3}{4} \\
0 & 0 & 1 & \frac{1}{4}
\end{array}\right]
\end{align}
$$