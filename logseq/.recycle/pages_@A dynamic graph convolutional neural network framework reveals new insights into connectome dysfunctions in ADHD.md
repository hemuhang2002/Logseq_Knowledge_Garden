tags:: [[code-availiable]], [[已读 未学习]]
date:: 02/2022
issn:: 10538119
doi:: 10.1016/j.neuroimage.2021.118774
title:: @A dynamic graph convolutional neural network framework reveals new insights into connectome dysfunctions in ADHD
pages:: 118774
volume:: 246
item-type:: [[journalArticle]]
access-date:: 2024-03-04T04:26:43Z
call-number:: 1
original-title:: A dynamic graph convolutional neural network framework reveals new insights into connectome dysfunctions in ADHD
language:: en
url:: https://linkinghub.elsevier.com/retrieve/pii/S1053811921010466
publication-title:: NeuroImage
journal-abbreviation:: NeuroImage
authors:: [[Kanhao Zhao]], [[Boris Duka]], [[Hua Xie]], [[Desmond J. Oathes]], [[Vince Calhoun]], [[Yu Zhang]]
library-catalog:: 5.7
links:: [Local library](zotero://select/library/items/HNUEKXYA), [Web library](https://www.zotero.org/users/13743486/items/HNUEKXYA)

- [[Attachments]]
	- [已接受版本](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10569447/pdf/nihms-1773458.pdf) {{zotero-imported-file QMT4ZPSV, "Zhao 等 - 2022 - A dynamic graph convolutional neural network frame.pdf"}}
- [[Notes]]
	- 如何通过皮尔逊系数构建脑图？
	  
	  两跳编码方式
	  
	  “Abstract” (Zhao 等, 2022, p. 1) 🔤抽象的🔤新的dGCN方法，广泛的对比实验，可视化
	  结论：很厉害，同时可以泛化到别的disorder上去
	  
	  “Introduction” (Zhao 等, 2022, p. 2) 🔤介绍🔤ADHD背景知识、ADHD计算检测的发展、GCN的发展概述、GCN在mentor disorder中的应用，目前GCN的缺陷
	  
	  “Data acquisition and preprocessing” (Zhao 等, 2022, pp. -) 🔤数据采集​​和预处理🔤ADHD-200数据集，只使用进行了个人性格测试的样本进行使用；虽然预处理消除了部分脑脊液，但是运动的影响还没有剪出，所以我们使用了isolation forest来进行进一步预处理
	  
	  “Proposed approach” (Zhao 等, 2022, p. 5) 🔤提议的方法🔤1.1.介绍了构建图可以通过population 和 subject 图，population不能利用脑子的拓扑结构，subject可以利用脑子的结构，一般来说，节点特征可以很多，如体素灰质体积，表面区域等。1.2.介绍了皮尔逊系数的好处。本文通过计算 ROI 时间序列的 Pearson 相关矩阵作为边缘特征，形成邻接矩阵，并计算一个 ROI 与所有其他 ROI 之间的时间序列偏相关系数作为节点特征2.1两跳编码方式
	  
	  “Results” (Zhao 等, 2022, pp. -) 🔤结果🔤①多种对比方式，与常规的机器学习对比 SVM LR等，以及MLP,GCN,GAT等进行广泛的对比。②进行了10倍交叉验证，以及strattified采样（不太懂）③进行了leave-study-site-out实验，本来用了四个数据集进行training，现在只使用三个作为训练集，然后剩下的一个作为测试集④消融实验，消融实验的方式和技巧。⑤通过可视化权重来分析重要的脑网络⑥用重要脑区进行了预测实验和相关性实验
	  
	  “Discussion” (Zhao 等, 2022, pp. -) 🔤讨论🔤①空间GCN减少了运算量--就是说没用频域卷积②subject-level的卷积更有利于预测，只需要一个人的数据和训练好的模型就可以进行预测，而不是需要整个数据集一起才能进行预测，同时收敛性能和稳定性更好③2-hop，Normconv，EdgeConv，ConvReadout各有优势 ④我们的实验结果符合最新的脑生物研究⑤可以视为DMN网络⑥未来可以使用时空序列⑦可以尝试不同的功能脑区划分实验⑧使用先验的神经生物学知识来指导训练⑨使用更高级的从PCD表型中得到的特征
	  
	  “Conclusions” (Zhao 等, 2022, pp. -) 1. 2- hop 2，dGCN，可以使用top-K来动态建模 3.使用了特殊的readout层，减少了信息丢失