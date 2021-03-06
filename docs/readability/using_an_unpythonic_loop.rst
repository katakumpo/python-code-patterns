Using an unpythonic loop
========================

Summary
-------

Instead of counting over an index and retrieving the corresponding index 
element within the for loop, you should use enumerate to retrieve the 
index and list element simultaneously.

Description
-----------

`PEP 20 <http://legacy.python.org/dev/peps/pep-0020/>`_ states "There should be one-- and preferably only one --obvious way to do it." Creating a loop that uses an incrementing index to access each element of a list within the loop construct is not the preferred style for accessing each element in a list. The preferred style is to use ``enumerate()`` to simultaneously retrieve the index and list element. 

Examples
----------

Loop defines index and accesses each list element with index
............................................................

The module below uses an index variable ``i`` in a ``for`` loop to iterate through the elements of a list. This is not the preferred style for iterating through a list in Python.

.. warning:: The code below is an example of an error. Using this code will create bugs in your programs!

.. code:: python

    l = [1,2,3]

    for i in range(0,len(list)):  # creating index variable
        le = l[i]  # using index to access list
        print i,le

Solutions
---------

Retrieve index and element when defining loop
.............................................

The updated module below demonstrates the Pythonic style for iterating through a list. When you define two variables in a ``for`` loop in conjunction with a call to ``enumerate()`` on a list, Python automatically assigns the first variable as an index variable, and the second variable as the corresponding list element value for that index location in the list.

.. code:: python

    for i, le in enumerate(l):
        print i, le
    
References
----------
- `PEP 20 - The Zen of Python <http://legacy.python.org/dev/peps/pep-0020/>`_
