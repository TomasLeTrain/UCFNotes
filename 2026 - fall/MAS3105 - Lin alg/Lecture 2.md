
### Section 1.1
review


## Section 1.2 - Row reductions & Echelon forms

solve system of equations through matrix form:

Echelon form and reduced echelon form (matrix forms that make it easy to find solutions). Can use "legal" row operations to transform the graph:
- $n$ * row (where $n \neq 0$): $\alpha R_{i} \to R_{i}$
- add a multiple of one row to another: $R_{i}+kR_{j} \to R_{i}$
- swap 2 rows: $R_{i} \leftrightarrow R_{j}$

*Must denote all operations to not lose points*

**Leading Entry:** first non-zero # (from left to right) (nop basically)

**Examples:**
1.
$$
\begin{align} \\
\left[\begin{array}{ccc|c}
1 & 0 & 3 & 4 \\
0 & 1 & -1 & 5 \\
0 & 0 & 0 & 0
\end{array}\right] \\
\boxed{ R_{1} + R_{2}*3 \to R_{1} } \\
\left[\begin{array}{ccc|c}
1 & 3 & 0 & 19 \\
0 & 1 & -1 & 5 \\
0 & 0 & 0 & 0
\end{array}\right]  \\
\to \\
x_{1}=19-3x_{2} \\
x_{2}=5+x_{3} \\
\to \\
x_{1}=19-3(5+x_{3}) \\
x_{1}=19-15-3x_{3} \\ \\

x_{1}=4 - 3x_{3} \\
x_{2}=5+x_{3} \\
x_{3} = \text{any num}

\end{align}
$$

The original matrix was in an easier form already, transforming give same answer but more steps.


2.
$$
\begin{align}
\left[\begin{array}{ccc|r}
1 & 2 & 6 & -8 \\
0 & 1 & -2 & 3 \\
0 & 0 & 0 & 0
\end{array}\right] \\ \\

1x_{1}+2x_{2}+6x_{3}=-8 \\
1x_{2}-x_{3}=3 \\
 \\
x_{1}=-8-2x_{2}-6x_{3} \\
x_{2}=3+2x_{3} \\
 \\
x_{1}=-8-2(3+2x_{3})-6x_{3} \\
x_{1}=-8-6-4x_{3}-6x_{3} \\ \\

x_{1}=-14-10x_{3} \\
x_{2}=3+2x_{3} \\
x_{3} = \text{any \#}

\end{align}
$$

3.
$$
\begin{align}
\left[\begin{array}{ccc|c}
2 & 0 & 6 & 8 \\
0 & 1 & -1 & 5 \\
0 & 0 & 0 & 0
\end{array}\right] \\

2x_{1}+6x_{3}=8 \\
x_{2}-x_{3}=5 \\
 \\
x_{1}=4-3x_{3} \\
x_{2}=5+x_{3} \\
x_{3}=\text{any \#}
\end{align}
$$

$$
\begin{align}
\left[\begin{array}{ccc|c}
1 & 3  & -4 & -5 \\
2 & 1 & 5 & 7 \\
0 & 0 & 0 & 0
\end{array}\right] \\
x_{1}+3x_{2}-4x_{3}=-5 \\
2x_{1}+x_{2}+5x_{3}=7 \\
 \\
R_{2} - 2R_{1} \to R_{2} \\
 \\
x_{1}+3x_{2}-4x_{3}=-5 \\
-5x_{2}+13x_{3}=17 \\
 \\
x_{1}=-5-3x_{2}+4x_{3} \\
-5x_{2}=17 - 13x_{3} \\

 \\
x_{1}=-5-3x_{2}+4x_{3} \\
x_{2}=-\frac{17}{5} + \frac{13 x_{3}}{5} \\

x_{1}=-5-3\left( -\frac{17}{5} + \frac{13 x_{3}}{5} \right) +4x_{3} \\
x_{2}=-\frac{17}{5} + \frac{13 x_{3}}{5}
 \\
x_{1}=-5 +\frac{17 * 3}{5} - \frac{13 * 3* x_{3}}{5} +4x_{3} \\
x_{2}=-\frac{17}{5} + \frac{13 x_{3}}{5} \\

x_{1}=-5 +\frac{51}{5} + x_{3}(4 - \frac{39}{5}) \\
x_{2}=-\frac{17}{5} + \frac{13 x_{3}}{5}

\end{align}
$$


**Leading Entry:** first number (left to right) in the row that is non zero is the leading entry.

**Echelon form:** 
1. all non-zero rows are above any rows with all zeroes (all zero-rows should be at the bottom).
2. The columns of leading entries should be **strictly** increasing as row increases (the lower we go, the more to the right the leading entry). Two rows cannot have the same leading entry since its strictly increasing.
3. all numbers below a leading entry will be zero (follows from 2).

**Example**
$$
\left[\begin{array} \\
0 & \boxed{ 3 } & 0 & -1 & \dots \\
0 & 0 & 0 & \boxed{ 8 } & \dots \\
0 & 0 & 0 & \boxed{ 2 } & \dots \\
0 & 0 & 0 & 0 & \dots
\end{array}\right]
$$
This matrix is **not** in echelon form since both 8 and 2 share the same leading entry.

*Remark:* All matrices can be reduced to *some* echelon form and a *unique* reduced echelon form

**Reduced Echelon form:** a matrix which when in **echelon form** satisfies some conditions:
1. All leading entries are a 1
2. All Leading entries must be only non-zero in column. 


Theorem 1: Uniqueness of hte reduced echelon form
The reduced echelon form of a matrix is **unique**.
Or in other words: Each matrix is row equivalent to a unique reduced echelon matrix.


**Pivot position:** The positions of the leading entries of the reduced echelon form. (can talk about pivot position even if matrix is not in ech form).

**Pivot column:** a column that has a pivot position
**pivot:** nonzero \# in a pivot position.

## Reducing matrix to EF

1. find first non-zero column
2. make that column be non-zero in first row by using the "legal" moves.
3. now that first row will have a **pivot position**, so afterward we must make everything under it zero (through allowed transformations).
4. now we can reduce the problem to now be the column-row after the current one.
5. repeat these steps for the smaller matrix until the whole matrix is in echelon form



## reducing EF to REF
going from **right to left**
Find the first pivot point starting from the right, then make everything above it zero. Repeat that for all remaining zeroes. When doing transformations, keep in mind rows used for transformations (keep echelon form, use rows below current when doing transformations).

**Basic/dependent:** variable that has pivot col
**Free variable:** if no pivot col for variable