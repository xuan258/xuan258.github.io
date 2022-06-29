---
title: 【Hexo】Mac OS上使用Hexo + Github搭建博客教程
tags:
categories:
cover: https://sunny-blog.oss-cn-beijing.aliyuncs.com/%E5%8D%9A%E5%AE%A2%E5%B0%81%E9%9D%A2%E5%9B%BE%E6%96%87%E4%BB%B6/cover5.jpg
---

# hexo介绍

Hexo是一个快速、简洁且高效的博客框架，具体可以见[Hexo官网](https://hexo.io/zh-cn/)，它在github上的star数现在已经到34.7k，Hexo主要有以下特点：
1. 超快速度：Node.js所带来的超快生成速度，可以让上百个页面在几秒内完成渲染。
2. 支持Markdown：Hexo支持Github Flavored Markdown 的所有功能，甚至可以整合 Octopress 的大多数插件。
3. 一键部署：只需一条指令即可部署到 Github Pages，Hexoku 或其他平台。
4. 插件或可扩展性：强大的 API 带来无限的可能，与数种模版引擎（EJS，Pug，Nunjucks）和工具（Babel，PostCSS，Less/Sass）轻易集成。

# 安装环境
### 安装<code>Node.js</code>

下载地址：[Node.js](https://nodejs.org/en/)

![Node.js](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_01.png)
### 安装淘宝镜像
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 使用命令安装淘宝镜像：</span><br><span class="line">npm install -g cnpm --registry=https://registry.npm.taobao.org</span><br></pre></td></tr></tbody></table></figure>

### 安装Hexo
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 使用命令去安装Hexo</span><br><span class="line">cnpm install -g hexo-cli</span><br></pre></td></tr></tbody></table></figure>

### 安装成功
安装成功后，使用<code>hexo -v</code>命令去查看Hexo的版本：

![安装成功显示图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_02.png)

# 初始化Hexo Blog

### 新建一个文件夹

我这里创建一个名为Blogs的文件夹，并进入该文件夹内

### 初始化Hexo
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 初始化hexo</span><br><span class="line">hexo init</span><br></pre></td></tr></tbody></table></figure>

初始化成功如下：

![初始化成功显示图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_03.png)

这时候Blogs下的目录结构如下：

![这时候Blogs下的目录结构](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_04.png)

### 本地启动Hexo
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 启动Hexo</span><br><span class="line">hexo s</span><br></pre></td></tr></tbody></table></figure>

![本地启动Hexo](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_05.png)

浏览器打开博客网站

![本地启动Hexo](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_06.png)

# 创建博客文章

### 创建博客
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 创建一篇博客</span><br><span class="line">hexo n "我的第一篇博客文章"</span><br></pre></td></tr></tbody></table></figure>

文章在Blogs目录下的结构如下：

![文章在Blogs目录下的结构](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_07.png)

### 清理项目缓存

新增博客文章或修改博客文章内容，需要执行此命令

<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 清理之前生成的网站</span><br><span class="line">hexo clean</span><br></pre></td></tr></tbody></table></figure>

### 重新生成博客
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 重新生成博客</span><br><span class="line">hexo g</span><br></pre></td></tr></tbody></table></figure>

### 再次启动项目
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 再次启动博客网站</span><br><span class="line">hexo s</span><br></pre></td></tr></tbody></table></figure>

浏览器页面展示如下：

![浏览器页面显示图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_08.png)

# 修改网站主题
Hexo框架默认的是landscape主题，Hexo上有三百多种主题，大家可以上[Hexo 官网](https://hexo.io/themes/)选择自己喜欢的主题，我这里以butterfly为例：

### 下载butterfly主题
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 下载butterfly</span><br><span class="line">git clone https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly</span><br></pre></td></tr></tbody></table></figure>

![下载butterfly主题显示图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_09.png)

我们下载的主题都存放在Blogs/themes文件夹下：

![主题目录图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_10.png)

### 修改项目配置文件

主题下载下来之后，我们需要在项目配置文件_config.yml里面修改我们的主题：

![修改的图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_11.png)

把默认的<code>landscape</code>修改为我们下载好的主题<code>butterfly</code>

### 重新生成项目

这时候再执行我们Hexo三连：
<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 清理项目缓存</span><br><span class="line">hexo clean</span><br><span class="line"></span><br><span class="line">// 重新生成项目</span><br><span class="line">hexo g</span><br><span class="line"></span><br><span class="line">// 本地启动项目</span><br><span class="line">hexo s</span><br></pre></td></tr></tbody></table></figure>

Tips：重新生成项目和本地启动项目可以合并：<code>hexo g & hexo s</code>

再次打开项目，效果图如下：
![报错信息图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_12.png)

哈哈啊哈～ 惊喜不～ 意外不～ 这是个啥玩意？？？

莫慌～ 发现问题 - 找到问题 - 分析问题 - 解决问题：

原因其实也很简单，我们没有安装pug和stylus的渲染器，执行如下命令：

<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">// 在Blogs目录下 安装pug 和 stylus渲染器</span><br><span class="line">npm install --save hexo-renderer-jade hexo-generator-feed hexo-generator-sitemap hexo-browsersync hexo-generator-archive</span><br></pre></td></tr></tbody></table></figure>

安装完成后，重新生成项目：

![重新生成项目图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_13.png)

到这里，我们的主题修改就完成了，后期我们可以根据自己的需要去修改butterfly的配置文件，让我们的博客网站更加个性化。

下一篇文章我将说说如何修改主题让我们的博客网站更具个性化。

关于Hexo搭建博客到这里就讲得差不多了，下面我们就想怎么把博客部署到Github上。

# 部署博客到Github

首先，你得要有一个自己的Github账号吧，我相信99.99%的开发者都是有Github账号的，如果你是那0.01%，请前往Github自行注册。

### 创建仓库

在Github里创建一个存放博客项目的仓库，操作如下

![存放博客项目的仓库](img/warehouse-name.png)

这里有两个注意点：

1. 仓库的名称必须与你Github账号名相同
2. 仓库必须以<code>gitHub.io</code>结尾

比如你Github账号名叫：<code>xiaoxunbao</code>，那你新建的这个仓库名就叫：<code>xiaoxunbaoi.github.io</code>

创建之后，我们就有了一个存放博客项目仓库：

![存放博客项目仓库](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_16.png)

### 安装Hexo部署插件

进入到Blogs目录下，安装部署插件：

<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">cnpm install --save hexo-deployer-git</span><br></pre></td></tr></tbody></table></figure>

![安装部署插件图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_17.png)

###修改项目配置文件

好了，万事俱备，只欠修改_config.yml文件了，打开_config.yml文件，拖拽到最后，修改文件：

![原配置文件图片](https://sunny-blog.oss-cn-beijing.aliyuncs.com/20220509/20220509_18.png)

修改为：

![修改后配置文件图片](/img/github-config.png)

注意：repo为你刚创建的Github项目的地址，如果你是使用的vim打开的_config.yml，记得修改了要:wq保存退出

### 重新生成项目

清理项目缓存：

<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">hexo clean</span><br></pre></td></tr></tbody></table></figure>

重新生成博客：

<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">hexo g</span><br></pre></td></tr></tbody></table></figure>

部署到云端（Github）：

<figure class="highlight bash"><table><tbody style="display:block;overflow:auto;border:none"><tr><td class="code"><pre><span class="line">hexo d</span><br></pre></td></tr></tbody></table></figure>

注意：这里每次使用hexo d部署到Github为了安全都要求输入账号密码，如果你不希望每次都输入账号密码，可以跟博主一样设置Github的SSH Keys，以后每次发布到Github就不需要输入账号密码了。














