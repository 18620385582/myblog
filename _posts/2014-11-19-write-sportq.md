---
layout: post
title:  "模仿制作去动网站"
categories: misc client
tags: misc client 
---

看了一下html和css的视频，没有专门找html5和css3的，找的是那种什么8小时学会html啥的，感觉一个静态页面的制作还算挺简单的，因此打算模仿[去动官网](http://www.sportq.com/index.html)制作一个网站。
几点说明，在模拟的过程中，不会进行css初始化和浏览器的适配，只在chrome浏览器适用就ok，其次，去动官网是响应式布局，我只模仿在浏览器最大时的效果，不做响应式布局，再次，会通过审查元素来将人家的结构和大小抄下来。并且其中用到js的地方不做，比如官方微博或者加入我们里面的一些点击效果。在所以感觉这种模仿应该挺简单的，将过程一步一步记录下来。在写这个文章的时候我还没有开始模仿，并且我一边模仿一边记录。

#首页

用google的审查元素发现，首页两个大div，一个nav做导航，一个container做内容，container包含header，main和footer，main包含3个div。大致先布局出来。
nav完成效果如下：
![a](http://ww3.sinaimg.cn/large/005yyi5Jjw1emgbd1w497j30cv01pwec.jpg)


header分为大背景，小背景，两个按钮，就是a标签，因为没有初始化css，所以需要自己去调节margin啥的，跟审查元素的不太一样。
那两个按钮基本上把css拷贝过来就可以用。效果如下
![a](http://ww2.sinaimg.cn/large/005yyi5Jjw1emgcy8rn1ej30zn0hjacx.jpg)

main区域分三块，每一块都有两张图片加一个边框，去动还做了图片看不到的时候显示文字，这里我就没必要做了，主要是熟悉html和css的编写么。

footer区域就比较简单了，就是一段版权的文字而已，超链接我都没加。

#关于，加入，协议

都有主页的nav，可以直接copy过去。我都是在页面内部添加的css，懒得模块化了。加入我们的模块里面有几个超链接是用jquery实现的，我也没去实现它。

#总结

css+html总体来说比较简单，但是对于距离的把握，还有css浮动布局的理解还是挺麻烦的。不像android有多种布局方式，div的布局只有浮动，所以浮动和清除浮动在水平布局方面就显得特别重要。
还有div的盒子模型以及margin重叠也是一些容易出差错的地方，总的来说，很容易上手，但是如果是纯手写并且要做的像老手一样快捷好看，还是需要长时间的练习。或者去找一种方便的css框架如bootstrap。