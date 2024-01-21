file:: [LeeDL_Tutorial_v.1.1.1_1700402602978_0.pdf](../assets/LeeDL_Tutorial_v.1.1.1_1700402602978_0.pdf)
file-path:: ../assets/LeeDL_Tutorial_v.1.1.1_1700402602978_0.pdf

- 但把图像上下颠倒，可能不是一个训练集或真实世界里面会出现的图像。如果给机器根据奇怪的图像学习，它可能就会学到奇怪的东西。所以数据增强，要根据对数据的特性以及要处理的问题的理解，来选择合适的数据增强的方式
  ls-type:: annotation
  hl-page:: 33
  hl-color:: yellow
  id:: 655b4173-aca9-4b58-bd29-b44d5514e543
- 根据验证集上面的分数去挑选结果，再把这个结果上传到 Kaggle 上面得到的公开分数
  ls-type:: annotation
  hl-page:: 35
  hl-color:: yellow
  id:: 655b43cd-6716-4c8a-9b3a-01730ca92a5f
- 如下三种情况
  ls-type:: annotation
  hl-page:: 40
  hl-color:: yellow
  id:: 655b4e4d-cbee-4b6d-8366-f2f1bddb370a
  hl-stamp:: 1700482638960
- 如果 n 阶对称矩阵 A 对于任意非零的 n 维向量 x 都有 xTAx > 0，则称矩阵 A 为正定矩阵. 如果 n 阶对称矩阵 A 对于任意非零的 n 维向量 x 都有 xTAx < 0，则称矩阵 A 为负定矩阵.
  ls-type:: annotation
  hl-page:: 41
  hl-color:: red
  id:: 655b4e74-cc04-4c1c-bba3-71fb7fe66005
- 数的数量代表了误差表面的维度. 既然维度这么高，会不会其实就有非常多的路可以走呢？既然有非常多的路可以走，会不会其实局部极小值就很少呢?
  ls-type:: annotation
  hl-page:: 43
  hl-color:: yellow
  id:: 655b4f74-88b5-4ce6-b489-8cc55ed10505
- 那么在每一个回合里面，参数会更新 20 次。用一笔数据算出来的损失相对带有更多噪声
  ls-type:: annotation
  hl-page:: 45
  hl-color:: yellow
  id:: 655b50dd-35cf-40cf-b114-80d8c1e9548a
- 大的批量大小反而是较有效率的，一个回合大的批量花的时间反而是比较少的。
  ls-type:: annotation
  hl-page:: 47
  hl-color:: yellow
  id:: 655b513a-0c3d-46a8-9348-66ad64eb5ab2
- 但实际上有噪声的的梯度反而可以帮助训练
  ls-type:: annotation
  hl-page:: 47
  hl-color:: yellow
  id:: 655b5141-e8af-4d90-9656-a7b05b5add06
- 量跟小的批量训练得一样好。实验结果发现小的批量在测试的时候会是比较好
  ls-type:: annotation
  hl-page:: 48
  hl-color:: yellow
  id:: 655b51bf-d75f-4cc1-9c40-28fbfb9070ac
- 小的批量比较长，大的批量反而是比较快的，所以从一个回合需要的时间来看，大的批量是较有优势的。 而小的批量更新的方向比较有噪声的，大的批量更新的方向比较稳定。但是有噪声的更新方向反而在优化的时候有优势，而且在测试的时候也会有优势。所以大的批量跟小的批量各有优缺点，批量大小是需要去调整的超参数
  ls-type:: annotation
  hl-page:: 48
  hl-color:: yellow
  id:: 655b520b-9408-4dd6-8d12-6777f8c540f0
- 虽然图 3.36b 中圆圈的梯度很小，但 Adam 会自动调大学习率，还有机会走到右下角，不过训练的过程比较困难。总之，改变损失函数可以改变优化的难度。
  ls-type:: annotation
  hl-page:: 62
  hl-color:: yellow
  id:: 655b6019-60e1-4325-a882-5d9836dc603d
- 如果是 x2 的话，假设 x2 的值都很大，当 w2 有一个小小的变化的时候，虽然 w2 这个变化可能很小，但是因为它乘上了 x2，x2 的值很大，那 y 的变化就很大，e 的变化就很大，L 的变化就会很大，就会导致我们在 w 这个方向上，做变化的时候，我们把 w 改变一点点，误差表面就会有很大的变化。
  ls-type:: annotation
  hl-page:: 64
  hl-color:: yellow
  id:: 655b6160-e5b0-4c33-8599-ad37d593bc34
- 一般而言，特征归一化，要放在激活函数之前，之后都是可以的，在实现上，没有太大的差别
  ls-type:: annotation
  hl-page:: 65
  hl-color:: yellow
  id:: 655b61aa-4faf-4e18-921d-8bb11058ff30
- 批量大小如果比较大，也许这个批量大小里面的数据就足以表示整个数据集的分布。
  ls-type:: annotation
  hl-page:: 67
  hl-color:: yellow
  id:: 655b61f8-af07-48ce-a8ea-07cce8f484aa
- 果运算资源足够支撑不做汇聚，很多网络的架构的设计往往就不做汇聚，而是使用全卷积，卷积从头到尾，看看做不做得起来，看看能不能做得更
  ls-type:: annotation
  hl-page:: 85
  hl-color:: yellow
  id:: 655c059b-48c5-4111-a63d-66ceb714a23f
- ，汇聚是可有可无的
  ls-type:: annotation
  hl-page:: 85
  hl-color:: yellow
  id:: 655c05a6-d1cb-4c44-af92-79465141a6dd
- 图像上的第1 个观察是，只需要看小范围就可以知道很多重要的模式。下围棋也是一样的，图 4.32中的模式不用看整个棋盘的盘势，就知道发生了什么事（白子被黑子围住了）。接下来黑子如果放在被围住的白子下面，就可以把白子提走。白子如果放在白子下面，被围住的白子才不会被提走。其实 AlphaGo 的第 1 层的滤波器大小就是 5 × 5，所以显然设计这个网络的人觉得棋盘上很多重要的模式，也许看 5 × 5 的范围就可以知道。此外，图像上的第 2 个观察是同样的模式可能会出现在不同的位置，
  ls-type:: annotation
  hl-page:: 87
  hl-color:: yellow
  id:: 655c0631-6e79-41d1-ac1d-5cb0c79a6c26