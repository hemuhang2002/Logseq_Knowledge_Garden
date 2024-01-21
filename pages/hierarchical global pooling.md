- 定义：为了解决global pooling存在的信息丢失问题而提出的分层聚合节点嵌入
- 举例：
	- 使用 \[\text{ReLU}(\text{Sum}(\cdot))\] 做聚合，先分别聚合前两个节点和后三个节点的嵌入，然后再聚合这两个嵌入。
		- \[(G_1)\]：
		  第一轮：\[( \hat{\mathbf{y}_a}=\text{ReLU}(\text{Sum}({-1,-2}))=0 ), ( \hat{\mathbf{y}_b}=\text{ReLU}(\text{Sum}({0,1,2}))=3 )\]
		  第二轮：\[( \hat{\mathbf{y}_G}=\text{ReLU}(\text{Sum}({\mathbf{y}_a,\mathbf{y}_b}))=3 )\]
		- \[(G_2)\]：
		  第一轮：\[( \hat{\mathbf{y}_a}=\text{ReLU}(\text{Sum}({-10,-20}))=0 ), ( \hat{\mathbf{y}_b}=\text{ReLU}(\text{Sum}({0,10,20}))=30 )\]
		  第二轮：\[( \hat{\mathbf{y}_G}=\text{ReLU}(\text{Sum}({\mathbf{y}_a,\mathbf{y}_b}))=30 )\]
	- 这样我们就可以将 \[(G_1)\] 和 \[(G_2)\] 作出区分了。
- 实际应用
	- [DiffPool](https://blog.csdn.net/PolarisRisingWar/article/details/118001121#fn10)
-