#############################
第二章 写的又好又快的秘诀    
#############################


2.3 避免常见错误 
=================

* strcpy , strcat, sprintf, 与 strncpy , strncat, snprintf,

* sizeoff

* valotile

* intptr_t, uintptr_t


    这两个数据类型的定义,位于 `/usr/include/stdint.h` 文件中，这个文件是在 `C99` 中新增加的文件，
    `/usr/include/inttypes.h`  C99 新增加的文件，在这个文件中有 `#include<stdint.h>` ,

    因此，使用时，既可以
    
    .. code-block:: c

        #include <stdint.h>

    又可以　

    .. code-block:: c

        #include <inttypes.h>

    在 `/usr/include/stdint.h`  中定义:

    .. code-block:: c

        /* Types for `void *' pointers.  */
        #if __WORDSIZE == 64
        # ifndef __intptr_t_defined
        typedef long int		intptr_t;
        #  define __intptr_t_defined
        # endif
        typedef unsigned long int	uintptr_t;
        #else
        # ifndef __intptr_t_defined
        typedef int			intptr_t;
        #  define __intptr_t_defined
        # endif
        typedef unsigned int		uintptr_t;
        #endif

    1. 提高程序的可移植性（在32位和64位的机器上).

    2. 定义这两个数据类型别名也是为了 `void *` 指针. 在C语言中，任何类型的指针都可以转换为 `void *` 类型，并且在将它转换回原来的类型时不会丢失信息。



2.4 自动测试 
===============


.. literalinclude:: ../../code/2/4/autotest/dlist.h
    :language: c
    :encoding: utf-8


.. literalinclude:: ../../code/2/4/autotest/dlist.c
    :language: c
    :encoding: utf-8


.. literalinclude:: ../../code/2/4/autotest/Makefile
    :language: Makefile
    :encoding: utf-8


