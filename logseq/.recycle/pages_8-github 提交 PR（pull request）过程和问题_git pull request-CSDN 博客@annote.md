:PROPERTIES:
:index: 8
:END:

- *原文* :: [github 提交 PR（pull request）过程和问题_git pull request-CSDN 博客](https://blog.csdn.net/weixin_41697143/article/details/81837369)
- *快照* :: [github 提交 PR（pull request）过程和问题_git pull request-CSDN 博客](http://localhost:7026/reading/8)
- *标签* ::  


### 摘要
#+BEGIN_QUOTE
文章浏览阅读2w次，点赞17次，收藏55次。前几天boss让做一个PR，一脸懵逼，查资料问同事，最后还被boss批，终于提交了PR。PR，全程pull Request ，下面写一下提交过程和我遇到的坑。项目背景：一个开源项目，我自己创建了一个分支并进行大量修改，需要PR到master上面，boss进行merge。1. 登录我的github，访问开源项目的github，在代码右上方有一个按钮，fork。点击fork后，自己的git..._git pull request
#+END_QUOTE

### 重点摘抄

 前几天 boss 让做一个 PR，一脸懵逼，查资料问同事，最后还被 boss 批，终于提交了 PR。

 PR，全程 pull Request ，下面写一下提交过程和我遇到的坑。

 项目背景：一个开源项目，我自己创建了一个分支并进行大量修改，需要 PR 到 master 上面，boss 进行 merge。

 接下来执行完毕，使用 git remote -v 查看当前状态，会出现这样的反馈信息

 3. 到项目的 github 中，复制项目的链接，继续查看当前状态

 现在你的本地代码已经与远程代码相连了。

 坑 1： 一定确定 origin 是你自己的地址，upstream 是远程的地址。

 这部分操作我没有全面处理过，自己之前直接删除有冲突的部分。以后需要多实践才行。


