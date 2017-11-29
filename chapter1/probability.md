# Probability

- 概率(Probability): $$P(x) \in [0,1]$$
- 累计分布函数(Cumulative distribution function): $$\Phi(x) = P(x\le x_0)$$


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
# 条件概率(Conditional Probability)：
Conditional probability is a measure of the probability of an event given that (by assumption, presumption, assertion or evidence) another event has occurred.
那么事件A在条件B的基础上发生的概率是：
$$
\begin{equation}
P(A|B) = \frac{P(A \cap B)}{P(B)}
\end{equation}
$$

那么当有很多事件影响时，即考虑($$B_i, i > 1$$):
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
- $$P(\theta)$$ 是没有数据支持下，$$\theta$$发生的概率：先验概率
- $$P(\theta|x)$$ 是在数据x的支持下，$$\theta$$发生的概率：后验概率
- $$P(x|\theta)$$ 给定某参数$$\theta$$的概率分布：似然函数


---
### Bernoulli Distribution


 
  

### 