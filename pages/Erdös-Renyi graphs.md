- 一个简单的图生成模型，分为两种变体
  collapsed:: true
	- $G_{np}$, $n$ 个节点的无向图，每条边 $(u, v)$ 以概率 $p$ 独立同分布生成
	- $G_{nm}$,有 $n$ 个节点的无向图，随机生成 $m$条边
- $G_{np}$，考察相应的[图属性]( ((65a89001-d1ad-461a-b687-64c42cdd328f)) )
  collapsed:: true
	- 度分布
	  $$
	  P(k) = C_{n-1}^k p^k (1-p)^{n-1-k}
	  $$其中，$C_{n-1}^k$ 是组合数，表示从 $n-1$ 个节点中选择 $k$ 个节点的组合数。$p$ 是每条边出现的概率，$1-p$ 是边不出现的概率。
	  
	  $$\bar{k}=p(n-1)$$
	  $$\sigma^2=p(1-p)(n-1)$$
	  是一个类似于高斯分布的模拟
	- [[聚类系数]]
	  首先公式定义：
	  $$
	  C_{i}=\frac{e_{i}}{C_{k_{i}}^2}=\frac{2e_{i}}{k_{i}(k_{i}-1)}
	  $$
	  然后节点$i$的邻居节点边的个数期望（概率乘上最大边数）：
	  $$E[e_i] = p \cdot C_{k_i}^2 = p \cdot \frac{k_i(k_i-1)}{2}$$
	  代入上述公式：
	  $$E[C_{i}]=\frac{E\left\lbrack e_{i}\right\rbrack}{e_{all}}=\frac{E\left\lbrack e_{i}\right\rbrack}{C_{k_{i}}^2}=\frac{pC_{k_{i}}^2}{C_{k_{i}}^2}=p=\frac{\bar{k}}{n-1}=\frac{\bar{k}}{n}$$
	  其中$p=\frac{\bar{k}}{n-1}$就是看的是一个节点的与其他节点可能存在边的概率。（平均度数/所有邻居）
	- path length 、connectivity
	- [[expansion]]
- 特点：
	- 真实图的节点度分布很偏，但是$G_{np}$类似于高斯分布
	- 真实图的聚类系数远大于$G_{np}$