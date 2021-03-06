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

---
### Convex function
If the domain of function $$f$$ is convex and satisfy $$\forall x,y \in ~dom ~f, 0 \le \theta \le 1$$, if we have 
$$
\begin{equation}
f(\theta x + (1 - \theta)y) \le \theta f(x) + (1-\theta) f(y)
\end{equation}
$$
---

### 一阶可微 & 二阶可微

若 f 一阶可微， 那么 f 为convex function 当且仅当 f 的定义域dom f 为convex，且


$$
\begin{eqnarray}
\forall x, y \in dom~f, f(y) \ge f(x) + \nabla f(x)^T(y-x)
\end{eqnarray}
$$


若 f 二阶可微，那么 f 为convex function 当且仅当 f 的定义域dom f 为convex，且

$$
\begin{eqnarray}
\nabla ^2f(x) \succeq 0 
\end{eqnarray}
$$
- 若f是一元函数，$$\succeq 0 $$ 表示二阶导数 大于等于 0
- 若f是多元函数，$$\succeq 0 $$ 表示 二阶导 Hessian 矩阵半正定




---

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
\Gamma(x) &=& \int^{\infty}_{0}t^{x-1}e^{-t}dt \\
          &=& - \int^{\infty}_{0}t^{x-1}de^{-t} \\
          &=& -t^{x-1}e^{-t}|^{\infty}_{0} + \int^{\infty}_{0}e^{-t}dt^{x-1}\\
          &=& -{\infty}^{x-1} e^{-\infty} + 0^{x-1}e^{-0} + \int^{\infty}_{0}e^{-t}(x-1)t^{x-2}dt\\
          &=& (x - 1)\int^{\infty}_{0}t^{x-2}e^{-t}dt
          &=& (x - 1) \Gamma(x - 1)
\end{eqnarray}
$$







