# Emitting Signals

Producers call Signal.send() -> notifiy all receivers

    !python
    >>> class Processor:
    ...    def __init__(self, name):
    ...        self.name = name
    ...
    ...    def go(self):
    ...        ready = signal('ready')
    ...        ready.send(self)
    ...        print("Processing.")
    ...        complete = signal('complete')
    ...        complete.send(self)
    ...
    ...    def __repr__(self):
    ...        return '<Processor %s>' % self.name
    ...
    >>> processor_a = Processor('a')
    >>> processor_a.go()
    Got a signal sent by <Processor a>
    Processing.

Notice the complete signal in go()? 

No receivers have connected to complete yet, and that is ok.