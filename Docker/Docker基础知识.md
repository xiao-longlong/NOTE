# Docker基础知识

## 指令

### docker images

```
docker images
```

+ 解释

  + image在docker中不指**图像**，而是指**镜像**。
  + 词源：早期的Docker命令使用了一些与航海相关的术语，这可能是因为Docker的创始人之一，Solomon Hykes，有一段时间是一名游艇船长。这些术语的选择是为了与船只和航海有关，以突出Docker的目标是提供轻量级、可移植的容器化解决方案。在航海领域，"image"一词通常用来指代一艘船的外观，即船体的外观。在Docker中，"image"也可以被理解为容器的外观或模板，因为它包含了运行应用程序所需的一切。这种类比可以帮助人们理解镜像的概念，即它是一个静态的、不可更改的实体，类似于船体的外观。

+ 作用

  + 在Docker中，`docker images`命令用于列出本地主机上存储的所有Docker镜像。

  + |                     REPOSITORY                     |        TAG         |   IMAGE ID   |   CREATED    | SIZE   |
    | :------------------------------------------------: | :----------------: | :----------: | :----------: | ------ |
    | lux.x-contion.top:500/x-contion/cuda_conda_pytorch | cu118-py39-torch13 | f97cf1051915 | 4 weeks ago  | 17.7GB |
    | lux.x-contion.top:500/x-contion/cuda_conda_pytorch |       latest       | c702c1b130ac | 4 months ago | 16.6GB |
    |                       alpine                       |       3.16.3       | bfe296a5250  | 7 months ago | 5.54MB |

+ 快速记忆

  + ·REPOSITORY 用于指明来源。
  + TAG 用于标识版本，方便使用时查看版本。
  + IMAGE ID 用于标识此镜像独一无二的ID，用于引用该镜像。

### 将用户添加入docker用户组

+ 作用

  + 使用docker的过程中，很多情况下都需要root权限才可以；
  + 为了避免多次使用sudo命令，故在此将当前用户添加到docker组；

+ 指令

  + ```
    # 添加docker用户组，一般已存在，不需要执行
    sudo groupadd docker
        
    # 将登陆用户加入到docker用户组中
    sudo gpasswd -a $USER docker
    
    # 更新用户组
    newgrp docker
    
    # 测试docker命令是否可以使用sudo正常使用
    docker version
    ```

### docker run

+ 作用

  + 利用镜像创建一个容器

+ 指令

  + ```
    docker run -it 仓库名称:TAG /bin/bash
    ```

+ 指令说明
  + 加上`/bin/bash`是为了创建容器后，能启动一个命令行交互界面，如果不加则容器在后台启动。即`/bin/bash`将当前cmd转到容器中了。