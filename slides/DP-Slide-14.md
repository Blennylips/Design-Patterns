# Optimizing Signal Sending

If the data to be sent down a signal is very expensive, it can be more efficient to check to see if any receivers are connected first by testing the receivers property:

    !python
    >>> bool(signal('ready').receivers)
    True
    >>> bool(signal('complete').receivers)
    False

Checking for a receiver listening for a particular sender is also possible:

    !python
    >>> signal('ready').has_receivers_for(processor_a)
    True