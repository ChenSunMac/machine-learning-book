## 决策树 数学模型及推导

给定训练数据
$$x_i \in R^n, i=1,…,l$$  
以及标签好的y 
$$y \in R^l$$, 
A **decision tree** recursively partitions the space such that the samples with the same labels are grouped together. 
决策树递归的将这些数据和对应的标签划分到一起，递归的建树。


### ID3 算法
在这里，我们的输入是m个样本，实际上是m行的table，每个样本有n个离散特征，特征集合为A



