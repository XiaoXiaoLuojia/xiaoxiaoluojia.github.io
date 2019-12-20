---
layout: post
title:  "Ubuntu配置opencv+opencv_contrib"
date:   2019-10-13
categories: 安装记录
tag: Ubuntu
---

* content
{:toc}


## opencv + opencv_contrib

* 安装依赖项

```
sudo apt-get install build-essential  
  
sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev  
  
sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev  

sudo apt-get install build-essential qt5-default ccache libv4l-dev libavresample-dev  libgphoto2-dev libopenblas-base libopenblas-dev doxygen  openjdk-8-jdk pylint libvtk6-dev

sudo apt-get install pkg-config
```

* 官网下载源码

opencv
--https://github.com/opencv/opencv/releases

opencv_contrib
--https://github.com/opencv/opencv_contrib/releases 

下载需要的版本

解压两个压缩包，然后将 opencv_contrib 放到 opencv X.X.X 里面，双击进入解压出来的opencv X.X.X文件夹，打开终端，创建build文件夹，cmake
```
mkdir build
cd build 
cmake ..
```


* cmake

```
cmake -D CMAKE_INSTALL_PREFIX=/usr/local -D CMAKE_BUILD_TYPE=Release -D OPENCV_EXTRA_MODULES_PATH=YOUR-PATH/opencv_contrib/modules -D OPENCV_ENABLE_NONFREE:BOOL=ON ..
```

* make

```
make -j8
sudo make install 
```

两篇由于提前安装anaconda3，结果make报错的解决方法（但是试过好像没有解决问题）

[Makefile:160: recipe for target 'all' failed(ubuntu16.04+opencv3.4+gcc5.4.0)](https://blog.csdn.net/ZT0518/article/details/83445308)

[Makefile:160: recipe for target 'all' failed（Ubuntu 16.06 + Opencv3.2）解决办法](https://blog.csdn.net/Zafir_410/article/details/74357544)


