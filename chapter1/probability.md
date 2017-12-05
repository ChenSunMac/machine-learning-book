# Probability

* 概率\(Probability\): $$P(x) \in [0,1]$$
* 累计分布函数\(Cumulative distribution function\): $$\Phi(x) = P(x\le x_0)$$

## Example：

把n个求放入N个盒子中，假设盒子容量无限，求事件A = {每个盒子至多有一个球}的概率

```
基本事件总数：
    第一个球: N种放法；
    第二个球：N种放法；
    。。。
```

一共$$N^n$$种放法

```
每个盒子至多有一个球的事件数：
    第一个球：N种；
    第二个球：N-1种；
    。。。
```

一共 $$N(N-1)(N-2)...(N-n+1) = P^n_N$$, 所以概率应该是$$\frac{P^n_N}{N^n}$$

---

# 条件概率\(Conditional Probability\)：

Conditional probability is a measure of the probability of an event given that \(by assumption, presumption, assertion or evidence\) another event has occurred.  
那么事件A在条件B的基础上发生的概率是：


$$
\begin{equation}
P(A|B) = \frac{P(A \cap B)}{P(B)}
\end{equation}
$$


那么当有很多事件影响时，即考虑\($$B_i, i > 1$$\):


$$
\begin{equation}
P(A) = \sum_i P(A|B_i) P(B_i)
\end{equation}
$$


## Bayes' theorem

Bayes' theorem describes the probability of an event, based on prior knowledge of conditions that might be related to the event.


$$
\begin{equation}
P(B_i|A) = \frac{P(A | B_i)P(B_i)}{\sum_{j} P(A|B_j)P(B_j)}
\end{equation}
$$


我们也可以简化它变成:


$$
\begin{equation}
P(\theta|x) = \frac{P(x | \theta)P(\theta)}{P(x)}
\end{equation}
$$


* $$P(\theta)$$ 是没有数据支持下，$$\theta$$发生的概率：先验概率
* $$P(\theta|x)$$ 是在数据x的支持下，$$\theta$$发生的概率：后验概率
* $$P(x|\theta)$$ 给定某参数$$\theta$$的概率分布：似然函数

---

## 期望E() 和 方差 D(X)

**期望是概率加权下求平均值**
- E(X + Y) = E(X) + E(Y)
- 若 X 和 Y 独立， 则 E(XY) = E(X) E(Y)

**方差也写作var**
$$D(X) = E(X^2) - [E(X)]^2$$
- $$Var(c) = 0$$
- $$Var(X+c) = 0$$
- $$Var(kX) = k^2Var(X)$$


**协方差 (Covariance)**, is a measure of the joint variability of two random variables.
也就是两个随机变量具有相同方向变化趋势的度量

$$
\begin{equation}
Cov(X, Y) = E{[ X- E(X) ] [Y - E(Y)] }  = E(XY) - E(X) E(Y)
\end{equation}
$$

- 若 $$Cov(X, Y) > 0$$, 他们变化趋势相同
- 若 $$Cov(X, Y) < 0$$, 他们变化趋势相反
- 若 $$Cov(X, Y) = 0$$, 他们不相关


**协方差 (Covariance) 矩阵(Matrix)**:

对于n个随机向量$$[x_1,x_2,x_3...,x_n]$$, 任意两个元素之间都可以得到一个协方差, 从而形成一个**n*n**的对称矩阵：

$$
\begin{equation}
c_{i, j} = E{[ X_i- E(X_i) ] [X_j - E(X_j)] } 
\end{equation}
$$

---
## Chebyshev's inequality

显示了随机变量的"几乎所有"值都会"接近"**平均**

$$
\begin{equation}
c_{i, j} = E{[ X_i- E(X_i) ] [X_j - E(X_j)] } 
\end{equation}
$$





---

### Bernoulli Distribution

| X | 1 | 0 |
| :--- | :--- | :--- |
| P | p | q = 1- p |

- $$E(X) = 1\times p + 0 \times p = p$$
- $$D(X) = E(X^2) - [E(X)]^2 = pq$$

**Negative binomial distribution** 描述了事件成功概率为p,直到r次成功，总实验次数X的概率为:



$$
\begin{equation}
P(X = x; r, p) = C^{r-1}_{x-1} p^r(1-p)^{x-r}
\end{equation}
$$


### Poisson Distribution

Poisson distribution is a discrete probability distribution that expresses the probability of a given number of events occurring in a fixed interval of time or space if these events occur with a known constant rate and independently of the time since the last event.

也就是说当一个随机事件，以固定的平均瞬时速率$$\lambda$$随机且独立的出现时，那么这个事件在单位时间内出现的次数服从泊松分布。（它的分布律和Taylor展开式里的项很像）


$$
\begin{equation}
P\{X = k\} = \frac{\lambda^k}{k!} e^{-\lambda},~~~k = 0,1,2,...,~~ \lambda > 0
\end{equation}
$$

- $$E(X) = \sum_{k=0}^{\infty} k \frac{\lambda^k}{k!}e^{-\lambda} = \lambda$$
- $$D(X) = E(X^2) - [E(X)]^2 = \lambda$$

泊松分布的期望值和方差都等于参数$$\lambda$$

### Uniform Distribution
The probability density function of the continuous uniform distribution is:


$$ 
f(x) = \frac{1}{b-a} , \forall a \le x \le b,
$$


other points, $$f(x) = 0$$
- $$E(X) = \frac{1}{2}(a+b)$$
- $$D(X) = E(X^2) - [E(X)]^2 = \frac{1}{12}(b-a)^2$$

### Exponential Distribution

Exponential distribution is the probability distribution that describes the time between events in a **Poisson point process**, i.e. a process in which events occur **continuously and independently** at a constant average rate. It is a particular case of the **gamma distribution**. It is the continuous analogue of the geometric distribution, and it has the key property of being **memoryless**. In addition to being used for the analysis of Poisson point processes it is found in various other contexts.

这里这个函数和泊松分布很像
$$
\begin{equation}
f(x) = \frac{1}{\lambda}e^{\frac{-x}{\lambda}},~x>0,~\lambda > 0
\end{equation}
$$

- $$E(X) = \int^{\infty}_{0} x\frac{1}{\lambda}e^{\frac{-x}{\lambda}}dx = \lambda$$
- $$D(X) = E(X^2) - [E(X)]^2 =\lambda^2$$


### Normal/Gaussian Distribution
The normal distribution is useful because of the central limit theorem. In its most general form, under some conditions (which include finite variance), it states that averages of samples of observations of random variables independently drawn from independent distributions converge in distribution to the normal, that is, become normally distributed when the number of observations is sufficiently large. Physical quantities that are expected to be the sum of many independent processes (such as measurement errors) often have distributions that are nearly normal.

$$
\begin{equation}
f(x|\mu,\sigma^2) = \frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{(x-\mu)^2}{2\sigma^2}},~\sigma > 0, -\infty < x < \infty
\end{equation}
$$

- $$E(X) = \int^{\infty}_{0}  x f(x)dx = \mu$$
- $$D(X) = E(X^2) - [E(X)]^2 =\sigma^2$$


### Beta Distribution

The beta distribution has been applied to model the behavior of random variables limited to intervals of finite length in a wide variety of disciplines.

In Bayesian inference, the beta distribution is the conjugate prior probability distribution for the Bernoulli, binomial, negative binomial and geometric distributions. For example, the beta distribution can be used in Bayesian analysis to describe initial knowledge concerning probability of success such as the probability that a space vehicle will successfully complete a specified mission. The beta distribution is a suitable model for the random behavior of percentages and proportions.


$$
\begin{equation}
f(x) = \frac{1}{B(\alpha, \beta)} x^{\alpha - 1}(1 - x)^{\beta - 1}, x\in[0,1]
\end{equation}
$$

where 


$$
\begin{equation}
B(\alpha, \beta) = \int^{1}_{0} x^{\alpha - 1}(1 - x)^{\beta - 1} dx = \frac{\Gamma(\alpha)\Gamma(\beta)}{\Gamma(\alpha + \beta)}
\end{equation}
$$

- $$E(X) = \frac{\alpha}{\alpha + \beta}$$
- $$D(X) = E(X^2) - [E(X)]^2 =\frac{\alpha \beta}{(\alpha + \beta)^2}$$





