# 实验室gitlab上拉取资源使用流程

## 本地准备

+ 在本地需要资源的地方新建好文件夹。
  + 一般只需要新建资源项目的上一级目录。
+ 进入资源项目的上一级文件夹

## 拉取

+ 登录实验室网址

> git.x-contion.top:1213

+ 找到要拉取的资源并复制ssh或http链接
  + ![image-20230703092312246](C:\Users\闲卿\AppData\Roaming\Typora\typora-user-images\image-20230703092312246.png)
+ 在命令行输入如下的指令

```shell
git clone ssh/http链接
```

+ 可能需要将链接中的`git`替换成`lux4`，并在`top`后加上`:1213`，如下。

```shell
# 原指令
git clone http://git.x-contion.top/public_fork/YOLOX.git

# 修改后指令
git clone http://lux4.x-contion.top:1213/public_fork/YOLOX.git
```

## 简单查看

+ 下载完成后可以`cd`进取，并`ls`一下以查看是否资源完整。