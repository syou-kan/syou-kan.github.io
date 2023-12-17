---
title: maven-无法解析插件
headimg: https://static.dearxuan.com/background/pc/13.jpg
date: 2023-10-15
categories:
 - maven
tags:
- 无法解析插件
- maven开发
- maven报错
keywords:
- 开发时的配置错误
---

报错信息

![image-20231031140219605](assets/image-20231031140219605.png)

刚开始是修改`maven` 源为阿里源,但是却无法解决问题.

![image-20231031140344700](assets/image-20231031140344700.png)

你可以先尝试修改阿里源

应用[知乎](https://www.zhihu.com/question/350864269/answer/993425872)一位大佬的的回答

![image-20231031140653841](assets/image-20231031140653841.png)

当然如果你成功了就可以结束了,但是我猜你,修改完成后,依然报错

![image-20231031140834059](assets/image-20231031140834059.png)

我先告诉你原因:

- 是因为刚开始`maven`在下载时,网速不好,一直没有下载完成时,你就将下载强制结束了,结果就是虽然没有下载成功但是文件夹和文件已经创建完成了.

![image-20231031141148610](assets/image-20231031141148610.png)

![image-20231031141234439](assets/image-20231031141234439.png)

这样就造成了虽然你更换了阿里源,但是文件夹和文件已经创建也无法重新下载,你需要先将它们删除掉,然后重新下载.

如果你没有修改本地仓库位置时一般路径是`C:\Users\a8480\.m2\repository`,找到你要删除的文件夹

比如 我的仓库路径是 `E:\File\maven_lib\repository`

![image-20231031141148610](assets/image-20231031141148610.png)

路径是`“仓库位置”\org\apache\maven\plugins\maven-compiler-plugin` 文件夹下有一个 `3.11.0`文件夹,将文件夹删除掉 我的这个报错就好了

- 成功解决

![image-20231031141519594](assets/image-20231031141519594.png)
