###########################
第三章 从动态数组学习设计  
###########################


3.1 动态数组与双向链表  
========================

.. literalinclude:: ../../code/3/1/darray/typedef.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/1/darray/darray.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/1/darray/darray.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/1/darray/Makefile
    :language: Makefile
    :encoding: utf-8

3.2 排序  
========================

* 冒泡排序
* 快速排序
    先将元素分成两个区，所有小于某个元素的值在第一个区，其他在第二个区。然后分别对这两个区进行快速排序，直到所分的区只剩下一个元素为止。
* 归并排序
    让左右两部分进行排序，然后把它们合并起来。在排序左右两部分时，同样使用归并排序. 

.. literalinclude:: ../../code/3/2/sort/typedef.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/2/sort/sort.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/2/sort/sort.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/2/sort/Makefile
    :language: Makefile
    :encoding: utf-8

3.3. 有序数组的两个应用   
========================

.. literalinclude:: ../../code/3/3/sort_app/typedef.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/3/sort_app/search.c
    :language: c
    :encoding: utf-8


.. literalinclude:: ../../code/3/3/sort_app/sort.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/3/sort_app/sort.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/3/sort_app/darray.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/3/sort_app/darray.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/3/sort_app/test_helper.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/3/3/sort_app/Makefile
    :language: Makefile
    :encoding: utf-8



