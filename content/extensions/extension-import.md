---
date: 2019-01-08T21:07:13+01:00
title: "通过crx文件导入extension"
weight: 11
keywords:
- extensions
- chrome
description : "通过crx文件导入extension, 实现共享"
---

有的时候，同事需要extension, 但是不能科学上网。这时可以通过crx文件导入extension, 实现共享。

## 导出

点击右上角的菜单icon（三条横线那个）->更多工具->扩展程序。

来到chrome://extensions/页面，开发者模式打上勾，点击“打包扩展程序…”，在弹出的窗口里面填写 扩展程序根目录 项


通常在当前chrome浏览器对应的`***\User Data\Default\Extensions\要导出的插件id\子文件夹\`

比如我这里是：

- 文件夹`C:\Users\a\AppData\Local\Google\Chrome\User Data\Default\Extensions\cmnlfmgbjmaciiopcgodlhpiklaghbok\`
- extension 对应id 是`cmnlfmgbjmaciiopcgodlhpiklaghbok`

点击打包扩展程序，在刚才选的那个文件目录（到插件id那一级）下就有了一个crx文件（打包的插件）和一个pem文件（密钥）了。

## 导入

首先，你要有一个crx文件类型的插件

把下载的文件后缀名crx改为rar，解压缩得到文件夹（有错误提示不用理会）打开该文件夹。

如果出错了:

> 打开该文件夹，把里面的”_metadata”文件夹改名为”metadata”（去掉开头的下杠），不去掉的话会报一个“Cannot load extension with file or directory name _. Filenames starting with ’_‘ are reserved for use by the system.”


进入扩展程序中心，启用开发者模式，加载正在开发的程序包，选择刚才的文件夹就行了，搞定！

## 参考

- https://blog.csdn.net/software_kid/article/details/49124809