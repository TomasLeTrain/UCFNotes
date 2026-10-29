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

