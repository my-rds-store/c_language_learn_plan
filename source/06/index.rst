####################
第六章 算法和容器   
####################

6.1 容器  
==========

1) typedef.h  
---------------

.. literalinclude:: ../../code/6/1/linear_container/typedef.h
    :language: c
    :encoding: utf-8

2) darray
-------------

.. literalinclude:: ../../code/6/1/linear_container/darray.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/1/linear_container/darray.c
    :language: c
    :encoding: utf-8

.. code-block:: sh

   gcc -Wall -Wno-unused-function -g -m32 -DDARRAY_TEST darray.c -o darray_test

3) dlist  
----------------------


.. literalinclude:: ../../code/6/1/linear_container/dlist.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/1/linear_container/dlist.c
    :language: c
    :encoding: utf-8

.. code-block:: sh

    gcc -Wall -Wno-unused-function -g -m32 -DDLIST_TEST dlist.c -o dlist_test


4) linear_container_dlist
----------------------------


.. literalinclude:: ../../code/6/1/linear_container/linear_container.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/1/linear_container/linear_container_dlist.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/1/linear_container/linear_container_dlist.c
    :language: c
    :encoding: utf-8

5) queue
------------

.. literalinclude:: ../../code/6/1/linear_container/queue.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/1/linear_container/queue.c
    :language: c
    :encoding: utf-8

.. code-block:: sh
 
    gcc -Wall -Wno-unused-function -g -m32 -DQUEUE_TEST dlist.c linear_container_dlist.c  queue.c -o queue_test


6) linear_container_darray
----------------------------

.. literalinclude:: ../../code/6/1/linear_container/linear_container_darray.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/1/linear_container/linear_container_darray.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/1/linear_container/linear_container_test.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/1/linear_container/Makefile
    :language: Makefile
    :encoding: utf-8

6.2 迭代器  
====================

.. literalinclude:: ../../code/6/2/iterator/invert_ng.c
    :language: c
    :encoding: utf-8


.. literalinclude:: ../../code/6/2/iterator/iterator.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/2/iterator/dlist_iterator.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/2/iterator/dlist_iterator.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/2/iterator/darray_iterator.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/2/iterator/darray_iterator.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/2/iterator/invert.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/2/iterator/Makefile
    :language: Makefile
    :encoding: utf-8

6.3 动态绑定  
=============

.. literalinclude:: ../../code/6/3/runtime/call_cos.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/3/runtime/module.h
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/3/runtime/module_linux.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/3/runtime/module_test.c
    :language: c
    :encoding: utf-8

.. literalinclude:: ../../code/6/3/runtime/Makefile
    :language: Makefile
    :encoding: utf-8







