# Linux 服务器上手指南
这个Wiki旨在帮助使用 Linux 服务器的朋友们学习和查询一些简单的技巧和问题.
主要面向的是一些使用 Python 进行深度学习相关工作的同学, 设计一些环境配置、程序运行的方法.
问题主要来源是在实际使用中遇到的问题, 希望随着问题的补充可以把项目不断发展壮大.

大家可以在项目的 Issues 中提问或者私聊给我, 我会把问题汇总整理到这个仓库.

# 基础上手
利用 Python 进行深度学习代码编写, 个人建议使用 Anaconda 配置代码环境. 
Anaconda 的优势有:
1. Anaconda 可以自己虚拟出一个 Python 环境, 与服务器安装的 Python 隔离开, 方便大家同时使用不同版本的 Python (同时跑 Python2, Python3 )、不同版本的 Python 包(例如不同版本的 Tensorflow ).
2. Anaconda 不仅能提供 Python 的环境, 也可以提供其他的开发环境 G++, CUDA等, 方便大家进行其他代码的编写和运行.
3. 可以直接安装各类包, 免去了自己找包 -> 下载 -> 安装 -> 安装失败 -> ... 无限循环的困境.

入门上手可以阅读 [conda 使用教程](https://conda.io/docs/user-guide/getting-started.html).

# FAQ
1. Anaconda 的更新速度很慢怎么办? 
 
  这是由于 Anaconda 的服务器在国外导致, 国内的可以使用清华的更新源.

  `conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/`

  `conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/`

  `conda config --set show_channel_urls yes`

  参见 https://mirror.tuna.tsinghua.edu.cn/help/anaconda/


2. 服务器上的 CUDA 环境是 8.0, 我想使用 9.0 怎么办?

  利用 Anaconda 在自己的目录下安装一个 CUDA 环境

  `conda intsall -c anaconda cudatoolkit=9.0`
  
  
3. 常见的深度学习一般使用特定的矩阵库, 默认会跑满所有的 CPU 核数, 如何设置指定的核数?

  设置矩阵库使用核数可以参考这个

  https://stackoverflow.com/questions/30791550/limit-number-of-threads-in-numpy

  看numpy用的啥矩阵库可以参考这个
  
  https://codeday.me/bug/20180923/259874.html
