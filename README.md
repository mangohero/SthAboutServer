# Linux服务器上手指南
这个Wiki旨在帮助使用Linux服务器的朋友们学习和查询一些简单的技巧和问题.
主要面向的是一些使用Python进行深度学习相关工作的同学, 设计一些环境配置、程序运行的方法.

# 基础上手
利用Python进行深度学习代码编写, 个人建议使用Anaconda配置代码环境. 
Anaconda不仅能提供Python的环境, 也可以提供其他的开发环境G++、CUDA等, 方便大家进行版本控制.
入门上手可以阅读[conda使用教程](https://conda.io/docs/user-guide/getting-started.html).

# FAQ
1. Anaconda的更新速度很慢怎么办? 

  这是由于Anaconda的服务器在国外导致, 国内的可以使用清华的更新源.
  `conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/`
  `conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/`
  `conda config --set show_channel_urls yes`
  参见 https://mirror.tuna.tsinghua.edu.cn/help/anaconda/

2. 服务器上的CUDA环境是8.0, 我想使用9.0怎么办?

  利用Anaconda在自己的目录下安装一个CUDA环境
  `conda intsall -c anaconda cudatoolkit=9.0`
  
3. 常见的深度学习一般使用特定的矩阵库, 默认会跑满所有的CPU核数, 如何设置指定的核数?

  设置矩阵库使用核数可以参考这个
  https://stackoverflow.com/questions/30791550/limit-number-of-threads-in-numpy
  看numpy用的啥矩阵库可以参考这个
  https://codeday.me/bug/20180923/259874.html
