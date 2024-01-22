:PROPERTIES:
:index: 2
:END:

- *原文* :: [理解 Android Studio 中的 Gradle](https://zhuanlan.zhihu.com/p/139685763)
- *标签* ::  [[简悦笔记]]


### 摘要
#+BEGIN_QUOTE
前言 在讲述下文之前，我想说一下为什么要写这篇文章。我在刚接触android的时候（当然现在也没接触多久），当我下好了AS，建立好我第一个项目的时候，我就全然没有去理会过Gradle这个构建工具，直接开始埋头敲代码…
#+END_QUOTE

### 重点摘抄

 我们每次创建一个项目的时候，都会有个 gradle 的文件夹，里面就包含着一个 wrapper 文件夹。那么为什么要有这个呢？gradle 是一门发展很快的语言，语言发展快，api 也就会经常更新，构建语言含有丰富的插件，变化很快的话，就难以兼容以前老的版本。而 wrapper 就用来解决解决兼容性问题。wrapper 里定义了 gradle 的版本。

 我现在的这个项目用的 gradle 版本是 5.4.1 的，那么这个版本是跟我现在的工程绑定的。若今后构建这个工程时，它都会用我所绑定的 gradle 版本（避免版本兼容性问题）所以 wrapper 的作用就是会来检查在你构建这个工程的机器上有没有 5.4.1 这个版本。如果有就开始构建，没有就去下载这个版本。再举个例子，假如你现在从网上下载了一个项目，而这个项目它所绑定的 gradle 版本是 5.1.1 的，而你的机器现在只有 5.4.1 版本的 gradle，那么当这个项目在你这台机器上构建的时候，wrapper 就会看你机器上有没有 5.1.1 版本的 gradle，发现没有的话就会去到所提供的 url 下载这个版本。

![图片](https://pic1.zhimg.com/v2-bbc85877e64e5f8be4c5539bc9db799c_r.jpg){:height 456, :width 585}

 上图我们可以这样来理解，将 repositories 理解成 “到哪里”，depenencies 理解成 “下哪些”。也就是说我们在 dependencies 里面所要下载依赖的 jar 包都要去到 repositories 中所给你的仓库里去找 --- 上图中的 google()、jcenter()，到 google 和 jcenter 这两个仓库里面去找。google 仓库和 jcenter 仓库中都是一些 jar 包和 aar 包。然后我们会看到在 dependencies 注释了一个 NOTE，大致意思就是不要将你的 application 的依赖放在这里，它们属于单独模块中的 build.gradle 文件。这是什么意思呢？继续往下面看你就会知道了。

![图片](https://pic4.zhimg.com/v2-5471eef1348f01f714bb9e14fe67186b_b.jpg){:height 456, :width 585}

 在 buildscript 下面还有一个与其相似的 allprojects，它里面也有一个 repositories，但却没了 dependencies。可能会有人会有疑问，为什么 repositories 还要再申明一次呢？其实这两个 repositories 所作用的地方是不相同的，buildscript 下面的是 gradle 自身构建所需要的一些依赖；而 allprojects 下方的仓库则是给项目中的其他 module 去使用的，像 app 模块或者其他你自己新建的一些模块它们所需的依赖就是到 allprojects 下面所给的仓库里去找。若你想知道你的 allprojects 中有哪几个 project，可以像下图一样点击右方的 Gradle 查看就好。

 第一个是我们上面已经讲了的，它是对应整个项目的，是作用于所有 module 的配置；而第二个就是对应其所在的模块层，上图中可以看到第二个的括号中写着【Module：app】，也就是说它是作用于 app 这个模块的，其描述了该模块的相关配置。如果你再新建一个模块，那么同样也会有一个作用于这个新模块的 build.gradle。

![图片](https://pic2.zhimg.com/v2-f147a7cea3bb0747aac5704718a429b5_r.jpg){:height 456, :width 585}


