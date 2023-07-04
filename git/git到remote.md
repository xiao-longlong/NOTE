# git到remote

+ 这篇文章旨在记录如何将代码git到远程。
  + 远程包括实验室的github和自己的gitlab。
  + 操作方法包括命令行和git graph两种

## 1.1本地安装git

```shell
# 一般来说只有在新的docker容器或宿主机的新账户上才没有git，即此处的指令并非是必要的。

# 安装git
apt-get update
apt-get install git

# 配置git
# user_name和mail建议用github的。
git config --global user.name "user_name"
git config --global user.email "mail"

# 查看配置，确认成功
git config --global --list
```

## 1.2本地项目配置git

```shell
# 对于每个项目都要配置git才能使用，方法如下

# 初始化新项目的 Git 仓库
git init

# 将项目文件添加到 Git 仓库中
git add .

# 提交项目的初始版本
git commit -m "Initial commit"
```

## 2.1git到实验室的gitlab

### 2.1.1命令行操作

```shell
# 为项目新建分支并切换到此分支（此步骤不必要，如果想直接上传主分支，就不用新建分支）
git branch <新分支名>

# 添加实验室gitlab为远程仓库
git remote add <远程仓库名>(自己命名即可) <gitlab_URL>

# 推到实验室的gitlab上
git push
```
+ 说明
  + <gitlab_URL>需要通过如下网址登陆是实验室的gitlab，或新建项目，或找到要psuh的项目以拿到,如下
> http://git.x-contion.top:1213/

![gitlab_URL](../image/gitlab_URL.png)
