- 大致流程和 [[AGM]]差不多，区别在于$P\left(u,v\right)$的定义上
- $P\left(u,v\right)$定义
  首先$F_{uA}$是节点$u$在社区$A$中的强度，如果$u$是社区$A$的强成员，那么$F_{uA}$应该很大($F_{uA}$是一个正数)
  $$P\left(u,v\right)=1-\exp^{-F_{uA}F_{vA}}$$
  如果$u,v$都是A的强节点，那么$P\left(u,v\right)$约等于1
  如果$u,v$有一个节点不属于A，那么$P\left(u,v\right)$等于0
- 如果$u,v$属于多个社区，那么
  $$P\left(u,v\right)=1-\prod_{C\in\Gamma}\left(1-P\left(u,v\right)\right)$$
  可以化简得到
  $$
  P(u,v)=1-\prod_{C\in T}\left(1-P_{c}(u,v)\right)\\=1-\prod_{C\in T}\left(1-\left(1-\exp(-F_{uC}\cdot F_{vC})\right)\right)\\=1-\prod_{C\in T}\exp(-F_{uC}\cdot F_{vC})\\=1-\exp\left(-\sum_{C\in T}F_{uC}\cdot F_{vC}\right)\\=1-\exp\mathbf{(-F_{u}^{T}F_{v})}\quad(\text{内积})
  $$
- 其他的就和 [[AGM]]一样了