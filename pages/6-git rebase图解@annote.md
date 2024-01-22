:PROPERTIES:
:index: 6
:END:

- *原文* :: [git rebase图解](https://zhuanlan.zhihu.com/p/198887332)
- *标签* ::  [[简悦笔记]]
- ### 重点摘抄
  id:: 65ae709f-d487-401d-8f9c-f27c9cb439fb
  
  ![图片](https://pic4.zhimg.com/v2-ed87f4ce6f82bbe96e19c20fcf32b61f_r.jpg){:height 456, :width 585}
  
  如果这个时候用 merge 把 master 分支合并到 develop 分支，就会是 No-fast-foward 的合并方式在 develop 分支上产生一个新的提交
  
  ![图片](https://pic3.zhimg.com/v2-051f6d187e0c3c36620c4ecb3dfca07a_r.jpg){:height 456, :width 585}
  
  后续我们去 review develop 分支的代码的时候，会发现以前 master 分支上的别人提交的 commit5 commit6 和 develop 分支上你提交的的 commit7 commit8 杂糅到了一块儿，很不方便 review 你写的代码但是，如果你想让 develop 分支历史看起来像没有经过任何合并一样，你可以用 git rebase 命令$ **git rebase master这个命令会把你的 develop 分支里的每个提交 (commit) 都取消掉，并且把它们临时保存为补丁(patch)，这些补丁放到了目录中，然后把 develop 分支更新为最新的 master 分支，最后把保存的这些补丁应用到 develop 分支上。.git/rebase**
  
  ![图片](https://pic3.zhimg.com/v2-5dccab4236caab322c50b3f7dab3171e_r.jpg){:height 456, :width 585}
  
  当 develop 分支更新之后，它会指向这些新创建的提交 (commit)，而那些老的提交会被丢弃。 如果运行垃圾收集命令 (pruning garbage collection)，这些被丢弃的提交就会删除如果 rebase 过程中有冲突，就先解决冲突，然后执行 继续变基git rebase --continue当我们使用 git log 来参看 commit 时，使用 git merge 和使用 git rebase 的 commit 的顺序会不相同。假设 commit5 提交于 9:00AM，commit7 提交于 10:00AM，commit6 提交于 11:00AM，commit8 提交于 12:00AM对于使用 git merge 来合并所看到的 commit 的顺序（从新到旧）是：commit9，commit8，commit6，commit7，commit5，commit4，commit3，commit2，commit1对于使用 git rebase 来合并所看到的 commit 的顺序（从新到旧）是：commit8Copy，commit7Copy，commit6，commit5，commit4，commit3，commit2，commit1 其中 commit8Copy 提交只是 commit8 提交的克隆，commit7Copy 提交只是 commit7 提交的克隆