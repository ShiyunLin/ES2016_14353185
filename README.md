# 关于配置dol的过程

​	14353185_林诗韵



## dol框架												

​	dol（distributed operation layer）是一个可以自动匹配应用到多处理器架构平台shapes的框架。他主要由三个部分组成：dol应用编程传感器、dol功能模拟器和dol匹配优化



## HOW TO INSTALL

### 首先配置g++, java 等环境

​	一开始需要进行更新以及安装ant unzip等功能。另外g++在学习编译原理的时候已经配置过了，就是简单的利用apt-get install g++来完成，不再赘述；关键在于java配置的时候遇到了一些问题：

​	首先使用apt-get install openjdk-7-jdk来配置jdk7, 根据其他同学的反应，应该是可以运行的，但是这样配置的java第二次ant会build fail.所以我在甲骨文官网上下载了jdk8的安装包（jdk-8u101-linux-i586.tar.gz）来自己配置java 环境；

​	具体的操作没有截图，步骤如下：

​	a. 在/usr/lib中建立java文件夹

​	b.在这里解压压缩包，并且命名为jdk8

​	c.打开.bashrc文件加入jdk路径，然后运行.bashrc文件

​	d.配置jdk文件

    sudo update-alternatives --install /usr/bin/java java /usr/lib/java/jdk8/bin/java 300
    sudo update-alternatives --install /usr/bin/javac javac /usr/lib/java/jdk8/bin/javac 300

这样就可以将系统java安装为jdk8了，可以利用 java -version 来查看java版本



### 然后开始进行安装systemc

​	a. 先建立dol文件夹，然后将dol_ethz.zip和systemc-2.3.1.tgz解压进去

```
unzip dol_ethz.zip -d dol
tar -zxvf systemc-2.3.1.tgz
```

 ![WechatIMG6](/Users/shiyunlin/Desktop/Compulsary Courses/嵌入式/LAB01/image/WechatIMG6.jpeg)

 ![WechatIMG7](/Users/shiyunlin/Desktop/Compulsary Courses/嵌入式/LAB01/image/WechatIMG7.jpeg)



​	b. 编译systems，解压后进入目录并且建立并进入objdir文件夹然后运行configure,接下来编译

``` 
cd systems-2.3.1
mkdir objdir
cd objdir
../configure CXX=g++ --diable-async-updates
sudo make install all
```

​	可以看到如下结果：

![WechatIMG9](/Users/shiyunlin/Desktop/Compulsary Courses/嵌入式/LAB01/image/WechatIMG9.jpeg)

![WechatIMG10](/Users/shiyunlin/Desktop/Compulsary Courses/嵌入式/LAB01/image/WechatIMG10.jpeg)



### 编译dol

​	进入dol文件夹，修改build_zip.xml文件中的路径，将路径改为刚刚编译的systemc的路径（yyy为路径）

```
<property name="systemc.inc" value="YYY/include"/>
<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
```

​	然后编译xml文件，build sucessful之后可以试着编译第一个例子

```
ant -f build_zip.xml all
cd build/bin/main
ant -f runexample.xml -Dnumber=1
```

​	成功的标志为：

![WechatIMG14](/Users/shiyunlin/Desktop/Compulsary Courses/嵌入式/LAB01/image/WechatIMG14.jpeg)

![WechatIMG15](/Users/shiyunlin/Desktop/Compulsary Courses/嵌入式/LAB01/image/WechatIMG15.jpeg)



### 	以上，完成了dol的环境配置



## EXPERIENCE

​	本次试验遇到最大的问题就是配置java环境的时候，出现了我不能理解的错误。利用apt-get直接安装成功了点jdk7为什么不能编译成功呢？所谓的“搭建了多个版本的java”这个是不成立的。重新安装了一个全新的Linux系统之后我重复了同样的安装行为，确保在安装jdk7之前系统内没有任何的java版本，即使这样最后一次还是build fail???

​	





