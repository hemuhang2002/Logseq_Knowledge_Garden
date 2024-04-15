- 毕业设计idea
  collapsed:: true
	- 基本肯定是双流
		- 然后添加注意力机制
	- 重点是学习到振幅信息
		- 振幅相对是？ 可以先验设置重要性来放大振幅相关的参数（比如是手臂和手掌中心的点距离以及中心点距离的变化，则可以在这个节点卷积上先验设置较高的值来放大幅度）
	- 衡量的是震颤幅度
		- 震颤幅度分为两个聚类，一个是手部的信息，一个是肩膀的信息，还有一个是肩膀信息和手部信息的汇聚
		- 直接设定一个固定点，比如左上角，特征设置为000，进行卷积计算？
	- 时间维度的汇聚
		- 手部振幅是的时间跨度大还是小？,手部特征可能需要聚合为一个点最后再去计算
			- 如果不同振幅对应不同的跨度，应该设置不同的时间感受野来提取做TCN提取（1*1 3*3 5*5 maxpooling 1*1conv)
- 毕设文件更新
	- st1_data_new:将原始的data文件进行右手翻转后的文件
	- st_2_human_crop:将st1_data_new中的文件进行人体裁剪，但是有部分没有成功写入，没有成功写入的名单保存在st2_cropped中
	- st3_hand_crop:将st_w_human_crop进行手部裁剪，但是有部分没有成功写入。将st_w_human_crop进行手部裁剪。对没有成功写入的文件，从st1_data_new中重新裁剪，裁剪出只含有运动手的视频。
	- st3_hand_crop_2:st3_hand_crop所有的视频进行观看，对缺失手部的视频进行重新裁剪 已完成
- 毕设已有相关论文总结
	- [[2019-2022相关论文总结]]
	- [[论文代码备忘录]]
	- [[函数文档]]
- 10.30 -- 11.5
	- DONE 2s - AGCN 论文
	- DONE 2s-AGCN 代码
	- DONE PB-GCN 论文
	- DONE PB-GCN
	  :LOGBOOK:
	  CLOCK: [2023-11-01 Wed 19:56:45]--[2023-11-01 Wed 19:56:46] =>  00:00:01
	  :END:
	- DONE MS-G3D代码
	  id:: 6550ef35-b602-4f3a-9c6b-88517e52d052
	- DONE [[毕业设计资料调研]]
	  :LOGBOOK:
	  CLOCK: [2023-11-01 Wed 19:56:56]--[2023-11-01 Wed 19:56:56] =>  00:00:00
	  :END:
	- DONE CTR-GCN代码
		- 爱因斯坦求和公式：列出式子，看隐藏元和自由元
	- DONE 看骨骼识别论文以及添加注意力机制的代码
	  :LOGBOOK:
	  CLOCK: [2023-11-06 Mon 14:03:48]--[2023-11-06 Mon 14:03:49] =>  00:00:01
	  CLOCK: [2023-11-06 Mon 14:03:50]--[2023-11-20 Mon 10:56:17] =>  332:52:27
	  :END:
	- DONE 2019年相关论文阅读结束＋总结
- 11.6 -- 11.12
	- DONE 看骨骼识别论文以及添加注意力机制的代码
	  :LOGBOOK:
	  CLOCK: [2023-11-09 Thu 10:19:42]--[2023-11-20 Mon 10:56:19] =>  264:36:37
	  :END:
	- DONE 2020年论文阅读
	- DONE [[所有论文复习思考总结]]
	- DONE 2021年论文阅读
	- DONE 2022年论文阅读
	- DONE [[开题报告]]
	  :LOGBOOK:
	  CLOCK: [2023-11-13 Mon 00:04:33]--[2023-11-13 Mon 16:56:12] =>  16:51:39
	  :END:
- 11.13-11.19
	- DONE 看[ieeexplore.ieee.org](https://ieeexplore.ieee.org/abstract/document/10193771) 或许有用
	- DONE 开题报告
	- DONE 注意力机制论文
	- DONE 数据处理问学姐，去徐汇，以及记录表
	- DONE ST-GCN代码精学
	- DONE 阅读相关文献
- 11.20-11.26
	- DONE 学习GCN-人体姿态识别的其他论文
	- DONE 看DMGNN代码
	  DEADLINE: <2023-11-22 Wed>
	  :LOGBOOK:
	  CLOCK: [2023-11-26 Sun 12:45:10]--[2023-11-26 Sun 14:21:42] =>  01:36:32
	  :END:
	- DONE 看Constructing Strong and Fast Baseline for skeleton-based action recognition 代码
	- DONE 测试不同的骨架算法
		- DONE OPENpose
		- DONE mmpose
		- DONE blazehand
- 11.27-12.3
	- DONE 学习图神经论文和算法
	- TODO
		- 视频反转还没全部完成
		- 尝试最好的crop裁剪
- 12.4 - 12.10
	- DONE 对st3的视频进行分析调研（找出有问题的，然后和cropped的一起处理，裁剪出只含运动手部的视频），其次将这些人工处理的视频替换到文件夹，然后用folder2one进行提取到一个文件夹（data_processed and landmark）->研究如何处理landmark
		- 首先学习输入数据的格式，然后再去处理数据
	- DONE 首先观看所有的order视频，只需要两只手的视频，三只手不行，把第三只手的提取出来
	- DONE 然后进行到数据处理的部分
- 12.11-12.17
	- DONE 函数文档
	- 预处理 -
		- 匀速差值 、 不需要兼顾、先试一试
		- 归一化方式，按照单个视频，单个方向归一化 min_max，z-socre均值方差
		- 固定长度填充方式
			- 镜像
			- 填充成0
			- 循环
		- 只输入医生还是患者的手
		- 输入手的部分
		- 输入手的信息
		- 最后特征融合的方式
		- 邻接矩阵就是最基本
			- 医生患者手的融合或者区分
		- CNN、伪图像，光流
			- 单独
			- 概率融合
	- DONE 边缘值的处理，作用于所有的视频
	- DONE 检查插值情况，做视频筛选
	- [numpy ndarray 之内功心法 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/39287693) #python
	- DONE 初步筛选数据集的指标
		- 可视化标签到对应的qt文件，要求直接首先制作all_list和label_list
		- 其次筛选的时候，对于0的数据，只要识别正常，就可以放进去，对于2类数据，只要异常就放进去，这里面会有存在不异常的，比如只有指尖在动，这种是不需要的、
	- DONE 对于手指数据集，制作了之后进行测试即可，说明了不可用性即可。
	-
	-
	- [使用有监督对比学习对CIFAR10进行分类，达到0.9546 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/665802511) #学习网址
	- [NIPS20 - 将对比学习用于监督学习任务《Supervised Contrastive Learning》_supervised contrastive learning 代码mask-CSDN博客](https://blog.csdn.net/qq_36560894/article/details/120799699) #学习网址
	-
-
-
-
-
-