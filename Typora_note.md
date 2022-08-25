---
title: "Typora笔记上传Github图片显示问题"
description: 
date: 2022-08-18T17:40:40+08:00
image: 
math: 
license: 
hidden: false
comments: true
draft: false
---



## 用Typora软件编写的Markdown文件上传到github图片丢失问题



Typora是一个很不错的Markdown编辑器。但是在笔记中添加图片相对麻烦。特别是没有设置图片的默认存储路径时，移动md文件或者上传到github上会造成图片丢失。今天在把一个笔记上传到github上时，突然发现

`img src=" "`路径格式的图片没有丢失，探索之后发现这是一个好的方法，但是在操作过程中会增加一点工作量。具体操作如下：



### 把文件存储路径改为相对路径

因为Markdown文件时纯文本文件，因此所以用户无法在 Markdown 文件中直接插入图片文件，而是通过在 Markdown 文件中引用文件路径或者 URL 的方式插入图片，所以默认情况下，Typora 会先将文件保存到一个固定的目录，具体什么目录跟操作系统有关。这里先随便截个图插入到当前文档：

<img src="Typora_note.assets/image-20220818180018215-16614005980711.png" alt="image-20220818180018215" style="zoom:67%;" />

点击图片可以发现该图片默认存放在`C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20220818180018215.png`下。当你在本机内移动该本md文档时，图片还是能正常显示，因为并没有改变文档的位置。但是当你把本文档分享给别人或者上传到自己的github上时，图片无法显示，因为图片是在你自己的电脑上保存着，别人的电脑上没有也就无法显示。

这时，我们可以把保存图片的路径改为相对路径。在Typora中，文件----->偏好设置----->图像。按下图箭头指示修改。

<img src="Typora_note.assets/image-20220818181610709.png" alt="image-20220818181610709" style="zoom:67%;" />

修改完成后当向Typora中插入图片时Typora会自动在该md文件当前目录下新建一个 `  当前文件名.asset`文件夹，用来存放插入该文档的图片。

<img src="Typora_note.assets/image-20220818182553316.png" alt="image-20220818182553316" style="zoom:67%;" />

插入图片的路径就变成了 `Typora_note.assets/image-20220818181610709.png`

这时在分享该文档时可以把md文件和存放图片的文件夹打包成一个文件，注意保持相对路径正确，也就是md文件和   .asset文件夹要保持在同一级目录下。如果只是单纯的分享给别人看，在文件---->导出---->PDF更方便。



### 上传到Gitbub的图片设置



关于图片显示的问题，有些图片上传到Github上就无法显示。先参考这个方法，[(2条消息) 如何解决上传到github上的图片显示不出来的问题_儒雅的烤地瓜的博客-CSDN博客_github显示不了图片](https://blog.csdn.net/sunyctf/article/details/124112909)可以解决图片显示问题。

如果电脑连接了外网，使用了相对路径后，把md文档和保存图片的文件夹都上传到github，图片就可以实时浏览了。



网上有很多用服务器或者插件上传到图集的方法，可以不用外网实现图片的实时浏览，我觉得太麻烦了。今天偶然间发现一个可以弯道超车的方法——缩放图片。

插入图片后点击图片右键选择缩放图片，选择任意尺寸，缩放完成后发现图片的路径变成了HTML格式，这种格式上传到Github上是可以实时浏览的。关于在哪设置图片的路径自动转换成HTML格式的方法，还没找到。

<img src="Typora_note.assets/image-20220825120404392.png" alt="image-20220825120404392"  />

