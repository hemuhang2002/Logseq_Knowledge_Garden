> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [juejin.cn](https://juejin.cn/post/7021727244124962846)

> 今天教大家如何给开源项目提交 pr，成为一名开源贡献者。pr 是 Pull Request 的缩写，即给开源项目提交代码贡献。

今天教大家如何给开源项目提交 pr，成为一名开源贡献者。pr 是`Pull Request`的缩写，当你在 github 上发现一个不错的开源项目，你可以将其 fork 到自己的仓库，然后再改动一写代码，再提交上去，如果项目管理员觉得你的提交还不错的话，就会将你的代码合并，然后你就成为了这个代码的贡献者了。

基础的 git 操作咱今天就不说了，直接步入正题，傻瓜式流程，直接按步操作即可。

一、fork 代码
---------

先登录自己的 github 账户，找到自己要提 pr 的项目。这里我们以 element-plus 为例。

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c48d346ee9ad414f8fbc807696844b4d~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

进入主页后，可以看到右上角有 Fork 按钮，点击之后，等待几秒就会 fork 成功。

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a819682f02424d2fa4a654ea6c14a8e9~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

我们可以看到，此时该项目就跑到我们自己的仓库目录下了，接下来我们就可以将该项目克隆到本地，进行后续操作。

二、clone 代码
----------

1.  点击页面上右边的 Code 绿色按钮，再点击复制按钮，复制该链接，将其克隆到本地。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/702d8e01a2684210803f612c9ac47fbc~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

2.  在本地的某个目录下，打开命令行，输入如下代码

```
git clone https://github.com/smalller/element-plus.git


```

注意！注意！注意！上面的地址是我仓库的地址，千万不要直接复制，要去复制自己仓库下的地址。

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3d185c5460954cbfae685eb11ac8f2e6~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

这样就代表项目已经成功克隆到本地。

3.  接下来，我们可以在克隆好的项目的根目录下，用以下命令，查看自己是否与远程仓库建立了连接

```
git remote -v


```

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e7e9f218aadd4805b39f3f9025a550a3~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

可以看到，已经建立连接，接下来还需要与上游建立连接，这里上游指的是一开始 fork 的那个项目源，即 element-plus。

4.  与上游建立连接，这段代码可直接复制。

```
git remote add upstream https:


```

此时，我们再输入`git remote -v`，就可以看到本地已经和远程仓库以及上游建立了连接。

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/288357033dba40ba83b08ff6fca3d40a~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

三、同步最新代码
--------

为什么要这么做？因为当你在开发的时候，可能其他人也在开发，很有可能你 fork 的代码已经不是最新的了，这时你就需要不断更新你的代码，至少保证在 push 前要更新一次，这样才能确保不会发生代码冲突。

命令行输入以下代码

```
 git fetch upstream dev  


```

为什么这里是 dev 分支，因为该项目默认 clone 的就是 dev 分支下的代码。当然这里你也可以自己在本地创建一个分支，然后拉取，最后再去 dev 分支里合并自己创建的分支代码。

四、编写代码
------

接下来，就是自由发挥环节了，这里不做过多说明了。

五、提交代码
------

代码编写完成后，就可以提交代码了。当然，不同开源项目可能会有自己的提交规范，我们可以看下 element-plus 的提交规范。

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4adeebf42e9a45b799f6efc5578858c6~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

我们只需按照其中`Pull Request`规范来做即可。

1.  commit 代码

```
git add .
git commit -m fix(components): [el-scrollbar] fix xxx bug


```

2.  push 代码

```
git push origin dev


```

push 代码成功后，我们就将进行最后一步，提交 pr。

六、提交 pr
-------

我们回到自己仓库的项目主页，可以看到刚才提交的记录，则表示之前的操作都已成功。接下来，点击箭头所指的`Pull Requests`选项。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7e929da409f14b719ee820d0c536c58d~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

点击箭头所指的`New pull request`按钮

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bb8668ed89ef45a98687f4500999a791~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

接下来，点击`Creat pull request`即可提交成功。

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f510e96bd37548578db503a4e3793b25~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

最后，只需耐心等待管理员的审核即可。开源项目的所有 pr 记录可以在这里查看，包括你刚才提交的。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1e650919ab0145fba32eebb3110351c5~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

如果你的提交被审核通过，则会像下面这个这样，显示`All checks have passed`

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/eeeee92de588402298fd1622e6ac96f8~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

这样，整个提交 pr 流程就已完成，是不是觉得很简单，可以自己去试试哦，毕竟能成为一个开源项目的贡献者还是挺不错的，也算是面试的加分项。