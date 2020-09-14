---
title: "Windows10配置libtorch C++库"
layout: post
date: 2020-01-12 15:42
image: /assets/images/libtorch/title.png
headerImage: true
tag:
- others
category: blog
author: Buzhen Huang
excerpt: libtorch
description: libtorch
---

**<font face="微软雅黑">本文为博主原创文章，转载请注明出处。</font>**

本文记录了libtorch的配置过程，方便之后再次安装。
## 一、下载
在官网选择合适的版本下载。这里选择了使用CUDA10.1的release版。
```https://download.pytorch.org/libtorch/cu101/libtorch-win-shared-with-deps-1.6.0%2Bcu101.zip```
<div  align="center"> 
<img src="/assets/images/libtorch/download.png" width = "500" height = "120"/>
</div>

## 二、配置
#### 创建CMakeLists.txt
libtorch的下载文件中没自带cmakelists。因此我们需要在解压后文件夹中新建一个```CMakeLists.txt```并添加一下内容。

    # 设置 cmake 版本限制
    cmake_minimum_required(VERSION 3.0 FATAL_ERROR)
    cmake_policy(SET CMP0054 OLD) #避免错误警告
    # 项目名称
    project(libtorch-app)

    # 设置 libtorch-win-shared-with-deps-latest 目录,主要让 find_package 可以找到 Torch 的 TorchConfig.cmake 配置文件以及其他相关 Config.cmake 配置文件

    set(CMAKE_PREFIX_PATH "./libtorch-win-shared-with-deps-1.6.0+cu101")
    set(Torch_DIR "./libtorch-win-shared-with-deps-1.6.0+cu101/libtorch/share/cmake/Torch")
    find_package(Torch REQUIRED)

    add_executable(libtorch-app main.cpp)
    target_link_libraries(libtorch-app "${TORCH_LIBRARIES}")
    set_property(TARGET libtorch-app PROPERTY CXX_STANDARD 11)

#### 创建cpp
在```CMakeLists.txt```的同级目录中创建```main.cpp```

    #include <torch/torch.h>
    #include <iostream>
    int main()
    {
        torch::Tensor tensor = torch::rand({ 9,9 });
        std::cout << tensor << std::endl;
        return 0;
    }

#### 编译
使用cmake将source文件夹选择为```CMakeLists.txt```所在的文件夹。另自行选取输出的```build```文件夹。
<div  align="center"> 
<img src="/assets/images/libtorch/compile.png" width = "450" height = "250"/>
</div>

打开```build```文件夹中的```libtorch-app.sln```进行编译。

## 三、测试
我习惯于将有关文件单独放在第三方库中。所以我将解压文件夹中的```bin/include/lib```三个文件夹单独拿出来。
<div  align="center"> 
<img src="/assets/images/libtorch/test1.png" width = "180" height = "130"/>
</div>

我们将```bin```文件夹的路径添加进环境变量。然后我们新建一个空项目，选择release，x64。将```include```和```lib```文件夹的路径分别加入到包含目录和库目录。
<div  align="center"> 
<img src="/assets/images/libtorch/test2.png" width = "400" height = "280"/>
</div>

然后新建一个cpp添加：

    #include <torch/torch.h>
    #include <iostream>

    #ifdef _DEBUG
    #pragma comment(lib, "c10.lib")
    #pragma comment(lib, "torch_cpu.lib")
    #pragma comment(lib, "torch_cuda.lib")
    #else
    #pragma comment(lib, "c10.lib")
    #pragma comment(lib, "torch_cpu.lib")
    #pragma comment(lib, "torch_cuda.lib")
    #endif // _DEBUG

    int main()
    {
        torch::Tensor tensor = torch::rand({ 9,9 });
        std::cout << tensor << std::endl;
        return 0;
    }

正常输出
<div  align="center"> 
<img src="/assets/images/libtorch/test3.png" width = "500" height = "120"/>
</div>

## References
\[1\] 學海無涯：https://www.cnblogs.com/cheungxiongwei/p/10689483.html<br>

---
