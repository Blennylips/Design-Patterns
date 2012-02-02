# Language Dependencies in Patterns 

* DPs are not independent from language choice: "if", "while", etc are patterns in assembly
* Design and implementation must interact
* (many) DPs for Java/C++ are "workarounds for static typing"
* Pythonic patterns are minus the WfST and take advantage of python's strengths

<br>

    !python
    >>> import this
    The Zen of Python, by Tim Peters
    
    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    ...
    
    >>> if curious: import antigravity
    
	>>> from __future__ import braces
    File "<stdin>", line 1
    SyntaxError: not a chance

.notes: DP's best in design, less in impl