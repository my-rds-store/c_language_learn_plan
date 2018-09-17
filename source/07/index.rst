###############
第七章 工程管理
###############


7.1  Hello World
================

目录结构
--------

:: 

  hellowrold/
           |--- Makefile.am
           |
           |--- src/
                 |
                 |--- Makefile.am
                 |--- main.c


创建源文件mian.c
-----------------

`helloworld/main.c`

.. literalinclude:: ../../code/helloworld/src/main.c
    :language: c
    :encoding: utf-8


创建Makefile模板 
------------------

`helloworld/Makefile.am`

.. literalinclude:: ../../code/helloworld/Makefile.am
    :encoding: utf-8

src表示一个子目录，如果有多个子目录，用空格分开。
 

`helloworld/src/Makefile.am`

.. literalinclude:: ../../code/helloworld/src/Makefile.am
    :encoding: utf-8

PROGRAMS表示要产生的可执行文件,有多个可执行文件用空格分开，
而bin表示可执行文件的安装路径。
SOURCE表示生成可执行文件需要的源文件,有多个源文件用空格分开。

创建autoconf的模板
------------------

.. code-block:: bash

    $ auttoscan


在helloworld下运行 **auttoscan** 生成文件 configure.scan, 
改名为 configure.ac


.. literalinclude:: ../../code/helloworld/configure.scan
    :encoding: utf-8


并做修改

.. literalinclude:: ../../code/helloworld/configure.ac
    :encoding: utf-8
    :emphasize-lines: 5, 8

configure.ac 是由一系列的宏组成,这些宏最终有命令m4展开，得到一个脚本文件 **configure** ,
**configure** 的主要功能都是探测系统配置，然后根据这些配置来生成相应的Makefile文件.
比如 **AC_PROG_CC** 是用来检测编译器的. 
**AC_CONFIG_FILES** 和 **AC_OUTPUT** 是用来产生Makefile和其他数据文件的.


复制所用到的宏
--------------

.. code-block:: bash

    $ aclocal


AC_PROG_CC 之类的宏是标准的的宏(或者说是内置的宏),不需要我们自己去写它，但我们需要
通过 **aclocal** 把configure.ac 中所有的宏全部复制到我们的工程里来。在helloworld目录下
运行 **aclocal** 之后,当前目录下出现了以下内容.

* autom4te.cache : 临时目录，只是用来加速宏展开
* aclocal.m4     : 这是configure.ac中用到的宏的定义，有兴趣的读者可以看看。


生成配置头文件模块
------------------

.. code-block:: bash

 $ autoheader


配置文件(config.h)是用来定义在 C/C++ 程序中可以引用到的宏，像模块名称和版本号等等.
这些宏由configure脚本产生，但我们要提供一个模板文件。
这个模板文件可以用命令autoheader产生出来。
在helloworld目录下运行autoheader之后,当前目录下产生config.h.in, 一般情况下不去修改它.


创建几个必要的文件
------------------

* README : 描述模块的功能、用法和注意事项
* NEWS   : 描述模块最新的动态
* AUTHORS: 模块的作者及联系方式
* ChangeLog : 记录模块的修改历史，他有固定的格式。

    * 1) 最新修改放在最上面。
    * 2）对于每一条记录，第一行写日期，修改者和联系方式。第二行开始以tab开头(缩进),再加一个星号，后面再写修改的原因和位置等。如

     ::

        2009-03-29 Li XianJing
            * Created

生成Makefile.in和所需要的脚本
-----------------------------

.. code-block:: bash

    $ automake -a   
    # or
    $ automake --add-missing

这个命令会建立 COPYING depcomp INSTALL install-sh missing 几个文件的链接，这些文件指向系统中的文件。

automake 最重要的功能是以Makefile.am 为模板产生Makefile.in文件,Makefile.in相对于Makefile.am要复杂很多倍了,所幸的是我们不需要了解它。

生成configure脚本
-----------------

.. code-block:: bash

    $ autoconf
    
autoconf的功能是调用m4展开configure.ac中的宏,生成configure脚本,这个脚本是最终执行的脚本.

生成最终的Makefile
------------------

.. code-block:: bash

   $ ./configure

configure 有以下两个常用的参数。

* ---prefix :  用来制定安装目录，linux默认安装目录是 `/usr/local`

* ---host :  用于交叉编译，比如x86的PC机上编译在ARM板上运行的程序.

 ::

    ./configure --prefix=/home/jxm/work/arm-root/usr/ --host=arm-linux


编译
----

.. code-block:: bash

    $ make -j4

安装
----

.. code-block:: bash

   $ make install

7.2  函数库
================

7.3  应用程序
================


