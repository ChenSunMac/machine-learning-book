## Central Limit Theorem

设随机变量 $$X_1, X_2, ...$$ 互相独立，服从同一分布，并且具有相同的期望 $$\mu$$ 和 方差 $$\sigma^2$$, 那么随机变量Y: 



$$
\begin{equation}
Y_n = \frac{1}{\sqrt{n}\sigma}(\sum_{i = 1}^{n}X_i - n\mu)
\end{equation}
$$

的分布收敛到标准正态分布。


实际生活中，很多随机现象可以看做许多因素的独立影响的综合反映，往往近似服从正态分布


## Maximum likelihood estimation (MLE)

最大似然估计, a method of **estimating the parameters** of a statistical model **given observations**, by finding the parameter values that **maximize the likelihood** of making the observations given the parameters.

简单来说，就是从采样数据$$[X_1, ..., X_n]$$，以及估计的概率分布模型D,($$f_D(\theta_1,..., \theta_k)$$)，来求概率分布的参数 $$\theta_1,..., \theta_k$$;

这里的函数参数是我们通过采样样本数据估计得到的，我们有似然函数:

$$
\begin{equation}
L(x_1,x_2,....,x_n; \theta_1,...,\theta_k) = \prod_{i = 1}^n f(x_i; \theta_1, \theta_2, ..., \theta_k)
\end{equation}
$$

求参数的值，能够似的似然函数取最大值的方法就是最大似然估计。 

#### 实践：

一般先取对数，这样乘积变加法，然后再去偏导为0的点，也就是local maximum:

```
投硬币N次试验，n次朝上，N-n次朝下, 求估计的朝上的概率p:
```
STEP1:

$$
\begin{equation}
f(n|p) = \ln (p^n(1-p)^{N-n}) = n\ln p +(N-n)\ln (1 - p)
\end{equation}
$$

STEP2:

$$
\begin{equation}
\frac{\partial f(p)}{\partial p} = \frac{n}{p} - \frac{N-n}{1-p} \longrightarrow \hat p = \frac{n}{N}
\end{equation}
$$

```
求高斯分布的MLE:
```

STEP1: Pick the MODEL - Uniform Distribution

$$
\begin{equation}
f(x) = \frac{1}{\sqrt{2\pi} \sigma} e^{-\frac{(x - \mu)^2}{2\sigma^2}}
\end{equation}
$$


STEP2: Substitute the SAMPLES:

$$
\begin{equation}
L(X) = \prod^{n}_{i=1}\frac{1}{\sqrt{2\pi} \sigma} e^{-\frac{(X_i - \mu)^2}{2\sigma^2}}
\end{equation}
$$

STEP3: Take Log on both sides:

$$
\begin{eqnarray}
l(X) &=& \sum^{n}_{i=1}\log \frac{1}{\sqrt{2\pi} \sigma} e^{-\frac{(X_i - \mu)^2}{2\sigma^2}} \\
&=& \sum^{n}_{i=1}\log \frac{1}{\sqrt{2\pi} \sigma} + \sum^{n}_{i=1}\log -\frac{(X_i - \mu)^2}{2\sigma^2} \\
&=& \frac{-n}{2} \log (2\pi \sigma^2) - \frac{1}{2\sigma^2} \sum^{n}_{i=1}(X_i - \mu)^2
\end{eqnarray}
$$


STEP4: 对 \mu 和 \sigma 分别求偏导:

$$
\begin{eqnarray}
\mu = \frac{1}{n} \sum^{n}_{i=1} X_i \\
\sigma^2 = \frac{1}{n} \sum^{n}_{i=1}(X_i - \mu)^2
\end{eqnarray}
$$






