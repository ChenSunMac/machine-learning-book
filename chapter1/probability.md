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


### Beta Distribution