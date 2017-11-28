# Math Knowledge

### Derivative

| Expresion | Derivative |
| :--- | :--- |
| C | 0 |
| $$x^n$$ | $$nx^{n-1}$$ |
| $$\sin~x$$ | $$\cos~x $$ |
| $$a^x$$ | $$a^x\ln a$$ |
| $$e^x$$ | $$e^x$$ |
| $$\log_ax$$ | $$\frac{1}{x}\log_ae$$ |
| $$\ln x$$ | $$\frac{1}{x}$$ |
| $$(u + v)$$ | $$u' + v'$$ |
| $$(u\cdot v)$$ | $$u'v + uv'$$ |

---


### Taylor's theorem and polynomial

$$
\begin{equation}
f(x) = f(a) + f'(a)(x - a) + \frac{f''(a)}{2!}(x - a)^2  + ... + \frac{f^{(k)}(a)}{k!}(x - a)^k + R_k(a)
\end{equation}
$$

Numerical way of expressing $$e^x$$:
$$
\begin{equation}
f(x) = f(a) + f'(a)(x - a) + \frac{f''(a)}{2!}(x - a)^2  + ... + \frac{f^{(k)}(a)}{k!}(x - a)^k + R_k(a)
\end{equation}
$$

---

### Gradient

如果函数$$z = f(x,y)$$ 在点$$z_1(x,y)$$是 defferential,那么，函数在该点沿任一方向$$L$$的方向导数(
Directional derivative)都存在:
$$
\begin{equation}
\frac{\partial f}{\partial l} = \frac{\partial f}{\partial x}\cos \phi + \frac{\partial f}{\partial y}\sin \phi
\end{equation}
$$
where $\phi$ 是x轴到方向L的转角

若$$z = f(x,y)$$在区域D内有一阶连续偏导, 那么对于每一个点 $$P(x,y) \in D$$，梯度是:
$$
\begin{equation}
\nabla f= grad~f(x,y) = (\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y})
\end{equation}
$$

Gradient的方向应该是函数 $$z = f(x,y)$$ 在该点变化最快的方向，所以Gradient descent algorithm 利用$$z = f(x,y)$$ decreases fastest if one goes from $$(x,y)$$  in the direction of the negative gradient of $$z$$ at (x,y), e.g.  $$\nabla f(x,y)$$


### Useful approximation: $$N\rightarrow \infty \Rightarrow \ln N! \rightarrow N(\ln N - 1) $$

We can observe the following:
$$
\begin{eqnarray}
\ln N! &=& \ln \prod_{i = 1}^{N} i = \sum_{i = 1}^{N}\ln i \approx \int_1^N \ln x dx\\
&=& x\ln x|^{N}_{1} - \int_1^N x d\ln x \\
&=& N \ln N - \int_1^N x \frac{1}{x} dx \\
&=& N\ln N - N + 1 \\
&\rightarrow& N\ln N - N
\end{eqnarray}
$$

---
### Useful function: $$\Gamma(x) = (x-1)\Gamma(x - 1)$$
$$\Gamma(x)$$ 是阶乘在实数上的推广
$$
\begin{eqnarray}
\Gamma(x) = \int^{\infty}_{0}t^{x-1}e^{-t}dx = (x-1)!
\end{eqnarray}
$$





