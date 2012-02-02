# Coda the 2nd: Weak References

Strong references are pointers to objects that have an effect on their reference counts

    !python
    >>> a = [1,2,3]
    >>> b = a
    >>> # lots of operations involving a & b
    >>> del a ; del b

When is a destoyed?

    !python
    >>> class Foo(object):
         def __init__(self):
           self.obj = None
           print 'created'  

         def __del__(self):
             print 'destroyed'

         def show(self):
             print self.obj

         def store(self, obj):
             self.obj = obj
    >>> a = Foo()
    created
    >>> b = a
    >>> del a
    >>> del b
    destroyed