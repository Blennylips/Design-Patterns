# Signals

## Named signals are created with signal():


    !python
    >>> from blinker import signal
    >>> initialized = signal('initialized')
    >>> initialized is signal('initialized')
    True

Every call to signal('name') returns the same signal object (Singleton).
<br><br>
## Subscribing to Signals

### Signal.connect() registers a callback function.


    !python
    >>> def subscriber(sender):
    ...     print("Got a signal sent by %r" % sender)
    ...
    >>> ready = signal('ready')
    >>> ready.connect(subscriber)
