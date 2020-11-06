---
title: Gitee+PicGo图床搭建笔记
date: 2020-08-27 17:10:15
tags:
  - 技术
  - Gitee
  - Markdown
  - Typora
categories:
  - [技术,备忘]
comments: true
---

{% note info %} 
图床是干什么的？图床一般是指储存图片的服务器。
设置图床之后，在博客中插入的图片链接就可以随时在线预览。
{% endnote %}

神奇的PicGo就是为了解决这个问题诞生的，它可以将图片上传到指定的图床上，然后返回markdown链接，直接粘贴到你的文档中。

目前国内环境，使用PicGo +  [码云](https://links.jianshu.com/go?to=https%3A%2F%2Fgitee%2Fcom)来实现markdown图床，既可以白嫖，又方便快捷，可以说得上是最优解。

<!--more-->

## 软件安装

- 图库上传管理软件：[PicGo](https://github.com/Molunerfinn/PicGo/releases)

  包括`picgo-plugin-gitee-uploader`插件

- MarkDown编辑软件：[Typora](https://www.typora.io/)

### PicGo安装

**安装后界面如下：**

<img src="https://gitee.com/kzcy/pic/raw/master/img/82714.png" alt="软件界面" style="zoom:80%;" />

### 插件安装
选择最底下的`插件设置`，搜索**gitee**，安装第二个插件`gitee-uploader1.xxx`。

<img src="https://gitee.com/kzcy/pic/raw/master/img/82708.png" alt="软件界面" style="zoom:80%;" />

{% note warning %} 

这里注意一下，必须要先安装[node.js](https://nodejs.org/zh-cn/)才能安装插件。

{% endnote %}


##  建立[码云](https://gitee.com)仓库

### 新建仓库

点击右上角的`+`号，`新建仓库`。

<img src="https://gitee.com/kzcy/pic/raw/master/img/82706.png" alt="新建仓库" style="zoom:100%;" />

**新建仓库的要点如下：**

1. 输入一个仓库名称；

2. 其次将仓库设为公开；

3. 勾选使用Readme文件初始化这个仓库。

   <img src="https://gitee.com/kzcy/pic/raw/master/img/82701.png" alt="盗图一张" style="zoom:100%;" />

点击创建即完成仓库创建。

### 获取token

登录码云账号，点击头像进入`设置`，找到`私人令牌`，点击`生成新令牌`，把`projects`这一项勾上，其他的不用勾，然后`提交`。

<img src="https://gitee.com/kzcy/pic/raw/master/img/82709.png" alt="私人令牌" style="zoom:100%;" />



验证密码之后会出来一串数字，这一串数字就是你的`token`**（不能泄露，否者别人也可以操作你的数据）**，后面设置会用到。

{% note warning %} 

注意：这个令牌只会明文显示一次，建议在配置插件的时候再来生成令牌，直接复制进去，搞丢了又要重新生成一个。

{% endnote %}

## PicGo调教

### 插件配置

选择`图库设置`里的`gitee`选项**（没有安装插件前，没有此选项）**。

**配置要点：**

- **repo**：用户名/仓库名称*（仓库地址后面那一段）；*

- **branch**：分支，填写master；

- **token**：填入前面获取的`私人令牌`；

- **path**：路径，一般填写img；

- **customPath**：提交消息，可不填；

- **customURL**：自定义地址，可不填。

  ![image-20200827165059954](https://gitee.com/kzcy/pic/raw/master/img/image-20200827165059954.png)

### **测试**

随便选一张图片上传，上传之后默认复制链接到粘贴板。

##  PicGo+Typora

MarkDown写作软件很多，但是Typora是兼具功能与颜值的软件之一（也可能是唯一），而且支持实时预览。

**PicGo+Typora**支持图片`拖曳/粘贴`上传到服务器，解决了MarkDown写作图片插入的难题，非常实用。

配置上，打开Typora`设置`，在`图像`便签，按照下面设置即可：

![image-20200827170417361](https://gitee.com/kzcy/pic/raw/master/img/image-20200827170417361.png)

{% cq %}

 **Enjoy！**

{% endcq %}