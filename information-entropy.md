# Information Entropy

Information entropy is defined as the average amount of information produced by a stochastic source of data.

熵的概念最早起源于物理学，用于度量一个热力学系统的无序程度。在信息论里面，熵是对不确定性的测量，又叫做**平均信息量**。但是在信息世界，熵越高，则能传输越多的信息，熵越低，则意味着传输的信息越少。

简单来说，我们知道用二进制，1bit 可能有 0 或者 1 这两个值，完全随机的话可以说二者概率分别为0.5;

那么 2 bit 可能有 00, 01, 10, 11四个值，完全随机的话可以说他们的概率分别为 0.25...

也就是说当面对的事件越不确定，相对而言这个事件的信息量就越多，那么信息熵就越大.

Shannon defined the entropy Η of a discrete random variable X with possible values $$\{x_1, ..., x_n\}$$ and its probability $$p(x)$$ as :

$$
\begin{equation}
H(X) = -\sum_{i=1}^n p(x) 
\end{equation}
$$