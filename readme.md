#  LAB2实验报告-DOL配置

##DOL（Distributed Operation Layer）
The distributed Operation layer（DOL）is a software Development framework to program parallel applications  based on the Kahn process network model of computation and features a simulation engine based on SystemC.Moreover,the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems,including binding and mapping. 

##安装过程
* 安装必要的环境
> $ sudo apt-get update
$ sudo apt-get install ant
$ sudo apt-get install openjdk-7-jdk
$ sudo apt-get install unzip

* 下载文件（使用VMware虚拟机）.
>$ sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
$ sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip

* 解压文件
 * 新建dol文件夹
> $ mkdir dol
 * 将dolethz.zip解压到dol文件夹中
> $ unzip dol_ethz.zip -d dol
 * 解压Systemc
> $ tar -zxvf systemc-2.3.1.tgz
* 编译Systemc
 * 解压后进入systemc-2.3.1的目录下
> $ cd systemc-2.3.1
 * 新建一个临时文件夹objdir
> $ mkdir objdir
 * 进入该文件下objdir
> $ cd objdir
 * 运行configure
> $ ../configure CXX=g++ --disable-async-updates
 * 编译
> $ sudo make install
   
    ![1.png](http://upload-images.jianshu.io/upload_images/3250630-5a33b54d08584290.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

  * 记录当前工作路径
>$ pwd
* 编译dol
  * 进入刚刚的dol文件夹，修改build.xml文件 
 找到下面这段话，就是说上面编译的systemc位置在哪里
> property name=”systemc.inc” value=”YYY/include” 
property name=”systemc.lib” value=”YYY/lib-Linux/libsystemc.a”/
 * 编译
> $ ant -f build_zip.xml all

   若成功会显示build successful
 ![2.png](http://upload-images.jianshu.io/upload_images/3250630-67ecef1a9ca31bf2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* Run examples
  * 进入build/bin/main路径下
> $ cd build/bin/main
  * 运行第一个例子
> $ ant -f runexample.xml -Dnumber=1

   结果如下：
![3.png](http://upload-images.jianshu.io/upload_images/3250630-bb80705f3fed142f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##实验感想
其实一开始配置的时候一直是下不了，发现是自己的VMware一直连不上网，捣鼓了很久，设置ip，虚拟网络也一直在弄，最后是连自己的电脑的网络都不行了，所幸按照网上的教程弄就好了。其他的步骤按照PPT的讲义很流畅的做下来了，有一些failed基本都是输入错误。
