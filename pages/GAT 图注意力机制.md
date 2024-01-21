- 公式：在其中加入了两个节点的注意力$$\alpha_{v,u}$$
  $$\mathbf{h}_v^{(l)} = \sigma\left(\sum_{u\in \mathcal{N}(v)} \alpha_{vu} \mathbf{W}^{(l)} \mathbf{h}_u^{(l-1)}\right)$$
- [[Design Space]]解释：
	- $$\mathbf{h}_v^{(l)} = \sigma\left(\sum_{u\in \mathcal{N}(v)} \alpha_{vu} \mathbf{W}^{(l)} \mathbf{h}_u^{(l-1)}\right)$$
	- 信息转换
	  $$m_u = \alpha_{vu} \mathbf{W}^{(l)} \mathbf{h}_u^{(l-1)}$$
	- 信息聚合
	  $$\sum_{u\in \mathcal{N}(v)} $$
- 计算$$\alpha_{v,u}$$的方式
	- 首先**使用两个节点上一层的节点嵌入**计算两个节点之间的关联系数，$$a$$**是定义的计算注意力的可学习网络**
	  $$\textcolor{blue}{e_{vu}} = a\left(\mathbf{W}^{(l)}\mathbf{h}_u^{(l-1)},\mathbf{W}^{(l)}\mathbf{h}_v^{(l-1)}\right)$$其中，$$a$$可以是一个简单的线性层
	  $$\textcolor{blue}{e_{vu}}=\text{Linear}\left(\text{Concat}\left(\mathbf{W}^{\left(l\right)}\mathbf{h}_u^{\left(l-1\right)},\mathbf{W}^{\left(l\right)}\mathbf{h}_v^{\left(l-1\right)}\right)\right)$$
	- 然后使用$$softmax$$计算$$\alpha_{v,u}$$
	  $$\alpha_{vu} = \frac{\exp(e_{vu})}{\sum_{u'\in\mathcal{N}(v)}\exp(e_{vu'})}$$
- GAT的multi-head attention
	- 目的：增加模型鲁棒性，使模型不卡死在奇怪的优化空间，在实践上平均表现更好。
	- 实现：**使用不同的几套**$$\textbf{a}$$计算出几套节点嵌入，然后求和或者拼接
	  $$\begin{aligned}
	  \mathbf{h}_v^{(l)}[1] &= \sigma\left(\sum_{u\in N(v)}\textcolor{green}{\alpha_{vu}^1}\mathbf{W}^{(l)}\mathbf{h}_u^{(l-1)}\right) \\
	  \mathbf{h}_v^{(l)}[2] &= \sigma\left(\sum_{u\in N(v)}\textcolor{green}{\alpha_{vu}^2}\mathbf{W}^{(l)}\mathbf{h}_u^{(l-1)}\right) \\
	  \mathbf{h}_v^{(l)}[3] &= \sigma\left(\sum_{u\in N(v)}\textcolor{blue}{\alpha_{vu}^3}\mathbf{W}^{(l)}\mathbf{h}_u^{(l-1)}\right)
	  \end{aligned}$$
	  $$\mathbf{h}_v^{(l)}=\text{AGG}\left(\mathbf{h}_v^{(l)}[1],\mathbf{h}_v^{(l)}[2],\mathbf{h}_v^{(l)}[3]\right)$$
- GAT的特点：
	- 效果好
	- **可以直接对新节点、新图进行计算**
		- 注意力机制只是学习了每一层中用于计算关联系数的函数$$a$$，当有新节点加入时，依旧可以根据$$a$$，计算出关联系数