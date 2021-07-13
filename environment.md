# CAT入门教程

## System

CAT需要在Linux下使用，建议选择Ubuntu最新的LTS版本或者通过SSH使用远程服务器。

### 安装Linux系统

测试环境：Ubuntu 20.04 [官方下载][1]

Windows下安装双系统：[教程][2]

> Q：为什么使用Ubuntu？
>
> A：Linux是内核，有多种发行版本，Ubuntu的用户量大，对初学者来说，更方便找到各种问题的解答。

### 使用远程服务器

阮一峰的SSH[教程][3]

### Linux使用

入门推荐阅读：

- 《[快乐的Linux命令行][4]》
- 原版：《[*The Linux Command Line*][5]》

可以参考的网站：

- [菜鸟Linux教程][6]
- [Linux Tutorial][7]

> P.S：kaldi使用shell编写，对shell的掌握和Linux终端的梳理使用对提高效率很重要。

## Driver

默认使用NVIDIA显卡训练，需要安装显卡驱动

- 测试环境：NVIDIA RTX2060 Driver version：460.80

以下提供两种安装方式

方法一：打开“软件和更新”->“附加驱动”，选择推荐版本的nvidia-driver驱动安装。

方法二：打开终端，输入

```shell
sudo ubuntu-drivers devices
sudo ubuntu-drivers autoinstall
```

安装完成后重启系统。

检验安装成功并确认驱动版本：打开终端输入`nvidia-smi`

## Cuda

CAT目前仅支持GPU训练，Cuda为使用NVIDIA显卡训练DNN（Deep Neural Network）的必要开发环境，以下介绍Cuda的安装。

1. 下载前检查驱动版本号对应可以使用的CUDA版本：[versions][14]

2. 到[pytorch官网][16]查看pytorch支持的cuda版本号

   测试环境：CUDA Version 10.2

3. 下载安装需要的[cuda][15]版本（推荐runfile方式）

   安装时选择取消cuda自带的驱动的安装

4. 检查系统cuda版本`cat /usr/local/cuda/version.txt`

   `/usr/local/cuda/`一般是一个链接，链接到`/usr/local/cuda-x.x/`，

   

## Kaldi

## CAT

## Tools

以下介绍一些工作中常用的工具

### Git

免费开源的版本控制系统，[官网][8]

入门教程：

- 廖雪峰的Git[入门教程][10]（较为简单）
- [Gitbook][11]（更加详细）

命令清单：

- 阮一峰的Git[命令清单][9]
- git --help

![Git workflow by 阮一峰](./pictures/git-workflow-ryf.png)

### Markdown

Markdown 是一种轻量级标记语言，易于进行文档的编写。

- 菜鸟Markdown[教程][12]
- Markdown简明语法[教程][13]

推荐使用编辑器：

- vscode + extensions: Markdown All in One, Markdown Preview Enhanced 优点：方便自定义，可以直接配合git插件使用
- typora 优点：所见即所得（推荐）

### IDE

- pycharm 优点：集成功能丰富（推荐）
- vscode 优点：自定义强大

### Others

copytranslator 阅读英文文献便捷查词

dolphin 方便的图形界面文件浏览器

chrome 比firefox更好用（雾）的浏览器

P3X-OneNote Linux下的非官方开源OneNote软件

## How to Solve Problems

以下介绍一些常用的解决工作中困难的方式以及网站

[1]:https://ubuntu.com/download/desktop	"Ubuntu官网下载"
[2]:https://zhuanlan.zhihu.com/p/101307629	"Ubuntu双系统安装教程，知乎"
[3]:https://github.com/wangdoc/ssh-tutorial	"SSH使用教程，阮一峰"
[4]:https://github.com/billie66/TLCL	"《快乐的Linux命令行》"
[5]:http://linuxcommand.org/	"The Linux Command Line"
[6]:https://www.runoob.com/linux/linux-tutorial.html	"菜鸟教程，Linux教程"
[7]:https://github.com/dunwu/linux-tutorial	"dunwu/linux-tutorial"
[8]:https://git-scm.com/	"Git官网"
[9]:./resources/git-cheatsheet-ryf.pdf	"Git常用命令清单，阮一峰"
[10]:https://github.com/numbbbbb/Git-Tutorial-By-liaoxuefeng	"Git入门教程，廖雪峰"
[11]:https://git-scm.com/book/zh/v2	"Gitbook"
[12]:https://www.runoob.com/markdown/md-tutorial.html	"菜鸟教程，Markdown教程"
[13]:https://github.com/Melo618/Simple-Markdown-Guide	"Markdown简明语法教程"
[14]:https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html	"Cuda release notes"
[15]:https://developer.nvidia.com/cuda-toolkit-archive	"Cuda download"
[16]:https://pytorch.org/get-started/locally/	"Pytorch Installation"
