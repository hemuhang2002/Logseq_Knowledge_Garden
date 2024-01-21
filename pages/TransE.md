- 首先 [[heterogeneous graph]]在建模上通常被表示为：
	- {{embed ((659bf5fb-8e6f-4023-9f03-eef0451d3af6))}}
- 将实体和关系映射到 \(\mathbb{R}^d\) 上，使得对于给定的三元组 \((h, r, t)\)，当三元组为真时有 \(\mathbf{h} + \mathbf{r} \approx \mathbf{t}\)，反之当三元组为假时有 \(\mathbf{h} + \mathbf{r} \neq \mathbf{t}\)。
  评分函数 \(f_r(h, t)\) 可以定义为 \(f_r(h, t) = -||\mathbf{h} + \mathbf{r} - \mathbf{t}||\)，其中 \(\mathbf{h}\)、\(\mathbf{r}\) 和 \(\mathbf{t}\) 分别表示头实体 \(h\)、关系 \(r\) 和尾实体 \(t\) 的嵌入向量。
  $$\ell  = \sum\limits_{\left((h,l,t),(h^`,l^`,t^`)\right)} \nabla[\gamma + d(||\mathbf{h} + \mathbf{r} - \mathbf{t}||)- d(||\mathbf{h}^` + \mathbf{l} - \mathbf{t}^`||)]$$
	- **损失函数理解**：要求再正确的情况下L最小，错误的情况在L最大
		- 此处，正确的情况在d小，要求L小，所以是正函数
		- 正确的情况在d大，要求L小，所以是负函数
- 几种方法的比较
  {{embed ((659bfc2d-4d0f-426f-a9fa-0e0aed483894))}}
-
-