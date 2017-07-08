# lab-building
一、反向代理

介绍

通过 Node.js 可以很轻松的创建 web 反向代理。

实验楼即将使用 Github 取代现有的代码库，在实验环境中开放了 Github 访问权限。为了测试，我们准备编写一个程序来反向代理 Github 网站，请你帮助完成请求 Github 内容并把内容写入 Node.js http 服务的功能。

首先下载代码到指定位置：

$ cd /home/shiyanlou
$ wget http://labfile.oss.aliyuncs.com/contestlou11/proxy.js
代码中需要你补全 TODO 部分的内容，代码基本逻辑：

创建一个 http 服务
在 http 服务中请求 Github 网站
把获取到的 Github 网站内容写入创建的 http 服务的 response
目标

确保完成的代码文件路径 /home/shiyanlou/proxy.js
服务处于运行状态，即已经执行了 node proxy.js 后再点击提交结果
保持服务监听在 3000 端口，不要修改端口号
不要修改 TODO 部分之外的代码内容
提示语

使用 Stream pipe 更方便

二、课程学习记录

介绍

我们开发了一个 Node.js 程序，通过 Sequelize 向实验楼的 sqlite3 数据库中写入用户，课程和学习记录数据。但这个程序在你的实验环境中无法运行，请修复其中的 bug，让程序可以正确执行。

首先下载程序到指定位置：

$ cd /home/shiyanlou
$ wget http://labfile.oss.aliyuncs.com/contestlou11/study.js
下载依赖的包并解压：

$ cd /home/shiyanlou
$ wget http://labfile.oss.aliyuncs.com/contestlou11/node_modules.tar
$ tar xvf node_modules.tar
程序使用 node 运行，基本逻辑描述如下：

删除先前存在的数据库，重新创建用户，课程，学习记录三张表
插入一个用户
插入一个课程
插入用户学习课程 10 分钟的学习记录
输出用户学习记录
目标

完成任务需要达成的目标：

程序存放的位置 /home/shiyanlou/study.js
在 /home/shiyanlou/ 目录下安装所需包，即安装完成后会出现 /home/shiyanlou/node_modules 目录
不要改变程序的插入数据的逻辑，以及插入数据库的内容，只需要修复其中影响运行的 BUG
不要修改数据库的保存路径及表的名称
提示语

Promise 用法

知识点

Node.js 基础语法
Sequelize 用法
Promise 用法


三、Oauth2认证

介绍

我们知道，可以用 github 直接登录实验楼网站，其中使用了 Oauth2 认证方式。这里我们用 Node.js 开发了一个网站，也可以使用 github 直接登录，并会把用户信息存储在 sqlite3 中。但这个程序在你的实验环境中无法运行，请修复其中的 bug，让程序可以正确执行，并且使用你的 GitHub 账号登录成功。

在程序中我们使用了 passport 来实现 Oauth2 认证。

首先安装 sqlite3 并下载程序到指定位置：

$ sudo apt-get install sqlite3
$ cd /home/shiyanlou
$ wget http://labfile.oss.aliyuncs.com/contestlou11/auth.js
下载依赖的包并解压：

$ cd /home/shiyanlou
$ wget http://labfile.oss.aliyuncs.com/contestlou11/node_modules.tar
$ tar xvf node_modules.tar
配置域名解析 github.com（不配置有可能测试的时候无法 PASS）：

$ sudo vim /etc/hosts
# 添加下面两行的内容到 /etc/hosts 文件中
192.30.255.112  github.com
192.30.255.116  api.github.com
程序中的代码基本逻辑描述如下：

使用 Express 创建 http 服务
连接 sqlite3 数据库，并创建一个用户表
创建 passport 认证策略
创建相关 Express 路由
程序正常执行的步骤如下，使用 GitHub 登录：

访问 http://localhost:3000
点击 log in 访问登录页
此处输入图片的描述

点击 log in with github 使用 GitHub 登录
此处输入图片的描述

跳转到 GitHub 授权页面，确认授权
此处输入图片的描述

此处输入图片的描述

授权成功则跳转到首页，第一次登录时 user 信息会存入数据库
授权失败则跳转到登录页
此处输入图片的描述

授权成功后跳转到首页，点击 profile 访问 profile 页面
查看 profile 页面返回的登录信息
此处输入图片的描述

当成功进入到 profile 页面的时候就可以点击 提交结果 了！

目标

完成任务需要达成的目标：

程序存放的位置 /home/shiyanlou/auth.js
在 /home/shiyanlou/ 目录下安装所需包，为了避免耗费时间，在实验准备阶段步骤中已经提供了压缩包下载
修复其中影响运行的 bug，不要改变程序和数据库存储的路径，也不要改变监听的端口号和数据库的表结构
保持程序处于运行状态，同时使用自己的 Github 账号成功登录后，进入到 profile 页面后再点击 提交结果
提示语

passport 用法

知识点

Node.js 基础语法
passport 用法
Node.js 程序调试