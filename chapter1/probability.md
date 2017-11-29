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



# 条件概率(Conditional Probability)：
Conditional probability is a measure of the probability of an event given that (by assumption, presumption, assertion or evidence) another event has occurred.
$$
\begin{equation}
P(A|B) = \frac{P(A \cap B)}{P(B)}
\end{equation}
$$

