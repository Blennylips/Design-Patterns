# Weak References continued

Weak references have no effect on the reference count for an object

    !python
    import weakref
    >>> a = Foo()
    created
    >>> b = weakref.ref(a) # temp strong ref created by calling weak ref
    >>> a == b()
    True
    >>> b().show()
    None
    >>> del a
    destroyed
    >>> b() is None
    True
