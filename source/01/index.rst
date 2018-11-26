############################
第一章 从双向链表学习设计   
############################


1.3 Wirte once, run anywhere (WORA)  
=====================================


* 让C++可以调用


.. code-block:: c 

    # ifdef __cplusplus
    extern "C" {
    #endif 
    
    //.....
    
    # ifdef __cplusplus
    }
    #endif 

1.4 拥抱变化  
===============


.. literalinclude:: ../../code/1/4/embrace_change/dlist.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/1/4/embrace_change/dlist.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/1/4/embrace_change/main.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/1/4/embrace_change/Makefile
    :language: Makefile
    :encoding: utf-8


1.5 Don't Repeat Yourself(DRY)  
==============================

需求描述
------------

* 对一个存放整数的的双向链表，找出链表中的最大值.
* 对一个存放整数的的双向链表，累加链表中的所有整数.

.. literalinclude:: ../../code/1/5/dry/dlist.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/1/5/dry/dlist.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/1/5/dry/main.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/1/5/dry/Makefile
    :language: Makefile
    :encoding: utf-8


1.6 你的数据放在哪里  
==============================

需求描述
------------

对一个存放字符串的双向链表,把存放在其中的字符串转换成大写字母.

----

.. literalinclude:: ../../code/1/6/data_store/dlist_toupper.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/1/6/data_store/bss.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/1/6/data_store/data.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/1/6/data_store/heap_error.c
    :language: c
    :encoding: utf-8


.. literalinclude:: ../../code/1/6/data_store/Makefile
    :language: makefile
    :encoding: utf-8



