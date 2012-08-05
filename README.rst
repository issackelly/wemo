============
WeMo Hacking
============

I've spent some time reverse engineering my WeMo switch. It's pretty cool and I figured out how to get it to do what I wanted. It's based on UPnP, which I found the miranda
tool to be the best (closest to working with WeMo, and easiest to read)

I had to make some modifications to the miranda package to get it working, and to get it properly reporting the details of the device.

To use, download, cd into the wemo folder and open a python intepreter::

    $ python
    >>> from wemo import on, off, get
    Entering discovery mode for 'upnp:rootdevice', Ctl+C to stop...

    Error updating command completer structure; some command completion features might not work...
    Error updating command completer structure; some command completion features might not work...
    ****************************************************************
    SSDP reply message from 192.168.1.133:49153
    XML file is located at http://192.168.1.133:49153/setup.xml
    Device is running Linux/2.6.21, UPnP/1.0, Portable SDK for UPnP devices/1.6.6
    ****************************************************************

    Discover mode halted...
    >>> get()
    True
    >>> on()
    True
    >>> off()
    True
    >>> get()
    False
    >>> on()
    True
    >>>
