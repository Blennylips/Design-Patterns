# Data Through Signals

Additional keyword arguments can be passed to send(). 
These will in turn be passed to the connected functions:

    !python
    >>> send_data = signal('send-data')
    >>> @send_data.connect
    ... def receive_data(sender, **kw):
    ...     print("Caught signal sent by %r, data %r" % (sender, kw))
    ...     return 'received!'
    ...
    >>> result = send_data.send('anonymous', abc=123)
    Caught signal sent by 'anonymous', data {'abc': 123}
    >>> result
    [(<function receive_data at 0x...>, 'received!')]


The return value of send() collects the return values of each connected function as a list of (receiver function, return value) pairs:
