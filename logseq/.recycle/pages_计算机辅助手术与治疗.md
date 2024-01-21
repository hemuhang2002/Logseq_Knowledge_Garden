- {{cards [[计算机辅助手术与治疗]]}}
- 问题
	- ((658983d7-2e9d-413b-869c-8bc4cb080dbf))
	- ((65898d23-0aee-41e6-b309-7301bbf20f80))
	- ((65898d41-cf65-4c6c-adb5-0390b8146bc1))
- 练习
	- ((658a784e-103a-40e7-aada-a48083fa5070))
	- ((658cc37c-9a86-4e97-9269-e5a22357df48))
	- ((658cc509-1d85-4fde-9002-3ae1c3498853))
- ![IGST_SJTU-1.pdf](../assets/IGST_SJTU-1_1703493117581_0.pdf)
	- ((65893e93-ac67-4bc1-9be8-47b9fc881909))
		- 像素
		- 灰度值
		- 坐标
	- 图像分类
		- 二值、灰度、彩色、伪彩
		- 传感器类型
		- 维度
	-
- ![IGST_SJTU-2.pdf](../assets/IGST_SJTU-2_1703493377516_0.pdf)
	- 第二章 灰度图直方图的缺点？二值化阈值处理的五个方法？ #card
	  card-last-interval:: 8.81
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-01-05T03:50:32.399Z
	  card-last-reviewed:: 2023-12-27T08:50:32.399Z
	  card-last-score:: 5
		- ((65893f4e-4f34-44b0-b99f-1c1514c665be))
			- 灰度直方图
				- 空间信息丢失
			- Thresholding 
			  > can employ either a **fixed** or an **adaptive** threshold value
			  Thresholding contains 灰度直方图
				- **Isodata Algorithm**
				- **OTSU Algorithm**
				- **Entropy Method**
				- **Triangle Algorithm**
				- **Adaptive Thresholding**
- ![IGST_SJTU-3.pdf](../assets/IGST_SJTU-3_1703501478507_0.pdf) Basic Image Operations
	- 第三章 pixel operation 点操作、代数操作、几何操作 #card
		- point operation
			- Linear point operations
				- aD+b,不同的a和b的意义？
		- Algebraic operation
			- ![image.png](../assets/image_1703502055360_0.png){:height 236, :width 289}
		- Geometric operation
			- 原图像的放缩旋转
			  ![image.png](../assets/image_1703502173727_0.png){:height 271, :width 489}
	- 第三章 interpolation #card
		- Nearest Neighbor Interpolation
		- square interpolation
		- Higher Order Interpolation
	- 第三章 Neighbourhood Operators #card
		- 四领域or八领域
		- 4(8)-connected
			- two pixels within $$N_4(P) or N_8(P)$$
	- 第三章  Connected Component Labeling Algorithm #card
		- 算法的实质是扫描一幅图像的每个像素，对于像素值相同的分为相同的组(group),最终得到图像中所有的像素连通组件
- region properties有哪些？ #card
	- Perimeter and Area
		- A(P) = nI + nB/2-1
	- Center, Radius and Diameter
		- 离心率、中心，半径，直径
	- Centroid Moments and Orientation
		- 质心、矩、方向
	- Extreme Points and Curvature
	- Intensity Properties
- ![IGST_SJTU-4.pdf](../assets/IGST_SJTU-4_1703723119181_0.pdf) 卷积运算和图像滤波
	- 卷积的步骤 #card
		- ![image.png](../assets/image_1703504384454_0.png){:height 128, :width 330}
	- 边缘的类型 #card
		- ![image.png](../assets/image_1703504672519_0.png){:height 278, :width 301}
	- 边缘检测和图像滤波算子 #card
		- 边缘检测
			- prewitt operator ((65896bf8-0718-4244-b25f-6ff220c832ac))
			- Sobel operator
		- 图像绿波
			- 中值滤波
			- 高斯滤波
- ![IGST_SJTU-5.pdf](../assets/IGST_SJTU-5_1703504968316_0.pdf) VTK and ITK
- ![IGST_SJTU-6.pdf](../assets/IGST_SJTU-6_1703505036057_0.pdf) 数学形态学及其二值运算
	- 讲解了腐蚀\$、膨胀 $$\oplus$$、开运算和闭运算
	- 开运算、闭运算的先后顺序是？ #card
		- 开运算：腐蚀膨胀，作用是消除毛刺
		- 闭运算：膨胀腐蚀，填补孔洞
	- 形态学操作讲究一个SE和origin，一定有一个结构和**中心**
		- ![image.png](../assets/image_1703505701502_0.png){:height 253, :width 383}
- ![IGST_SJTU-7.pdf](../assets/IGST_SJTU-7_1703505852516_0.pdf) 二值形态学
	- 击中与击不中变换的原理，作用？ #card
		- 原理： {{embed ((656c1707-4d98-4bca-8c28-2283713f5c32)) }}
		- 作用：用于找到特定的模式块
		-
	- Pattern Spectrum
		- 模式谱，又称为颗粒度大小密度，是图像处理和分析中用来衡量图像中物体尺寸分布的概念。它在图像分析领域特别有用。
		- 工作原理？ #card
			- 不断的用开运算去差分，依次增大开运算核的大小，知道二值图像消失或灰度图像平滑
	- Recursive Erosion 递归腐蚀 #card
	  card-last-interval:: 8.81
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-01-04T02:49:33.340Z
	  card-last-reviewed:: 2023-12-26T07:49:33.341Z
	  card-last-score:: 5
		- 满足一定条件时停止
	- Distance Transform的步骤 #card
		- 举例
			- ((65898406-3482-4e75-a852-ea5170b2facb))
		- 执行多次递归侵蚀操作，使用适当的结构元素（SE），直到图像的所有前景区域都被侵蚀掉，涉及反复将侵蚀操作应用于图像。每次应用侵蚀操作，前景区域都会收缩，直到完全被侵蚀。
		  
		  在侵蚀过程之后，您可以为每个像素标记执行侵蚀操作的次数，直到它消失。这个过程可以总结如下步骤：
		- **递归侵蚀**：选择适当的结构元素（SE），并将侵蚀操作应用于图像。重复这个过程多次，直到所有前景区域都被侵蚀掉。
		- **像素标记**：当前景中的每个像素被侵蚀掉时，用执行侵蚀操作的次数标记它。这涉及跟踪每个像素的侵蚀迭代次数。
		- **距离变换结果**：一旦所有前景区域都被侵蚀掉，并且像素已被标记，您可以从标记图像中获取距离变换结果。距离变换结果将显示每个点到最近边界的距离，考虑了已进行的侵蚀过程和每个像素消失前执行的侵蚀次数
- 骨架提取与重建
	- 骨架提取算法 #card
		- 腐蚀结果减去腐蚀和开运算的结果
			- 不断循环直至无法为空
		- 重建算法
			- ![image.png](../assets/image_1703509507454_0.png){:height 189, :width 390}
- ![IGST_SJTU-8.pdf](../assets/IGST_SJTU-8_1703509528830_0.pdf) 复习的时候看看
- ![IGST_SJTU-9.pdf](../assets/IGST_SJTU-9_1703513452124_0.pdf)
	- 灰度膨胀与腐蚀的操作，膨胀是向哪边移动？腐蚀是向哪边移动？ #card
		- 膨胀是向右、腐蚀是向左
		- 开闭运算同理
		- 练习 ((65899135-6cce-4606-9741-93d91a704baa))
- ![IGST_SJTU-10.pdf](../assets/IGST_SJTU-10_1703514437624_0.pdf)
	- 形态学的边缘提取 #card
		- 三种方法
			- 膨胀减腐蚀
			- 膨胀减原图
			- 原图减腐蚀
	- 形态学的梯度，也可以分为内部和外部 #card
		- ![image.png](../assets/image_1703514806587_0.png)
	- 形态学平滑 #card
		- 灰度开运算可以使灰度图像从亮度表面以上变得平滑，而灰度闭运算则可以使图像从表面以下变得平滑（记住图像）
		   ![image.png](../assets/image_1703559156306_0.png){:height 146, :width 291}
		- 先开再闭
	- 顶帽变换与底帽变换的原因（从图像去记忆）？ #card
		- 首先顶帽变换是将曲线上的上面的帽子拿出来（开－原）
			- 意思是可以将原图中的亮物体拿出来
		- 底帽变换是将曲线的下凹处的帽子拿出来（闭－原）
			- 意思是将暗物体拿出来（将暗物体单独拿出来并且变亮）
	- DTT的原理和好处 #card
		- 能够把具有高梯度的信号拿出来（低梯度的每次做差的信号，都不大，见图 ((658a436b-2bb2-4455-9f65-8185370a6dee))）
		- 原理就是给定一个固定的阈值，用多个TT的差值进行作为输入来进行筛选，可以把梯度不高的信号删去
	- Ultimate Erosion 和 Geodesic Influence的应用？ #card
		- UE用于得来种子，GI用于重建分割，可以用于分割器官
		- ![image.png](../assets/image_1703560472947_0.png){:height 494, :width 405}
- ![IGST_SJTU-11.pdf](../assets/IGST_SJTU-11_1703560494663_0.pdf) 灰度的数学形态学(3)
	- 形态学重建和灰度重建 #card
	  card-last-interval:: 8.81
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-01-05T03:50:35.672Z
	  card-last-reviewed:: 2023-12-27T08:50:35.672Z
	  card-last-score:: 5
		- 给一个M,和限制区域V，让M不断膨胀直到填满V
		- 步骤：
			- 通过open or close操作得到seed，然后使用限制膨胀得到重建结果
	- Geodesic Distance #card
		- 考虑了范围内的
		  ![image.png](../assets/image_1703572727062_0.png){:height 226, :width 276}
	- 分水岭算法 #card
		- 用于图像分割
- ![IGST_SJTU-12.pdf](../assets/IGST_SJTU-12_1703573605307_0.pdf) 彩色图像和三维图像处理
	- HIS系统 #card
		- H是色度
		- I是intensity
		- S是饱和度
		- ![image.png](../assets/image_1703578296766_0.png)
	- out of balance #card
	  card-last-interval:: 8.81
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-01-05T03:47:03.640Z
	  card-last-reviewed:: 2023-12-27T08:47:03.640Z
	  card-last-score:: 5
		- 对两个颜色进行调整去match第三个颜色
		- 现实生活中是用调节Hue和saturation
			- Hue的调节是冷暖调节
			- Saturation是饱和度
	- 彩色图像修复 #card
	  card-last-interval:: 4.14
	  card-repeats:: 1
	  card-ease-factor:: 2.36
	  card-next-schedule:: 2023-12-31T11:47:19.783Z
	  card-last-reviewed:: 2023-12-27T08:47:19.783Z
	  card-last-score:: 3
		- 线性点变换确保RGB色彩平衡
		- 转换到HIS
		- 去噪
		- 锐化
		- 线性点变换到最佳值
		- 变换到RGB
	- pseudocolor color image #card
	  card-last-interval:: 8.81
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-01-05T03:46:32.473Z
	  card-last-reviewed:: 2023-12-27T08:46:32.483Z
	  card-last-score:: 5
		- 伪彩图，其实就是一个灰度图
		- 通过一个lookup table进行对应
		  ![image.png](../assets/image_1703579004578_0.png){:height 174, :width 237}
	- 彩色图像分割 #card
		- 不同的物体可能落在不同的色彩区域
			- 白色不会（白噪声）
		- 在hue-saturation是更好分割的维度
	- 通过手术三维切片获取三维信息的缺点 #card
		- 对齐信息的丧失
		- 导致拉伸、扭曲
	- Tomography 的坏处 #card
		- 高剂量的辐射
		- 矢状面（sagittal plane）、冠状面（coronal plane），以及横断面（transverse plane）
	- Stereometry 的应用是 {{cloze  用于获取立体图像}}
	- shaded surface display
- ![IGST_SJTU-13.pdf](../assets/IGST_SJTU-13_1703574073069_0.pdf) 计算机辅助手术的历史和关键技术
	- IGST的现代化趋势，为什么要IGST？ #card
		- 减少入侵伤害
			- 减少手术时间、恢复时间、费用
		- 定位、可视化病灶、提高准确与成功率
	- IGST的任务 #card
		- 聚合术前影像信息
		- 配准病灶体积与影像信息
		- 定位手术器械
		- 根据术前数据可见医学结构显示工具位置
		- 考虑术前数据与术中的实际差异
	- IGST存在的困难 #card
		- 价格贵 复杂程度高
		- 器官的形变造成的困难
		- 真实感与可应用性的困难
	- steretxy 立体定位术 #card
		- leksell frame -- 极坐标
		- horsley and clark frame-- 直角坐标
	- tracking device OTS和EMTS的优势 #card
		- 机械定位 -> 光学定位 -> 电磁定位
		- OTS
		  利用光学定位空间中的点
		  主要使用在刚性器械，可以直接通过换算得到器械尖端
		  > 有主动和被动的分别 主动是主动发出光被摄像头识别，被动是反射自然光被摄像头识别到，进而计算出圆心坐标，进而计算出尖端坐标（都是**红外光**）
			- 缺点
				- 无法穿透物体和人体
				- 收到环境光影响
			- 优点
				- 更稳定，精度更好
				- 不需要校准
				- 不受电磁干扰
		- EMTS
		  利用电磁定位空间中的点
		  > 有直流的也有交流的，或者永磁体
			- 缺点
				- 容易被干扰
				- 需要校准
			- 优点
				- 不被遮挡影响
				- 可以跟踪复杂的动作
	- IGST应用 #card
	  card-last-interval:: 8.81
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-01-05T03:46:57.807Z
	  card-last-reviewed:: 2023-12-27T08:46:57.807Z
	  card-last-score:: 5
		- 癫痫病灶切除术
		- 永久性前列腺放射性种植术
- ![IGST_SJTU-14.pdf](../assets/IGST_SJTU-14_1703574088225_0.pdf) 手术导航系统及技术展望
	- 手术导航系统的特征 #card
		- 特征：交叉与渗透
		- 信息技术向医学领域渗透的数字医学
	- 手术导航系统的现状问题 #card
		- 精度
		- 导航
		- 信息量不够
	- 手术导航系统的关键技术 #card
	  card-last-interval:: 8.81
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-01-05T03:46:50.883Z
	  card-last-reviewed:: 2023-12-27T08:46:50.884Z
	  card-last-score:: 5
		- 医学图像的三维建模
		- 医学图像的可视化
		- 图像分割
		- 图像配准
		- 图像融合
		- 术中超声、监控
		- 脑组织变形
		- 骨科导航技术
- ![IGST_SJTU-15.pdf](../assets/IGST_SJTU-15_1703574098061_0.pdf) 可变性模型
	- ![image.png](../assets/image_1703585930992_0.png){:height 354, :width 365}
	- 可变性模型的步骤 #card
		- 显示图像
		- 用户初始化边界，定义vertex的速度和加速度为0
		- 计算每个vertex的速度
		- 计算每个vertex的加速度（三个力 {{cloze image force、internal force、damping force}} image force是和梯度有关的，internal force就是点之间的牵制力、弧度越大，internal force越大 ((658aaabe-c688-4c0c-b761-5841578f83f9)) damping force的作用是防止震荡、系数在$$-1与0$$之间，永远和速度是相反的）
		- 更新每一个点的速度和位置
		- DDC重采样 {{cloze 按照疏密程度进行resample，防止形成的不均匀}}
		- 重复直到速度和加速度小于某一个值
- ![IGST_SJTU-16.pdf](../assets/IGST_SJTU-16_1703574114213_0.pdf) 水平集算法
- ![Image-Processing_SJTU-17.pdf](../assets/Image-Processing_SJTU-17_1703588759841_0.pdf) 图像配准技术
	- Registration Framework #card
	  card-last-interval:: 8.81
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-01-05T03:46:45.605Z
	  card-last-reviewed:: 2023-12-27T08:46:45.605Z
	  card-last-score:: 5
		- ![image.png](../assets/image_1703589180838_0.png){:height 225, :width 350}
	- 评价标准 #card
		- information based
		- surfaced based
		- voxel intensity based