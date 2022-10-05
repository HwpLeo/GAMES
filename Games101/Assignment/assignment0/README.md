# 作业0-环境搭建

课程给的方案是使用虚拟机。这里记录下在Windows10配置VSCode、MinGW、CMake、Eigen、OpenCV环境。

## 安装VSCode

## 安装MinGW
下载带-posix的免安装版本(不带posix的版本会在编译OpenCV时出现mutex错误)
https://sourceforge.net/projects/mingw-w64/files/


## 安装CMake

## 安装eigen

官网下载eigen源文件，使用cmake生成一个MinGW工程。
在build目录下使用管理员权限执行make，再执行make install
windows下切换目录：
```
cd /d d:
```

添加系统环境变量，变量名为`EIGEN3_INCLUDE_DIR`, 变狼值为`C:\Program Files (x86)\Eigen3\include`

## 安装OpenCV

从sourceforge下载OpenCV。双击打开之后提示一个解压过程。解压完成后和eigen一样的操作。
在configure执行完成后，取消勾选OPENCV_ENABLE_ALLOCATOR_STATS。再次点击configure。


最后还需要修改CMakeLists文件：
```
include_directories("C:/Program Files (x86)/Eigen3/include")
```