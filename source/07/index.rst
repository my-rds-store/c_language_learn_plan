###############
第七章 工程管理
###############

************************************************************************************************************
`automake 官方手册 <https://www.gnu.org/software/automake/manual/automake.html#Introduction>`_
************************************************************************************************************

* `A Small Hello World <https://www.gnu.org/software/automake/manual/automake.html#Hello-World>`_
* `使用autotools生成Makefile学习笔记 <https://geesun.github.io/posts/2015/02/autotool.html>`_


************************
7.1  Hello World
************************

* 参考
    * `例解 autoconf 和 automake 生成 Makefile 文件 <https://www.ibm.com/developerworks/cn/linux/l-makefile/>`_
    * `Autotools常见的工具包autoconf、automake、libtool 介绍 <https://www.zhihu.com/question/22644913>`_
    * `autoconf与automake加入新的编译选项 <https://segmentfault.com/a/1190000012798205>`_


1) 目录结构
====================

:: 

  hellowrold/
           |--- Makefile.am
           |
           |--- src/
                 |
                 |--- Makefile.am
                 |--- main.c


2)  `helloworld/main.c`
========================================

.. literalinclude:: ../../code/7/1/helloworld/src/main.c
    :language: c
    :encoding: utf-8

3) 创建Makefile模板 
========================================

**Makefile.am**

.. literalinclude:: ../../code/7/1/helloworld/Makefile.am
    :encoding: utf-8

**src/Makefile.am**

.. literalinclude:: ../../code/7/1/helloworld/src/Makefile.am
    :encoding: utf-8


4) 创建autoconf的模板
========================================

.. code-block:: bash

    $ auttoscan

在helloworld下运行 **auttoscan** 生成文件 configure.scan, 

.. literalinclude:: ../../code/7/1/helloworld/configure.scan
    :encoding: utf-8

改名为 `configure.ac`

.. code-block:: bash

    $ mv configure.scan  configure.scan

修改 `configure.ac`

.. literalinclude:: ../../code/7/1/helloworld/configure.ac
    :encoding: utf-8
    :emphasize-lines: 5, 8

configure.ac 是由一系列的宏组成,这些宏最终有命令m4展开，得到一个脚本文件 **configure** ,
**configure** 的主要功能都是探测系统配置，然后根据这些配置来生成相应的Makefile文件.
比如 **AC_PROG_CC** 是用来检测编译器的. 
**AC_CONFIG_FILES** 和 **AC_OUTPUT** 是用来产生Makefile和其他数据文件的.


5) 生成configure脚本
========================================

.. code-block:: bash

    $ touch README
    $ autoreconf --install


6) 生成最终的Makefile
=====================================

.. code-block:: bash

   $ ./configure

configure 有以下两个常用的参数。


    ::

        --prefix : 用来制定安装目录，linux默认安装目录是 /usr/local

        --host   : 用于交叉编译，比如x86的PC机上编译在ARM板上运行的程序.

        eg:
            ./configure --prefix=/home/jxm/work/arm-root/usr/ --host=arm-linux


7) 编译,安装
=====================================

.. code-block:: bash

    $ make -j4 && make install 

************
7.2  函数库
************

:: 

    └── base
        ├── AUTHORS
        ├── ChangeLog
        ├── Makefile.am
        ├── NEWS
        ├── README
        ├── autogen.sh
        ├── base.pc.in
        ├── configure.ac
        └── src
            ├── Makefile.am
            ├── darray.c
            ├── darray.h
            ├── darray_iterator.c
            ├── darray_iterator.h
            ├── dlist.c
            ├── dlist.h
            ├── dlist_iterator.c
            ├── dlist_iterator.h
            ├── hash_table.c
            ├── hash_table.h
            ├── invert.c
            ├── invert_ng.c
            ├── iterator.h
            ├── linear_container.h
            ├── linear_container_darray.c
            ├── linear_container_darray.h
            ├── linear_container_dlist.c
            ├── linear_container_dlist.h
            ├── linear_container_test.c
            ├── queue.c
            ├── queue.h
            ├── sort.c
            ├── sort.h
            ├── stack.c
            ├── stack.h
            ├── test_helper.c
            └── typedef.h


**Makefile.am**

.. literalinclude:: ../../code/7/2/base/Makefile.am
    :encoding: utf-8

**src/Makefile.am**

.. literalinclude:: ../../code/7/2/base/src/Makefile.am
    :encoding: utf-8

**base.pc.in**

.. literalinclude:: ../../code/7/2/base/base.pc.in
    :encoding: utf-8
 
**configure.ac**

.. literalinclude:: ../../code/7/2/base/configure.ac
    :encoding: utf-8

.. code-block:: sh
    
    # autogen
    autoreconf --install

    # build
    ./configure --prefix=/tmp/usr 
    make && make install 
 
    # show info
    # apt-get install -y pkg-config
    export PKG_CONFIG_PATH=/tmp/usr/
    pkg-config --list-all
    pkg-config --cflags --libs base

************************
7.3  应用程序
************************

