---
title: Github+hexo搭建博客详细记录
date: 2024-11-05 19:47:04
tags:
---

**全部搭建过程参考文章：**[**https://blog.csdn.net/yaorongke/article/details/119089190**](https://blog.csdn.net/yaorongke/article/details/119089190)

SSH设置：https://github.com/pengwenwu/skill-tree/blob/master/Hexo/hexo%20%2B%20github%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2%E6%95%99%E7%A8%8B.md




### **一、准备工作**

 

#### **1.**   **注册GitHub账号**

首先需要有一个GitHub账号，没有的话到先到GitHub官网注册（https://github.com/）。

注册可参考GitHub申请账号教程https://blog.csdn.net/yaorongke/article/details/119086305

#### **2.** **安装Git**

在自己电脑上安装好Git，hexo部署到GitHub时要用。参考 Git安装(网址：https://blog.csdn.net/yaorongke/article/details/119085413?fromshare=blogdetail&sharetype=blogdetail&sharerId=119085413&sharerefer=PC&sharesource=weixin_62431476&sharefrom=from_link)

![ ](/img/Github-hexo搭建博客详细记录/image1.png)

![ ](/img/Github-hexo搭建博客详细记录/image2.png)




#### **3.** **安装NodeJS**

在自己电脑上安装好NodeJS，Hexo是基于NodeJS编写的，所以需要安装NodeJS和npm工具。可参考NodeJS安装及配置(Windows)——

https://blog.csdn.net/yaorongke/article/details/119084295?fromshare=blogdetail&sharetype=blogdetail&sharerId=119084295&sharerefer=PC&sharesource=weixin_62431476&sharefrom=from_link

我的安装具体步骤：

##### **（1）下载安装包**

NodeJS官网下载地址：https://nodejs.org/zh-cn/download/

![ ](/img/Github-hexo搭建博客详细记录/image3.png)
下载安装包后双击安装包开始安装，一路点击Next即可，安装完成后，msi格式的安装包会自动添加环境变量。

安装finish后打开cmd，执行命令node -v查看node版本

![ ](/img/Github-hexo搭建博客详细记录/image4.png)

在安装node的同时也安装了npm，执行 npm -v 查看npm版本

![ ](/img/Github-hexo搭建博客详细记录/image5.png)

成功查看后就安装完成可以正常使用了，参考文章内还有讲解修改全局包配置，但我不需要这个所以省略后半部分，有需要可访问步骤3的网址。

 

### **二、创建仓库**

**1.** 在GitHub上**创建一个新的代码仓库**用于保存我们的网页。点击**Your repositories**，进入仓库页面。

![ ](/img/Github-hexo搭建博客详细记录/image6.png)
**2.** **点击New**按钮，进入仓库创建页面。

![ ](/img/Github-hexo搭建博客详细记录/7.png)

**3.** **填写仓库名**（必须与用户名一致），格式必须为<用户名>.github.io，然后点击Create repository。

![ ](/img/Github-hexo搭建博客详细记录/8.png)

 **4.** **点击creating a new file**创建一个新文件，作为我们网站的主页。

![ ](/img/Github-hexo搭建博客详细记录/9.png)
**5.** **新文件的名字必须为index.html**，内容先随便写一个简单的，填写之后点击Commit new file提交。

![ ](/img/Github-hexo搭建博客详细记录/10.png)
填写内容示例如下：

![ ](/img/Github-hexo搭建博客详细记录/11.png)
**6.** 在仓库页面，从上方导航栏**进入“Settings”-“Pages”**,找到主页的地址，示例为 https://yaorongke.github.io/

 

![ ](/img/Github-hexo搭建博客详细记录/12.png)
**7.** 接下来直接访问查询到的主页地址https://yaorongke.github.io/，可以看到一个比较简陋的网页：

![ ](/img/Github-hexo搭建博客详细记录/13.png)




### **三、安装Hexo**

Hexo 是一个基于NodeJS的静态博客网站生成器，使用Hexo不需开发，只要进行一些必要的配置即可生成一个个性化的博客网站，非常方便。Hexo官网https://hexo.io/zh-cn/

 

#### **1.**   **安装hexo**

注意，**第一个坑来了！**——自行创建一个WorkSpace-blog目录，在该目录下安装hexo，安装hexo命令以官网为准npm install hexo-cli -g，参考文章内的命令不知道为啥不可用，归结为坑（bushi）

`npm install hexo-cli -g`

![ ](/img/Github-hexo搭建博客详细记录/14.png)

2. 安装成功后查看版本

`hexo -v`

3. 创建一个项目 hexo-blog 并初始化，

`hexo init blog`

`cd blog`

`npm install`

4. 本地启动

`hexo g`

`hexo server`

![ ](/img/Github-hexo搭建博客详细记录/15.png)
这里有个踩过的坑：

启动失败了，原因是**4000端口被占用**，使用hexo s -p 8080命令**更换端口**.( 启动时需要在hexo-blog目录下)以自己的目录为准。



​                 更换为8080端口即可成功启动                



​                 启动失败，4000端口被占用                

![ ](/img/Github-hexo搭建博客详细记录/16.png)



 

### **四、更换主题**

#### **1.** 下载Fluid主题

  进入[Fluid官网](https://github.com/fluid-dev/hexo-theme-fluid)安装主题，**点击“最新 release 版本”**下滑找到**“Assets”**部分。

![ ](/img/Github-hexo搭建博客详细记录/17.png)

下载压缩包并解压到 “hexo-blog” – “themes” 目录，并将解压出的文件夹**重命名为 fluid**
![ ](/img/Github-hexo搭建博客详细记录/18.png)




#### **2.**   **指定主题**

如下修改hexo-blog目录中的 _config.yml文件的them和language（用vscode软件打开hexo-blog目录会非常好修改，后续需要执行的命令行也可以直接在vscode终端执行）：

![ ](/img/Github-hexo搭建博客详细记录/19.png)

我的vscode修改界面：
![ ](/img/Github-hexo搭建博客详细记录/20.png)


3. #### **创建「关于页」**

首次使用主题的「关于页」需要**手动创建**：

`hexo new page about`

创建成功后，编辑博客目录下 /source/about/index.md，**添加 layout 属性**。

修改后的文件示例如下：
![ ](/img/Github-hexo搭建博客详细记录/21.png)


### **五、发布到GitHub Pages**

 

#### **1.**   **安装hexo-deployer-git**
![ ](/img/Github-hexo搭建博客详细记录/22.png)


2. 修改 hexo-blog目录下的config.yml，配置 GitHub 相关信息

坑！

配置.yml文件时，**注意空格！！！**否则报错

![ ](/img/Github-hexo搭建博客详细记录/23.png)

接下来两个推送方式：

（1）参考文章内（如下）的配置方式部署不知道为什么一直没成功，放弃了。。。。。
![ ](/img/Github-hexo搭建博客详细记录/24.png)

![ ](/img/Github-hexo搭建博客详细记录/25.png)
这个问题暂时没解决，推送换了ssh连接

 

（2）换成ssh推送继续往下肝，这里开始参考开头提到的第二篇文章：[**https://github.com/pengwenwu/skill-tree/blob/master/Hexo/hexo%20%2B%20github%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2%E6%95%99%E7%A8%8B.md**](https://github.com/pengwenwu/skill-tree/blob/master/Hexo/hexo %2B github搭建个人博客教程.md)

![ ](/img/Github-hexo搭建博客详细记录/26.png)
![ ](/img/Github-hexo搭建博客详细记录/27.png)
以上步骤非常清晰，浅提几个点：

l  一开始没有.ssh目录，执行了命令ssh-keygen -t rsa -C “my email”命令，这里我是在c:/用户/username/目录下执行的，生成完成后用记事本打开id_ras.pub文件，然后Ctrl-A复制所有内容。

l  接下来的github->头像->Settings→SSH kyes→Add SSH key，粘贴复制的内容。对应图片放这里：
![ ](/img/Github-hexo搭建博客详细记录/28.png)

![ ](/img/Github-hexo搭建博客详细记录/29.png)

l  最后的url配置的就是步骤二-7中的主页地址

![ ](/img/Github-hexo搭建博客详细记录/30.png)

l  repo的内容在仓库页面-code-SSH可以直接复制
![ ](/img/Github-hexo搭建博客详细记录/31.png)

l  全部修改完配置保存后执行hexo g -d，部署完成后就可以打开主页：

![ ](/img/Github-hexo搭建博客详细记录/32.png)


--------------------------------

再附上之前我自己写的注意事项，记录点东西确实还是能帮上忙哦！
1. Node下载，注意看是否直接下载安装程序，压缩包还不会使用。
2. 在npm运行，就是Node，下载好了cmd到folder，执行npm命令就行。
3. 注意.ignore文件，否则上传一大堆。
4. github分支很重要，默认执行分支main，这就会出现部署到master分支，本地能成功执行hexo，但是github访问不到，去setting切换分支即可。
![ ](/img/Github-hexo搭建博客详细记录/image.png)
5. github pages没有实时更改内容是很正常的，发布前先`hexo s -p 8080`，本地执行没问题，先使用 `hexo clean` 清除本地缓存，然后`hexo g -d`提交。
6. 新建文章很简单，`hexo new name` 即可。
7. 发布照片时，要把生成的照片文件夹放到source下的img静态资源文件夹，养成良好习惯，放在post里面无法访问。


![ ](/img/Github-hexo搭建博客详细记录/37.png)

8. 稍微有一些地方没设置成功，都无法访问。今天的情况是，都部署成功了，githubPages能看得到第一篇文章，但是后续发布的文章一直没法看到，github代码也显示push成功。出了什么问题呢？确保 GitHub Pages 设置正确：

在仓库的 Settings > Pages 中，设置发布来源为 GitHub Actions 自动生成的文件。直接上图，真的shit，好在终于成功啦！
![ ](/img/Github-hexo搭建博客详细记录/38.png)

--------------------------------
以上是我帮ie家族一员Winnie配置时遇到的问题，尽管9月份我已经配置过了，苦于没有留下详细的说明文档，导致这次踩坑很多还是要不停搜索。于是我们两人决定写一份说明文档，当然，这份保姆级别教程要感谢Winnie~  Jessie主要是技术支持哈哈哈。Winnie会来看我的主页吗，不知道，祝她找工作顺利！可爱善良的女孩呀，幸福会来敲门的！



