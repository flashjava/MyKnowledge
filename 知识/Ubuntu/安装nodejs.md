* ##Git方式安装##

    1.  Install the dependencies:
        1. `sudo apt-get install g++ curl libssl-dev apache2-utils`
        2. `sudo apt-get install git-core`

    2. Run the following commands:
        1. `git clone git://github.com/ry/node.git`
        2. `cd node`
        3. `./configure`
        4. `make`
        5. `sudo make install`

说明：指定编译版本，重要！（参考页面：[详解如何在ubuntu上安装nodejs](https://cnodejs.org/topic/4f16442ccae1f4aa270010b5)）

* ##压缩包方式安装##

* 首先确保系统安装来python,gcc,g++,如果没有则安装：
    >`sudo apt-get install python`
    >
    >`sudo apt-get install build-essential`
    >
    >`sudo apt-get install gcc`
    >
    >`sudo apt-get install g++`

* 从[nodeJS官网](http://nodejs.org/)下载最新源代码包：node-v0.8.14.tar.gz
* 解压：
    >`tar -zxf node-v0.8.14.tar.gz`
    >
    >`cd node-v0.8.14`

*  安装
    * 默认安装：
        >`./configure`
        >
        >`make`
        >
        >`sudo make install`

    * 选择目录方式安装：
        >`./configure –prefix=/usr/node`
        >
        >`make -j 5 #5=CPU核数+1`
        >
        >`sudo make install`

* 安装结束，可以用下面的命令检查安装的版本：
    >`node –version`