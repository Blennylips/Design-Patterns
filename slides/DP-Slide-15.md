# Coda: (_python_) Decorators

## How can I make a decorator in Python that would do the following.

    !python
    @makebold
    @makeitalic
    def say():
       return "Hello"
    

    <b><i>Hello</i></b>

Do not do this at home!

    !python
    def makebold(fn):
        def wrapped():
            return "<b>" + fn() + "</b>"
        return wrapped
    
    def makeitalic(fn):
        def wrapped():
            return "<i>" + fn() + "</i>"
        return wrapped
    
    @makebold
    @makeitalic
    def hello():
        return "hello world"
    
    print hello()

.notes: A decorator is a function that expects ANOTHER function as parameter
