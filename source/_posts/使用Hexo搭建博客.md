---
title: 【手把手系列1】使用Hexo搭建博客（基础版）
index_img: https://gitee.com/youlan_lan/md_image/raw/master/20210607012255.png
categories:
- 博客搭建
tags:
- 小白教程
- 博客搭建
- node
- git
- github
---


# 使用Hexo搭建博客（基础版）

### 0. 前言

就目前来说，有非常多平台可以发表自己的博客，像CSDN、简书、掘金等等，并且这些平台有一定的流量，一篇好的博客很快就能吸引来大量的浏览量。

* 这些平台的优点很明显：操作简单，傻瓜式操作，可以进行交互。
* 但是也存在一些比较难受的缺点：平台的限制及一些广告，因违规而删除你的文章

而去购买服务器来进行搭建博客又有点大费周折了，而且成本极高，不利于小白快速上手。

于是，使用博客框架以及github这一方式就介于上述两种之间。我们使用hexo框架，再将搭建好的博客依托到github page平台上。这样，我们只用专心于我们的写作了。

> github毕竟是国外的网，打开确实有点慢，而国内站点码云的`gitee page` 被暂停使用了……
>
> ![码云没了...](https://gitee.com/youlan_lan/md_image/raw/master/20210607001959.png)

### 1. Hexo的介绍

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

Hexo是基于Node.js的静态博客框架，依赖少易于安装使用，可以方便的生成静态网页托管在GitHub和Coding上，是搭建博客的首选框架。

> 官方文档上的使用方法非常的详细，可以放心食用：https://hexo.io/zh-cn/docs/
>
> 本文只是摘取部分关键的步骤

### 2. 使用hexo搭建博客的步骤

1. 安装Git
2. 安装Node.js
3. 安装Hexo
4. GitHub创建个人仓库
5. 将hexo部署到GitHub
6. 更改主题
7. 设置个人域名
8. 发布文章

### 3. 安装

##### 1. 安装Git

- Windows：下载并安装 [git](https://git-scm.com/download/win).
- Mac：使用 [Homebrew](http://mxcl.github.com/homebrew/), [MacPorts](http://www.macports.org/) 或者下载 [安装程序](http://sourceforge.net/projects/git-osx-installer/)。
- Linux (Ubuntu, Debian)：`sudo apt-get install git-core`
- Linux (Fedora, Red Hat, CentOS)：`sudo yum install git-core`

##### 2. 安装 Node.js

Node.js 为大多数平台提供了官方的 [安装程序](https://nodejs.org/en/download/)。对于中国大陆地区用户，可以前往 [淘宝 Node.js 镜像](https://npm.taobao.org/mirrors/node) 下载。

> 上述两个安装方法不是本次教程的重点，不会安装的小伙伴可以到网上搜一下教程~

##### 3. 安装Hexo

安装好git之后，我们可以右击选择`Git Bash here`可以打开一个命令行窗口，输入：

```yaml
$ npm install -g hexo-cli
```

这是全局安装hexo脚手架，之后在这台电脑使用hexo搭建新的博客就不需要再次安装了

新建文件夹

```yaml
$ hexo init <folder>
$ cd <folder>
$ npm install
```

会生成很多文件夹，看不懂没关系，知道怎么配置就可以了。

- node_modules: 依赖包
- public：存放生成的页面
- scaffolds：生成文章的一些模板
- source：用来存放你的文章
- themes：主题
- **_config.yml: 博客的配置文件**

> 关于文件里面的参数可以到官方文档上查看，这里不多说了。

##### 4. 启动

```yaml
$ hexo clean
$ hexo g
$ hexo s
```

这三个命令非常重要

在浏览器中输入`localhost:4000` 就可以看到生成的博客页面了

`ctrl + c ` 可以关掉服务

### 4. 创建GitHub仓库

GitHub非常好用，配合着git一起使用，主要用于团队协作和下载优秀者的代码

> 详情可以自己去搜一搜

先注册一个账号，创建一个 `yourusername.github.io`的仓库

> 必须用这个名字，不然GitHub page不能识别你的文件

生成SSH添加到GitHub

> 这也不是我们本次教程的重点，具体步骤可以到网上搜搜教程，属于git的使用
>
> 只有把你电脑的ssh添加到你的GitHub上，你的git才能正常使用

### 5. 将Hexo部署到GitHub上

找到配置文件 `_config.yml`，翻到最后，根据自己的仓库进行配置

```yaml
deploy:
  type: git
  # YourgithubName需要改成你的GitHub账号名
  repo: https://github.com/YourgithubName/YourgithubName.github.io.git
  # 这里是你的代码推送到的分支名
  branch: master
```
<p style="color:red">注意：</p>
<p style="color:red">这里的branch需要填写仓库主支名，不然页面打开是没有效果的~</p>

安装deploy-git：

```
$ npm install hexo-deployer-git --save
```

然后

```yaml
$ hexo clean
$ hexo generate
$ hexo deploy

$ hexo g --d   # 一键部署
```

`hexo clean` 清除之前生成的东西
`hexo generate` 生成静态文章，可以用 `hexo g` 缩写
`hexo deploy` 部署文章，可以用 `hexo d` 缩写

部署成功后，在[http://yourname.github.io](http://yourname.github.io/) 这个网站就可以访问到你的博客了

### 6. 更改主题

到 https://hexo.io/themes/ 挑选自己喜欢的主题

推荐到GitHub上找star最多的几个主题，star多证明这一主题使用的人也多，相对地使用文档也会更加完整清晰，体验感更佳√

这里就不细讲了，后面会更新一篇使用`Fluid`主题的简易配置教程

> 待更……

### 7. 设置个人域名

现在你的域名是`yourname.github.io`，但是感觉好像逼格不够……

hhh 所以，你可以根据自己的喜好买一个看起来牛逼的域名

到阿里云上购买一个域名，不同的后缀价格不太一样，可以选择一个便宜的域名玩玩，看你的选择咯。

买到域名之后，需要进行实名认证，然后再到域名控制台中，找到你买的域名，点击解析，添加解析。

> 解析线路选择默认，不要选择境外

买好之后进入你的仓库，在settings中设置Custom domain，输入你的域名。

接着，你在你的博客文件source中创建一个名为`CNAME`文件，不用后缀，写上你的域名

然后再使用那几个命令进行部署就可以了

### 8. 发布文章

创建一个新的文件，然后在source/_post中打开markdown文件，就可以开始编辑了

```yaml
hexo new newpapername
```

写完之后，使用那三个命令进行部署

建议安装vscode，vscode带有命令行窗口非常方便，再下载一个`Markdown Preview Enhanced`插件，可以实时查看Markdown文件书写的效果图

### 9. 最后

最重要的两个命令:

```yaml
$ hexo clean
$ hexo g --d
```

建议新人先使用这种方式手动部署

待以后对GitHub等工具更为了解之后，可以使用GitHub page的自动部署功能

> 待更……