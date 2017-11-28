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

### $$N\rightarrow \infty \Rightarrow \ln N! \rightarrow N(\ln N - 1) $$

$$\ln N! = \ln \prod_{i = 1}^{N} i = \sum_{i = 1}^{N}\ln i \approx \int_1^N \ln x dx$$

```
a^x + b = c
```
$$
\begin{eqnarray}
\ln N!  &=& \ln \prod_{i = 1}^{N} i = \sum_{i = 1}^{N}\ln i \approx \int_1^N \ln x dx\\
        &=& x\ln x|^{N}_{1} - \int_1^N x d\ln x \\
        &=& N \ln N - \int_1^N x \frac{1}{x} dx \\
        &=& N\ln N - N + 1 \\
        &\rightarrow& N\ln N - N
\end{eqnarray}
$$


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



### Gradient




