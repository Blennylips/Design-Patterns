# Ha! _No one_ expected _more_ weak refs!

## Cyclic references

A need for weak references arises when objects have strong references forming a cycle:

    !python
    >>> a = Foo() ; b = Foo()
    created
    created
    >>> a.store(b) ; b.store(a)
    >>> del a ; del b
    >>> # Not destroyed!
    class Foo(object): 
        ...
        ...
        def store(self, obj):
            self.obj = weakref.ref(obj)

    >>> a = Foo() ; b = Foo()
    created
    created
    >>> a.store(b) ; b.store(c)
    >>> del a ; del b
    destroyed
    destroyed
