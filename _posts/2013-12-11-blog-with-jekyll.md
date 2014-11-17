---
layout: post
title:  "用jekyll搭建个人博客"
categories: misc client
tags: misc client 
---

每天都要学习大量的新知识，但是学的多，忘得也多，之前都是用word来做一些记录，但是不得不说，实在是太烦了，因此萌生了一种写博客的想法，有很多写博客的网站如csdn等。但是总觉得用起来烦，看到别人的博客都是markdown格式来写的，所以翻阅了一些资料，将本博客的搭建过程详细的记录下来作为个人博客的开篇之作。

##有多少可用的博客程序

[知乎](http://www.zhihu.com/question/21981094)上有人问过一个问题，里面有人简单的介绍了一些个人博客的特点，我的需求是一个简单的静态博客，评论功能可有可无，可以分类检索，最后我选择了jekyll。虽然我对nodejs比ruby熟悉的多，但是还是没选基于nodejs的hexo，至于以后会不会迁移，用了以后才知道。

##安装jekyll

说明一下，这里的步骤并不是我实际在操作时候的步骤，而是我在网上找到并看别人的教程，但是有些因为太旧或者一些其它原因而失败然后重新整理出来的一份步骤。为的是方便看到本文的人搭建一个Github上的个人博客。关于在Github上搭建个人博客道不道德的问题，请参考[使用 GitHub Pages 来做博客是否道德?](http://www.zhihu.com/question/20717014)，同时希望看到这篇文章的朋友搭建自己个人博客的时候不要在其上讨论国家大事，不然Github这么好的网站如果被墙了真的是要郁闷至极了。

####安装ruby

ruby的安装还是比较简单的，在它的主页上有个链接到[installer](http://rubyinstaller.org/downloads/)的是专门为windows用户准备的安装包。安装如下图红圈内的两个包
![a](http://ww2.sinaimg.cn/large/005yyi5Jjw1emei7r95vtj30c90gj75w.jpg " ")

第一个包就是ruby的windows的安装包，一路next即可，第二个会在后面解释。第二个包的解压缩需要用7z，当然现在7z已经是一个很流行的压缩格式，大部分压缩软件支持7z的解压缩，比如360。

####安装jekyll

ruby自带一个包管理工具gem，有点类似node的npm，不一样的是它默认安装就是在全局，并且默认是静默安装。通过gem来安装使用的命令如下：-V才能看到安装过程，否则控制台毛的不打，出错了也不知道。

{% highlight bash %}
gem install jekyll -V
{% endhighlight %}

在使用该命令安装之前，需要注意由于国内的网络原因，导致gems上面的资源下的很慢或者下不了，淘宝的一些人搭建了一个国内的gem镜像，所以需要从镜像中下载。

{% highlight bash %}
gem sources --remove https://rubygems.org/
gem sources -a https://ruby.taobao.org/
gem sources -l
{% endhighlight %}

上面的安装应该还会碰到一个问题，这个我暂时没法还原现场，说一下如何解决吧，这个问题是由于缺少DevKit，也就是上面下载的第二个7z的包，而引起的，那么我们只需要安装它即可。

首先解压缩，然后cd到根目录

{% highlight bash %}
ruby dk.rb init
ruby dk.rb install
{% endhighlight %}

这样就安装好了，如果碰到问题，比如下的版本不对啥的，手动更改配置config.yml中的路径指向你安装的ruby的根路径再运行install。

##搭建博客

[阮一峰的网络日志](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)详细的介绍了如何从0开始搭建一个在github上可用的博客，只是没有介绍jekyll的安装，对于从来没有接触过ruby的人来说，碰到一些坑难以避免，所以我前面总结了一下jekyll的安装，对于第一个HelloWorld的搭建，按照它的介绍一步步来应该是没啥问题的，但是对于我来说，我并不精通前段技术如html和css或者bootstrap，只是大概能看懂，而又不想搭建一个毫无色彩的博客，所以我需要选择一个我觉得还ok的框架，然后专心的写文章即可，而不是摆弄那些样式，做的非常的Geek。

####选择jekyll主题

所谓的主题其实是别人写好的一些样式和代码，方便懒人如我这种快速搭建一个看的过去的博客用的，我对主题的要求是两点，响应式布局，因为我可能会在手机上浏览自己写的文章，竟可能的简单，功能只需要有联系方式能向大家介绍自己，能给主题按自定义的标签分类和按照时间分类，并且稍微带一点点颜色即可。[jekyllthemes](http://jekyllthemes.org/)上搜集了很多老外编写的主题，Github上面还有很多中国人编写的主题，但是没有上传到上面的那个网站。我选择的主题是[Jekyll Metro](http://jekyllthemes.org/themes/jekyllmetro/)，这么个主题没有再折腾我更长时间，我把那些twitter，Facebook，linkin等等的都给删了，只是自己添加了一个Github的链接。然后就是about和blog。并且去掉了评论和搜索。

