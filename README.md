# Compiler
Linux LLVM 
记Ubuntu16.04虚拟机（virutalbox）装LLVM
对于Linux操作系统完全小白，每一步都很辛酸，记录下自己的历程，也希望为后人提供一点点帮助。

1.安装Ubuntu虚拟机16.04LTS

官网下载Ubuntu 16.04LTS,一开始下载的麒麟版，发生闪烁问题，查了貌似有少部分用户出现该问题，只能增    强英语能力，下载LTS为了长期支持。

Ubuntu虚拟机安装教程: blog.csdn.net/u012732259/article/details/70172704

2.安装中文输入法ibus

一开始下载了搜狗拼音包，发现自己并不会安装。查阅资料发现需要安装中文输入法框架。有两种，一个是flix...,我选择了ibus,前者据说也有潜在问题。

ibus中文输入法安装教程:搜索关键词出来的第一个教程误导小白，尝试后得到如下教程：

https://www.cnblogs.com/xcb0730/p/6808592.html

3.安装重点LLVM+Clang

这个安装花费了好几天，中间无数错误和坑

最后得出结论：阅读官网教程：llvm.org/docs/GettingStarted.html 读DOCS！！！

网上很多教程写的都有问题，而且自从LLVM更新之后，老版本的./configure命令失效，必须使用Cmake安装！

以下两个教程相对比较完整和正确：

blog.csdn.net/fan2273/article/details/76439042

https://www.jianshu.com/p/e8d3c38ebe77

步骤简而言之：安装LLVM->安装Clang->安装Cmake->(还没安完）

安装Cmake:blog.csdn.net/flydreamforever/article/details/65454018 （不过make我改成了make -j8）据说可以加速？（blog.csdn.net/lj402159806/article/details/76408597）

Ps:终端打开: ctrl+alt+T

终端内复制/粘贴: ctrl+shift+c / ctrl+shift+v

不知道是我的网络有问题（估计是）：svn下载LLVM遇到 svn not connected 然后文件locked up 解决方法是：进入当前操作的文件目录cd xx，使用命令svn cleanup

cmake装了不下五次 每次装要花费几小时 由于不敢开多核 所以只能慢慢等 还有就是磁盘需要太大 超过了25G 我只好又重新下载VM 重安UBUNTU 不过发现VM 真的比VBOX强一些 tools很轻易安装好了（为了可以全屏显示） VBOX 增强功能需要很麻烦 而且我没成功
