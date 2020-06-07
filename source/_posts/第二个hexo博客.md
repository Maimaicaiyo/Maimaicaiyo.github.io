---
categories:
- 博客
- 优化
---



提示存在了

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200601183034.png)

<!--more-->

私钥和公钥

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200601183800.png)

 **这里提示输入密码 我本来以为是输入自己的git账号的密码， 但是发现 括号写着（空 无口令）**

​            **于是搜了一下这里的相关资料 这里的意思是 使用ssh连接 这里创建一个你的连接的密码，**

​             **如果为空 则默认使用私钥进行连接**



### 其他图标icon

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200601225444.png)

查看html：`lcd-blog\public\index.html`

可以看到引入了`FontAwesome`字体图标

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200602014228.png)

可以将Font Awesome图标使用在几乎任何地方，只需要使用CSS前缀`fa`，再加上图标名称。 Font Awesome是为使用内联元素而设计的。我们通常更喜欢使用`<i>`，因为它更简洁。

可以看到class为`fa-monologue`,但是查询min.css并无这个class，所以网页显示空白图标；

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200602014506.png)

有个问题，重新部署后，这个类又变回默认的了??

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200602023645.png)

修改后的html要保存：`ctrl+s`

点击侧边栏后，图标又不见了>>因为进入了diary的html文件，所以要进入`lcd-blog\public\diary\index.html`修改，其他侧边栏同理

最后也不行，尝试在min.css文件中添加对应的样式：

```css
/* 自定义图标 */
.fa-monologue:before{content:"\f251"}
.fa-diary:before{content:"\f02d"}
.fa-poetry:before{content:"\f0f4"}
```

默认带出来的样式就不用改，这样`lcd-blog\public\diary\index.html`这些就不用改了，成功



### github私有共有库



### ssh公钥私钥



### 引入的css多了?v=2.1.5





预览全文这个推荐使用`<!-- more -->`，可以自定义哪一行才出现阅读全文。而且在排版不受影响。因为设置`auto_excerpt`为true在首页看到的排版会被压缩，影响美观。

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200602130407.png)



### 设置置顶

#### 文章置顶

目前已经有修改后支持置顶的[仓库](https://github.com/netcan/hexo-generator-index-pin-top)，可以直接用以下命令安装。

```cmd
$ npm uninstall hexo-generator-index --save
$ npm install hexo-generator-index-pin-top --save
```

然后在需要置顶的文章中加上`top: true`即可。

#### 设置置顶标志

打开：`/blog/themes/next/layout/_macro` 目录下的`post.swig`文件，定位到`<div class="post-meta">`标签下，插入如下代码：

```swig
{% if post.top %}
  <i class="fa fa-thumb-tack"></i>
  <font color=7D26CD>置顶</font>
  <span class="post-meta-divider">|</span>
{% endif %}
```

效果如下：

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200602150950.png)



### 增加文章更新时间

`lcd-blog\themes\hexo-theme-next\_config.yml`

`updated_at`改为true

```yml
post_meta:
  updated_at: true
```

进`themes\hexo-theme-next\layout\_macro\post.swig`文件可以编辑细节

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200606165117.png)

### 文章排版

如果粘贴为纯文本

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200602170031.png)



### hexo博文，用<!--more-->设置摘要，点击“阅读全文”后，会自动跳转到<!--more-->后面的文本

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/GIF 2020-6-3 10-13-46.gif)

主题配置文件：改为`scroll_to_more: false`。点击阅读全文就会滚动条跳到文章的最上面

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200603102930.png)





### 在 Markdown 语言中，如何实现段首空格的显示 ？

段首缩进这件事，应该是 CSS 或者其他排版工具的事情，Markdown 奉行的是样式和内容分开的哲学。

即使手动输入空格，&nbsp; 也是很不推荐的方法。我推荐全角空格，切换到全角模式下（一般的中文输入法都是按 shift + space）输入两个空格就行了。这个相对 &nbsp; 来说稍微干净一点，而且宽度是整整两个汉字，很整齐。

直接写
半方大的空白&ensp;或&#8194;
全方大的空白&emsp;或&#8195;
不断行的空白格&nbsp;或

```php
&nbsp;//半角空格（英文）
&emsp;//全角空格（中文）
```



### hexo添加新菜单并实现新菜单的文章归类

如何将文章归类到这个新建的菜单下面呢？

其实点击poetry进去的是`/categories/诗意`，跟进去`/categories`然后再点击分类，效果一样。

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/GIF 2020-6-3 0-58-52.gif)

所以在根目录配置文件`_config.yml`，修改对应的menu，url也改了

```html
menu:
	monologue: /categories/独白/|| monologue
	diary: /categories/日记/|| diary
	poetry: /categories/诗意/|| poetry
```



### 不蒜子统计访客

1、打开next主题配置文件\themes\next_config.yml，搜索找到**busuanzi_count**，把enable设置为true

```html
busuanzi_count:
  # count values only if the other configs are false
  enable: true
```

2、同样是在next主题配置文件\themes\next_config.yml下，搜索**footer**，在它底下添加counter，设值为true

```html
footer:
  # 不蒜子统计
  # 用于控制浏览次数和访问数量显示与否
  counter:
    enable: true
```

3、来到themes\next\layout_partials，找到**footer.swig**文件，打开编辑，在底下添加代码

```swig
{% if theme.footer.counter %}
    <script async src="//dn-lbstatics.qbox.me/busuanzi/2.3/busuanzi.pure.mini.js">   
    </script>
{% endif %}
```

完成！

后来发现数据没显示出来。原来是不蒜子官网换了域名，所以引用的js要换。

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200603153523.png)

首先需要先找到NexT下引用不蒜子统计的方法。文件路径为`/theme/next/layout/_third-party/analytics/busuanzi-counter.swig`文件。**footer.swig**文件的也要改。src换成：

```html
https://busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js
```

效果如下：

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200603154105.png)





### 另一个博客`hexo d`出现问题

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200603160350.png)

应该是本地ssh还是上一个博客的，绑定了上一个博客的github的ssh。所以连接不上远程仓库。

到`C:\Users\Administrator\.ssh`

最好是新建文件夹备份所有用过的ssh，需要的时候再从里面复制粘贴。最后连接成功！

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200603172012.png)