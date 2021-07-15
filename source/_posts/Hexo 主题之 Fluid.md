---
title: 【手把手系列2】 Fluid 主题配置教程
index_img: https://avatars2.githubusercontent.com/t/3419353?s=280&v=4
categories:
- 博客搭建
tags:
- 博客搭建
- 小白教程
---


# Hexo 主题之 Fluid

### 0. 前言

Hexo搭建好的博客是使用`landscape`主题，看起来挺丑的....不是很喜欢，所以我们到hexo官网上寻找一些好看的主题进行更改。

> hexo主题网站： https://hexo.io/themes/

这里有几百个主题供你选择，由于太多而且网站中也没有对这些主题进行筛选的功能，让人难以选择，所以我们推荐到github上寻找合适的主题：

![github上的搜索](https://gitee.com/youlan_lan/md_image/raw/master/20210607132952.png)

<img src="https://gitee.com/youlan_lan/md_image/raw/master/20210607133049.png" alt="" style="zoom: 67%;" />

从而可以看出，最受欢迎的是`Next主题`，还有几个主题的star数也不少，大家根据自己的喜好挑选即可。

浅谈几个挑选合适主题的标准：

* star数、fork数多的
* 使用文档写的比较详细的
* 更新时间比较近的，或者更新频率比较高的

### 1. Fluid主题介绍

<img src="https://gitee.com/youlan_lan/md_image/raw/master/20210607135407.png" alt="" style="zoom:67%;" />

这是一款 Material Design 风格的 Hexo 主题，以简约的设计帮助你专注于写作： https://github.com/fluid-dev/hexo-theme-fluid

![](https://gitee.com/youlan_lan/md_image/raw/master/20210607135202.png)

![](https://gitee.com/youlan_lan/md_image/raw/master/20210607135243.png)

整体上，简约风，个人是比较喜爱的。最重要的是这个主题的文档写得非常地详细，查起来非常容易，上手快。

### 2. 安装

安装的话，github的README.md文档写的很清楚了

这里直接复制粘贴一下：

**方式一：**

```
npm install --save hexo-theme-fluid
```

然后在博客目录下创建 `_config.fluid.yml`，将主题的 [_config.yml](https://github.com/fluid-dev/hexo-theme-fluid/blob/master/_config.yml) 内容复制进去。

**方式二：**

```yaml
git clone https://github.com/fluid-dev/hexo-theme-fluid.git
```

或者直接下载压缩文件，解压后放到themes目录，将解压出来的文件夹命名为`fluid`

### 3. 修改配置

修改 Hexo 博客目录中的 `_config.yml`：

```
theme: fluid  # 指定主题

language: zh-CN  # 指定语言，会影响主题显示的语言，按需修改
```

### 4. 创建页

首次使用主题的「关于页」需要手动创建：

```
hexo new page about
```

创建成功后，编辑博客目录下 `/source/about/index.md`，添加 `layout` 属性。

修改后的文件示例如下：

```
---
title: about
date: 2020-02-23 19:20:33
layout: about
---

这里写关于页的正文，支持 Markdown, HTML
```

**分类页、标签类也类似**

创建了这两个页，在写文章的时候，在最前面写上对应的category、tags即可

例如：

```markdown
---
title: 使用Hexo搭建博客（基础版）
index_img: https://gitee.com/youlan_lan/md_image/raw/master/20210607012255.png
categories:
- 博客搭建
tags:
- 博客搭建
- node
- git
- github
---
```

具体的参数可以查阅官方文档： https://hexo.io/zh-cn/docs/front-matter

### 5. 一些基础配置

本篇文章只介绍一些基础的配置，足够你搭建一个好看的博客。想要高级玩法请到fluid上查看指南~

打开`_config.fluid.yml`文件，这个文件已经很贴心的为我们写好了中文注释，大家根据自己的喜好进行配置即可~

**我们从上外下看吧**

#### 1. 图标favicon

这个是用于浏览器标签的图标

也就是这个小东东

![就是这个小东东](https://gitee.com/youlan_lan/md_image/raw/master/20210607141316.png)

favicon 和 apple_touch_icon设置成同一个就可以了

#### 2. 代码高亮

这个部分可以默认，也可以根据你的喜好进行修改

#### 3. 打字机效果fun_features

我这里把是否循环播放效果打开了，一直重复打字机的动画效果

![](https://gitee.com/youlan_lan/md_image/raw/master/20210607141600.png)

#### 4. 颜色color

这里是对一些颜色的配置，可以直接默认，我这边是把`navbar_bg_color` 设置成和主页图片相近的颜色，这样视觉效果更好

![](https://gitee.com/youlan_lan/md_image/raw/master/20210607141715.png)

#### 5. 字体font

默认好像是16px，我觉得有点小了，改成19px比较合适

![](https://gitee.com/youlan_lan/md_image/raw/master/20210607141845.png)

#### 6. 懒加载lazyload

这个打开，懒加载可以使得页面更加流畅，看不到的范围就先不加载，前端的小伙伴都懂~

这里有一个加载时的占位图片loading_img也可以设置一下

#### 7. 导航栏navbar

主要设置的参数：

* blog_title
* menu（一般这个默认就可以了）

#### 8. 搜索功能search

打开这个，可以在网页里通过关键字搜索到博客内容

#### 9. 页脚footer

根据自己的需要进行修改吧

我这边只修改了content和打开了statistics

content的内容需要使用**HTML**进行编写

![](https://gitee.com/youlan_lan/md_image/raw/master/20210607142609.png)

#### 10 . banner

刚创建好的banner都是一样的图片，不太好看，我们先对banner进行配置。

```yaml
banner_img: /img/bg/example.jpg   # 对应存放在 /source/img/bg/example.jpg
```

```yaml
banner_img: https://static.zkqiang.cn/example.jpg
```

推荐使用网络链接

> 如果是本地图片，目录文件夹可自定义，但必须在 source 目录下，博客与主题的 source 目录最终会合并，因此优先选择博客的 source。
>
> 图片大小建议压缩到 1MB 以内，否则会严重拖慢页面加载。

1. index

   ![index](https://gitee.com/youlan_lan/md_image/raw/master/20210607142729.png)

   效果：

   ![index](https://gitee.com/youlan_lan/md_image/raw/master/20210607142806.png)

   里面有个api接口，感兴趣的小伙伴可以去了解了解，可以使用随机播放不同的text

2. 文章页 Post Page

   * default_index_img 文章默认图片，如果没有指定 index_img 时会使用该图片，若两者都为空则不显示任何图片

   * meta 这里有一些文章标题下方的元信息设置，根据自己的喜好设置就可以了，需要使用的功能就设置成 true 就行了

   * updated 一些关于更新后显示的信息
   * copyright 版权声明，同样的content里需要使用html格式
   * 其他的就默认就好了，不是关键的功能

3. 其他页面

   根据自己的喜好设置就好了，可以一路默认

**主要是以下两个参数**

* banner_img
* banner_img_height

每个页面都可以配置一个banner_img，直接搜索`banner_img`快速定位进行修改

### 6. _config.yml

这里的注释是英文的，可能看起来不是那么方便，这里主要是两个地方需要修改，其他直接默认就可以了

1. 最开头的网站信息

   ![](https://gitee.com/youlan_lan/md_image/raw/master/20210607143908.png)

2. 以及最末尾的部署设置

   ![](https://gitee.com/youlan_lan/md_image/raw/master/20210607143912.png)

这里可以配置二次元人物，具体就到网上搜索就好了~ 搜`live2 看板娘`

### 7.  最后

算是一个傻瓜式教程了。。。。省略了非常多的步骤。next听说可玩度很高，配置之后网页非常好看（但我不喜欢又关我什么事hhh），next的贡献者非常多，所以next主题的维护以及更新等等方面都非常地强。

但是！fluid的简约风真的非常nice！！！安利一波

### 8. 小彩蛋

对了，在设置banner_img的时候，由于banner比较大，所以把图片放大之后非常地模糊。。。所以这个也让我浪费了非常多时间在找高清图以及增强图片清晰度的方法

* 增强图片清晰度的方法： 

  * 用ps：emmm....难度有点大，ps小白表示不想

  * 一些ai图像修复网站：傻瓜式操作，还不错

* 一些高清图片的网站

  这个是我后来在fluid的博客上看到的...应该早点看到，泪目

  * **元气桌面 https://desk.duba.com/**
  * https://wallpaperhub.app/
  * https://wallhaven.cc/
  * https://unsplash.com/

