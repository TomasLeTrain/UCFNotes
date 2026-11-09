practice problems for section 6.1
6.2,6.7,6.8,6.9,6.10

# 1 
*The random variable X has the cumulative distribution function*
$$
\begin{align}
F(x) = 1 - \frac{\alpha}{x^{2}} \text{ if } x \geq 5 \text{ and } 0 \text{ if } x <5
\end{align}
$$
*Unfortunately, I spilled co↵ee on the book that I read this problem in and I could not read the number in the place where I put the constant $\alpha$ :( Sorry about that. Find*
a. $\alpha$ without finding the pdf
$b$. $\alpha$ by finding the pdf
$c$. $P(X > 10 | X < 20)$
$d$. $P(X > 20 | X < 10)$

## a
$$
\begin{align}
0 = F(5) = 1 - \frac{\alpha}{5^{2}} \\
\boxed{ \alpha = 25 }
\end{align}
$$
## b
$$
\begin{align}
f(x) = F'(x) = \frac{d}{dx} \left(1-\frac{\alpha}{x^{2}}\right) \\
f(x) = \frac{2\alpha}{x^{3}} \\
\int_{-\infty}^{\infty} f(x) \, dx = 1 \\
\int_{5}^{\infty} -\frac{2\alpha}{x^{3}} \, dx = 1 \\
\left.\left( \frac{\alpha}{x^{2}} \right)\right|_{5}^{\infty} = 1 \\ \\
(1- 0) -(1-\frac{\alpha}{5^{2}}) = 1
\frac{\alpha}{5^{2}} = 1
\boxed{ \alpha=5^{2} = 25 }
\end{align}
$$

# Class Lecture
## Example 1d
The join density function of $X$ and $Y$ is given by
$$
\begin{align}
f(x,y) = \left\{\begin{array}{cc}
2e^{-x}e^{-2y} & 0 < x < \infty, 0 < y < \infty \\
0  & \text{otherwise}
\end{array}\right.
\end{align}
$$
Compute (a) $P\{X > 1, Y < 1\}$, (b) $P\{X < Y\}$, and (c) $P\{X < a\}$, (d) $P\{X < -1, Y < 1\}$

Must first find the PDF
$$
\begin{align}
F(a,b)= \int_{-\infty}^{a} \int_{-\infty}^{b} f(x,y) \, dy  \, dx  \\
= \int_{0}^{a} \int_{0}^{b} 2e^{-x}e^{-2y} \, dy  \, dx  \\
= \int_{0}^{a} \left.2e^{-x}\left( \frac{1}{-2} \right)e^{-2y} \right|_{0}^{b} \, dx  \\
= -\int_{0}^{a} e^{-x}(e^{-2b}-1) \, dx  \\
= \left. e^{-x}(e^{-2b}-1) \right|_{0}^{a}  \\
= e^{-a}(e^{-2b}-1) - (e^{-2b}-1) \\
\boxed{ = (e^{-a}-1)(e^{-2b}-1)  }
\end{align}
$$

So a:
$$
\begin{align}
P\{ X > 1, Y < 1 \} = F_{y}(1) - F(1,1)
\end{align}
$$
$b$:
$$
\begin{align}
P\{ X < Y \} = ? \\
\int_{-\infty}^{\infty} \int_{x}^{\infty} f(x,y) \, dy \, dx  \\
\int_{0}^{\infty} \int_{x}^{\infty} e^{-x}e^{-2y} \, dy \, dx  \\
\int_{0}^{\infty} \left. -\frac{2}{2}e^{-x}e^{-2y}\right|_{0}^{x} \, dx  \\
-\int_{0}^{\infty}  e^{-x}(e^{-2x} -  1) \, dx  \\
\left. e^{-x}(e^{-2x} -  1) \right|_{0}^{\infty} \\
e^{-\infty}(e^{-2\infty} -  1) -  e^{-0}(e^{0} -  1) \\
\boxed{ 0(0 -  1) -  1(1 -  1) = 0 }
\end{align}
$$