# CMake

## 介绍

CMake是一个跨平台的开源编译器.
完整文档请访问`[CMake Home Page](https://cmake.org)`,`[CMake Documentation Page](https://cmake.org/documentation)`和`[CMake Community Wiki](https://gitlab.kitware.com/cmake/community/wikis/home)`.

CMake由`[Kitware](http://www.kitware.com/cmake)`护和支持,并与社区成员合作开发.

## License

CMake根据OSI批准的BSD 3条款许可发布.
有关详细信息，请参见`[Copyright.txt](Copyright.txt)`.

## 编译CMake

支持的系统
-------------------

* Microsoft Windows
* Apple macOS
* Linux
* FreeBSD
* OpenBSD
* Solaris
* AIX

其他类UNIX的操作系统也可以使用,如果不能的话,移植CMake到这些平台上也不是什么问题.
请发布到“[CMake Discourse Forum](https://discourse.cmake.org)”,询问其他人是否有关于该平台的经验.

## 从零开始构建CMake

### UNIX/Mac OSX/MinGW/MSYS/Cygwin

再从CMake的源目录中找到的`bootstrap`脚本.
您可以使用--help选项查看受支持的选项.
您可以使用`--prefix = <install_prefix>`将其安装至自定义的CMake的安装目录,完成之后请运行`make`和`make install`.

例如,如果您只想从源代码编译和安装CMake，
您可以直接在源代码树中构建：

```
  $ ./bootstrap && make && sudo make install
```

或者,如果您打算开发CMake或以其他方式运行测试套件(test suite),请创建一个单独的构建树(build tree):

```
  $ mkdir cmake-build && cd cmake-build
  $ ../cmake-source/bootstrap && make
```

### Windows

在Windows下构建CMake的方法有两种:

1.使用`Visual Studio 2015`或更高版本的MSVC进行编译.
   您需要下载并安装CMake的二进制版本,
   你可以得到它们自`[CMake Download Page](https://cmake.org/download)`,
   然后使用CMake构建CMake.

2.在`[MSYS2](https://www.msys2.org/)`下使用`MinGW`进行构建.
   下载并安装`MSYS2`。然后安装所需的构建工具:
    
   ```
     $ pacman -S --needed git base-devel mingw-w64-x86_64-gcc
   ```

   和上面的引导程序.
   
### 用CMake编译CMake

???

#### 用CMake编译CMake编译CMake
##### 用CMake编译CMake编译CMake编译CMake

......

您可以使用基于CMake的构建系统来构建CMake,就像其他任何项目一样:
使用首选的选项和生成器在此CMake的源上运行已安装的CMake.然后编译并安装.

要获取帮助文档,请安装`[Sphinx](http://sphinx-doc.org)`,
并使用`-DSPHINX_HTML=ON`和/或`-DSPHINX_MAN=ON`配置CMake以启用`html`或`man`构建器,
如果未自动找到工具,则添加`-DSPHINX_EXECUTABLE=/path/to/sphinx-build`.

Reporting Bugs
==============

1.如果您有补丁(patch),请阅读`CONTRIBUTING.rst`.

2.否则,请发布到`CMake Discourse Forum`并对比预期和观察到的行为,以确定它是否确实是个bug.

3.最后,如果上述步骤未能解决问题，请打开`[CMake问题追踪器](https://gitlab.kitware.com/cmake/cmake/issues)`

## 参与项目

请参考`[CONTRIBUTING.rst](CONTRIBUTING.rst)`.
