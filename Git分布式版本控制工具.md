# Git**分布式版本控制工具**



## Git概述

Git是一个开源的[分布式](https://baike.baidu.com/item/分布式/19276232?fromModule=lemma_inlink)版本控制系统，可以有效、高速地处理从很小到非常大的项目[版本管理](https://baike.baidu.com/item/版本管理/2511538?fromModule=lemma_inlink)。 也是[Linus Torvalds](https://baike.baidu.com/item/Linus Torvalds/9336769?fromModule=lemma_inlink)为了帮助管理[Linux内核](https://baike.baidu.com/item/Linux内核/10142820?fromModule=lemma_inlink)开发而开发的一个开放源码的[版本控制软件](https://baike.baidu.com/item/版本控制软件/2617766?fromModule=lemma_inlink)。

## Git安装

安装地址：https://git-scm.com/download

**根据自己电脑操作系统的版本进行选择对应的下载地址**

![](https://github.com/Shy2593666979/Git-version/blob/main/image/image-20230722202013369.png)

**ps：**下载Git是在GitHub平台下载的，需要科学上网

![image-20230722171351870](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722171351870.png)

安装Git后右键桌面可显示 Git Bash 和 Git GUI

**Git GUI：Git提供的图形界面工具** 

**Git Bash：Git提供的命令行工具**



## Git基础配置

右键打开Git Bash输入

git config --global user.name “用户名”

git config --global user.email "邮箱名称"



完成后输入

git config user.name

git config user.email

查看是否配置完成

![image-20230722172636569](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722172636569.png)

## Git基础操作指令

### Git获得本地仓库 

1）在电脑的任意位置创建一个空目录作为我们的本地Git仓库 

2）进入这个目录中，点击右键打开Git bash窗口 

3）执行命令git init

4）如果创建成功后可在文件夹下看到隐藏的.git目录。

![image-20230722173356363](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722173356363.png)

**ps：**需要执行ls -al才能查看隐藏文件



![image-20230722173506827](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722173506827.png)


### 提交文件
git add (工作区 --> 暂存区) 

git commit (暂存区 --> 本地仓库)

**实例演示：**

首先在git_test01文件夹中创建test.txt文件，现在已经是在工作区，通过git add进入暂存区（git add . 代表提交当前文件夹），看看test文件状态

![image-20230722173844722](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722173844722.png)

现在已经显示test.txt文件已经进去暂存区, git commit -m "注释"提交到本地仓库，再次查看文件状态

![image-20230722174309090](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722174309090.png)

commit -m中的-m可有可无，如果没有加 -m的话，commit后也得进去编辑器进行注释

现在test.txt文件已经提交到本地仓库了



### 查看提交日志

![img](file:///C:\Users\枯木逢春i\AppData\Roaming\Tencent\Users\2593666979\QQ\WinTemp\RichOle\{JLQ@G]RGIV0]PLTVPXUKG6.png)

### 版本回退

命令形式：git reset --hard commitID

commitID 可以使用 git-log 或 git log 指令查看 

git reflog 这个指令可以看到已经删除的提交记录

**实例演示:**

****

刚才咱们已经在git_test01文件中创建了本地仓库，还把test.txt文件提交到本地仓库，第一次提交的注释为”first commit“

现在要把test.txt文件内容修改后再次提交，注释为"second commit"

git log查看提交日志，显示有两次提交，分别为”first commit“和"second commit"

![image-20230722175519040](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722175519040.png)

现在test文件内容为![image-20230722175639191](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722175639191.png)

现在通过版本回退到第一次提交的文件中

![image-20230722175937032](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722175937032.png)

现在已经把test.txt文件回退到第一次提交的时候了，vi test.txt可看到就是第一次提交时的结果.。



### 分支指令

几乎所有的版本控制系统都以某种形式支持分支。 使用分支意味着你可以把你的工作从开发主线上分离 开来进行重大的Bug修改、开发新的功能，以免影响开发主线。

* 查看本地分支

   命令：git branch 

* 创建本地分支

   命令：git branch 分支名 

* 切换分支(checkout) 

  命令：git checkout 分支名

* 我们还可以直接切换到一个不存在的分支（创建并切换）

  命令：git checkout -b 分支名

* 合并分支(merge) 一个分支上的提交可以合并到另一个分支

   命令：git merge 分支名称 

* 删除分支 不能删除当前分支，只能删除其他分支

   git branch -d b1 删除分支时，需要做各种检查

   git branch -D b1 不做任何检查，强制删除

![image-20230722183619490](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722183619490.png)

![image-20230722183920957](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722183920957.png)

![image-20230722184358170](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722184358170.png)

## 远程仓库

* GitHub（ 地址：https://github.com/ ）是一个面向开源及私有软件项目的托管平台，因为只支持 Git 作为唯一的版本库格式进行托管
* Gitee（地址： https://gitee.com/ ）是国内的一个代码托管平台，由于服务器在国内，所以相比于 GitHub，码云速度会更快
* GitLab （地址： https://about.gitlab.com/ ）是一个用于仓库管理系统的开源项目，使用Git作 为代码管理工具，并在此基础上搭建起来的web服务,一般用于在企业、学校等内部网络搭建git私服。

### 搭建远程仓库

因为GitHub在国内访问速度比较慢，我们现在使用Gitee来搭建远程仓库

<img src="C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722185012226.png" alt="image-20230722185012226" style="zoom: 50%;" />

### 配置公钥

**配置SSH公钥** 

* 生成SSH公钥 ssh-keygen -t rsa 
* 不断回车 如果公钥已经存在，则自动覆盖 
* 获取公钥 cat ~/.ssh/id_rsa.pub

**查看公钥**

* ssh -T git@gitee.com

打开gitee的设置找到SSH公钥

![image-20230722185713012](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722185713012.png)

### 操作远程仓库

**添加远程仓库**

命令： git remote add <远端名称> <仓库路径>

远端名称，默认是origin，取决于远端服务器设置 

仓库路径，从远端服务器获取此URL

![image-20230722190028742](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722190028742.png)

**查看远程仓库**

* 命令：git remote

**推送到远程仓库** 

命令：git push [-f] [--set-upstream] [远端名称 [本地分支名][:远端分支名] ] 

* 如果远程分支名和本地分支名称相同，则可以只写本地分支 git push origin master

*  -f 表示强制覆盖 

* --set-upstream 推送到远端的同时并且建立起和远端分支的关联关系。 

* git push --set-upstream origin master 

* 如果当前分支已经和远端分支关联，则可以省略分支名和远端名。 git push 将master分支推送到已关联的远端分支。

**从远程仓库克隆** 

* 如果已经有一个远端仓库，我们可以直接clone到本地。 

* 命令: git clone <仓库路径> [本地目录] 

* 本地目录可以省略，会自动生成一个目录

**从远程仓库中抓取和拉取** 

* 远程分支和本地的分支一样，我们可以进行merge操作，只是需要先把远端仓库里的更新都下载到本地，再进行操作。 

* 抓取 命令：git fetch [remote name] [branch name] 抓取指令就是将仓库里的更新都抓取到本地，不会进行合并 
* 如果不指定远端名称和分支名，则抓取所有分支。 
* 拉取 命令：git pull [remote name] [branch name] 
* 拉取指令就是将远端仓库的修改拉到本地并自动进行合并，等同于fetch+merge 
* 如果不指定远端名称和分支名，则抓取所有并更新当前分支。

![image-20230722191615093](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722191615093.png)

​     ![image-20230722191705610](C:\Users\枯木逢春i\AppData\Roaming\Typora\typora-user-images\image-20230722191705610.png)
