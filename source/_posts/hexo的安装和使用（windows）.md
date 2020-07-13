---
title: hexo的安装和使用（windows）
date: 2020-07-13 10:57:04
tags: hexo 
---

## hexo的安装和使用（windows）

### 一.环境的准备

1. 安装包管理工具（scoop）

   一个windows下的开源包管理工具，使用它帮我们安装git node 等常用工具，具体的介绍可参考其他文章，本文不做赘述

   ```powershell
   # 1. 输入以下命令确保 脚本的可以本地执行
   set-executionpolicy remotesigned -scope currentuser
   # 2. 执行下列脚本开始安装 scoop （国内访问不佳，最好挂代理）
   iex (new-object net.webclient).downloadstring('https://get.scoop.sh')
   # 3. 查看帮助命令
   scoop help
   # 4. 安装aira2 提高scoop下载安装速度
   scoop install aira2
   ```

2. 安装 git

   ```powershell
   scoop install git
   ```

3. 安装node

   ```powershell
   # 默认安装最新版node，如果需要其他版本，请使用n模块自行切换
   scoop install nodejs
   ```

   查看node 和npm 安装情况

   <img src="http://picture.yanfeng.space/markdown/20200712185819.png" alt="产看node 和 npm版本" style="zoom: 67%;" />

   跟换npm的镜像源为淘宝源

   ```powershell
   npm config set registry https://registry.npm.taobao.org
   ```

4. 安装hexo

   ```powershell
   npm install -g hexo-cli
   ```

   ![](http://picture.yanfeng.space/markdown/20200712191118.png)

5. 查看hexo 版本信息

   ```powershell
   hexo -v
   ```

   <img src="http://picture.yanfeng.space/markdown/20200712191524.png" style="zoom:67%;" />

6. 初始化hexo

   创建一个文件夹并进入，以后这个文件夹就是我们hexo的根目录了

   ```powershell
   cd blog
   # 当前初始化当前目录。 或者使用 hexo init <dirname> 初始化并创建目录
   hexo init .
   # 安装包相应的包 会自动的安装package.json下的包
   npm install
   ```

7. 文件夹说明

   查看目录结构 

   ``` powershell
   dir
   #=====================
   .
   │  .gitignore
   │  package-lock.json
   │  package.json	
   │  _config.yml  # 主配置文件
   ├─node_modules  # 依赖包
   ├─scaffolds     # 生成文章的模板文件
   ├─source		# 文章源码
   │  └─_posts
   └─themes		# 主题
   d-----      node_modules  # 依赖包
   d-----      scaffolds     # 生成文章的模板文件
   d-----      source		  # 文章的源码
   d-----      themes		  # 主题
   -a----      .gitignore    
   -a----      package-lock.json
   -a----      package.json  
   -a----      _config.yml   # 主配置文件
   ```
   
8. 配置

   用合适的编辑器打开配置文件，Windows 下可以用 默认的记事本或者notepad3 打开，mac和linux 可以用vi，vim打开

   ```powershell
   notepad _config.yml
   ```

   