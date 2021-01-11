# 基于LSTM的移动对象位置预测算法

## Summary
作者在考虑移动对象行为具有相似性和时效性的基础上，对历史轨迹位置向量进行降维，学习一个全局的位置预测模型，提高了预测模型的效率和精确度。
本文的重点在于数据降维和LSTM的应用。

## Notes
1. 移动对象轨迹数据的位置预测问题：
	* 马尔科夫链： 建立转移矩阵以推测下一步最可能到达的位置
	* 轨迹频繁模式挖掘：通过挖掘频繁模式找出典型运动模式
	* 循环神经网络RNN：通过隐藏层神经元的连接性处理序列数据，以学习运动模型
缺点：
	针对短时间轨迹序列，没有考虑到过长的历史信息会带来的维数灾难，不能解决长序列轨迹的位置预测问题。尤其是GPS采样周期短，收集到的数据多且连续。

2. 传统方法——轨迹频繁模式挖掘：
	将原始轨迹按密度聚类，将轨迹线段划分到不同的类簇中，以聚类序列表示轨迹。这种虽然能在保证划分意义的前提下缩短序列长度，但基于密度的聚类方法不仅时间复杂度大，而且会忽略聚类区域之外的离散轨迹。
	
3. 深度方法——LSTM：
	LSTM要求降低输入维度的向量，否则循环神经网络隐藏层和输入层的神经元之间的全连接属性会导致严重的维数灾难，增大开销，降低模型的学习效率。
	内容讲解：
	
	![Sturcture_of_LSTM_network](.\img_for_md\Sturcture_of_LSTM_network.png)
	
	
	
	
	
4. 数据降维：

  对轨迹数据进行预处理，常用网格化的方法。但这里考虑了经纬度信息。

  其核心思想是将移动对象所在平面划分成网格，将精确但冗余的经纬度信息转化为抽象的王哥信息，以便对移动对象进行预测。
## Relative works
[12] 通过张量分解（tensor factorization，TF）的方式，同时考虑历史轨迹信息中的地理位置信息和时间信息。上述算法都基于对移动对象历史访问记录的挖掘，没有考虑当前移动对象位置及轨迹，得到的预测精度不高。

[17] 出一种用因式分解转移概率矩阵的方法扩展了马尔科夫链模型，在时空数据的位置预测上取得了很好的效果。

[18] 用隐马尔可夫模型（hidden Markov model，HMM）计算移动轨迹序列中的**隐状态**来计算移动对象概率最高的下一个位置。

但多阶MC模型尤其是高阶 MC 模型，当数据增加时状态会呈爆炸式增长，转移概率矩阵规模的膨胀增加了预测的复杂度。


## References
 [12] Xiong L, Chen X, Huang T K, et al. Temporal collaborative filtering with Bayesian probabilistic tensor factorization[C]// Proceedings of the SIAM International Conference on Data Mining, Columbus, Apr 29-May 1, 2010. Philadelphia: SIAM, 2010: 211-222. 

 [17] Rendle S, Freudenthaler C, Schmidt-Thieme L. Factorizing personalized Markov chains for next-basket recommendation [C]//Proceedings of the 19th International Conference on World Wide Web, Raleigh, Apr 26-30, 2010. New York: ACM, 2010: 811-820. 

[18] Mathew W, Raposo R, Martins B. Predicting future locations with hidden Markov models[C]//Proceedings of the ACM Conference on Ubiquitous Computing, Pittsburgh, Sep 5-8, 2012. New York: ACM, 2012: 911-918. 

