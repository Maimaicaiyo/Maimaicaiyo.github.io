---
categories:
- 博客
	-博客更新维护
---

本来在家里搭建了自己的博客，然后有时候在公司电脑想提交更新博客，搜集相关资料，总结如下方法。

> 主要思路：利用git分支实现
>
> hexo生成的静态博客文件默认放在master分支上。
>
> hexo的源文件（部署环境文件）可以都放在hexo分支上（可以新创建一个hexo分支），换新电脑时，直接`git clone hexo分支地址`即可。

### 一、hexo搭建博客原理

hexo博客的部署环境目录：

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200607102918.png)

hexo博客的目录结构解析：

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/2859254-8ac27ff2282797b0 (1).jpg)

上传到github( master)的文件是这些：

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200607103129.png)

> 1.hexo帮助把博客发送到github，同时把md文件转换成网页文件。
>
> 2.hexo目录下的文件和github上的文件是不同的，public文件夹的文件通过hexo d 上传到github去了，其他的文件则留在本地目录下。

### 二、家里电脑上的操作

#### 1.对username.github.io仓库新建hexo分支，并克隆

> (1)在Github的username.github.io仓库上新建一个xxx分支，并切换到该分支
>
> (2)该仓库->Settings->Branches->Default branch中将默认分支设为xxx，update保存；
>
> (3)将该仓库克隆到本地，进入该username.github.io文件目录。

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200607004035.png)

完成上面步骤后，在当前目录使用Git Bash执行`git branch`命令查看当前所在分支，应为新建的分支xxx：

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200607005547.png)

#### 2.将家里电脑博客的部署文件拷贝进新克隆的分支username.github.io文件目录

先将本地博客的部署文件（**Hexo目录下的全部文件**，modules等文件可不用）全部拷贝进username.github.io文件目录中去。

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200607095349.png)

接下来，进入username.github.io文件目录下，将该目录下的全部文件提交到xxx分支，提交之前需注意：

> * 将themes目录以内中的主题的.git目录删除（如果有），因为一个git仓库中不能包含另一个git仓库，提交主题文件夹会失败。
> * 可能有人会问，删除了themes目录中的.git不就不能`git pull`更新主题了吗，很简单，需要更新主题时在另一个地方`git clone`下来该主题的最新版本，然后将内容拷到当前主题目录即可

#### 3.提交hexo分支

依次执行以下代码，即可将博客的hexo部署环境提交到GitHub个人仓库的xxx分支。

> (1)git add .
>
> (2)git commit -m 'hexo' （引号内容可改）
>
> (3)git push

分支上的内容已经更新了：

![](https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/20200607100142.png)

master分支和xxx分支各自保存着一个版本，master分支用于保存博客静态资源，提供博客页面供人访问；xxx分支用于备份博客部署文件，供自己维护更新，两者在一个GitHub仓库内互不冲突，完美！

### 三、公司电脑上的操作

至此，你的博客已经可以在其他电脑上进行同步的维护和更新了，方法很简单：

> 将新电脑的生成的ssh key添加到GitHub账户上
>
> 在新电脑上克隆username.github.io仓库的xxx分支到本地，此时本地git仓库处于xxx分支
>
> 切换到username.github.io目录，执行`npm install`(由于仓库有一个.gitignore文件，里面默认是忽略掉  node_modules文件夹的，也就是说仓库的hexo分支并没有存储该目录[也不需要]，所以需要install下)

到这里了就可以开始在自己的电脑上写博客了！

> 编辑、撰写文章或其他博客更新改动
>
> 依次执行`git add .`、`git commit -m 'hexo'`（引号内容可改）、`git push`指令，保证xxx分支版本最新
>
> 执行`hexo d -g`指令（在此之前，有时可能需要执行`hexo clean`），完成后就会发现，最新改动已经更新到master分支了，两个分支互不干扰！

### 四、回到家里电脑更新并提交博客

**注意： 每次换电脑进行博客更新时，不管上次在其他电脑有没有更新，最好先`git pull`**

