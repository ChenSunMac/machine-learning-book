## Decision Tree

Decision Tree 决策树 是一种树型结构，每个内部节点表示在一个属性上的测试，每个分支表示测试输出，每个叶节点代表的是一种类别。

决策树学习是自顶向下的递归方法，他是以信息熵为度量构造一棵熵值下降最快的树，到叶子结点处的熵值为0，此时每个叶节点中的实例都属于同一类。

决策树学习算法不需要使用者了解过多背景知识，只需要对训练实例进行较好的标注，就能够进行学习；属于有监督学习（supervised learning）
可以从一类无序，无规则的事物（概念）中推理出决策树表示的分类规则。

## 决策树生成算法

建立决策树的关键，就是在当前状态下选择哪个属性作为分类依据。

*信息增益* 表示得知特征属性A的信息而使得类X的信息的不确定性减少的程度。

特征A对训练数据集D的信息增益 g(D,A) = H(D) - H(D|A)

 H(D)表示数据集的经验熵(Entropy), H(D|A) 是特征A给定条件下数据集的经验熵。
 
 那么我们假设|D|代表数据集样本个数， 同时有K个类$$C_k$$， k = 1,2,... K; |$$C_k$$| 表示属于类Ck的样本个数，那么 $$\sum_{k} |C_k| = |D|$$
 
 我们可以把经验熵写成： 
 
 $$H(D) = -\sum_{k=1}^{K} \frac{|C_k|}{|D|}\log \frac{|C_k|}{|D|}$$
 
 
那么一般来说我们希望遍历所有特征，对于特征A：
我们计算A的信息增益
最后选择信息增益最大的特征作为当前的分裂特征。


## Overfitting and Solution
决策树对训练有很好的分类能力，但是泛化能力比较弱，容易overfitting.

**BootStrap Aggregation （BAGGING）**, bootstraping 来自成语 'pull up by your own bootstraps'，意为依靠自身力量让自己变得更好。是一种有放回的抽样方法：
1. 从样本中有重复的选出n个样本，
2. 在所有属性上，对这n个样本建立分类器 （Logistic, SVM, CART, ID3 等等皆可）
3. 重复以上两步m次，获得m个分类器
4. 将数据集放在这m个分类器上，最后根据结果投票决定数据属于哪一类。

**Random Forest 随即森林**，在第二步做了修改
1. 从样本中有重复的选出n个样本，
2. 在所有属性上随机选择k个属性，对这n个样本建立CART决策树
3. 重复以上两步m次，获得m个CART决策树
4. 这m个CART形成随即森林，最后根据结果投票决定数据属于哪一类。


## 总结
Decision Tree 代码清晰，逻辑简单，在分类问题上比较适合，同时也可以作为对数据分布探索的**首要尝试算法**。




