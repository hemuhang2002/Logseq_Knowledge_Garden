alias:: ranking loss,triplet loss

- [一文理解Ranking Loss/Margin Loss/Triplet Loss - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/158853633)
- 核心要点
	- 对于二元情况
	  $$L(r_0,r_1,y) = y ||r_0 - r_1|| + (1-y)max(0,m-||r_0-r_1||)$$其中m是个超参数
	  该公式的解释是：**对于正样本**，我希望他们距离小的时候loss小，**对于负样本**，我希望他们距离没有超过阈值m时候（这个时候任务距离还不够大，还没有区分开），他们举例越小，loss越大，可以继续训练，但是当他们之间的举例大于m时（此时根据max函数，第二项为0），不用继续更新
		- **对于正样本**，我希望他们距离小的时候loss小，**对于负样本**，我希望他们距离没有超过阈值m时候（这个时候任务距离还不够大，还没有区分开），他们举例越小，loss越大，可以继续训练，但是当他们之间的举例大于m时（此时根据max函数，第二项为0），不用继续更新
		  $$
		  \begin{array}{|c|c|c|}
		  \hline
		  \text{样本类型} & \text{距离} & \text{} \\
		  \hline
		  \text{正样本} & \text{距离小，loss小} & \text{更新，除非距离为0} \\
		  \hline
		  \text{负样本} & \text{loss随距离增大而增大} & \text{举例大于m，不用更新} \\
		  \hline
		  \end{array}
		  $$
	- 对于三元情况
	  $$L(r_a,r_p,r_n) = max(0,m+d(r_a,r_p)-d(r_a,r_n))$$
	  此时存在三种情况
	  ||Loss|解读|
	  |--|--|--|
	  |$$d(r_a,r_n)$$足够大|0|此时负样本分的很开，不用再更新|
	  |$$d(r_a,r_p)$$足够大|$$ m+d(r_a,r_p)-d(r_a,r_n)$$|此时正样本分的很开，需要再更新|
	  |$$ m+d(r_a,r_p)>d(r_a,r_n)$$|$$ m+d(r_a,r_p)-d(r_a,r_n)$$|此时对正样本的区分没有很理想，都没有比区分负样本更好，继续更新|