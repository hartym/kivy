.. _other_frameworks:

Integrating with other Frameworks
=================================

.. versionadded:: 1.0.8

Using Twisted inside Kivy
-------------------------

.. note::
    You can use the `kivy.support.install_twisted_reactor` function to
    install a twisted reactor that will run inside the kivy event loop.

    Any arguments or keyword arguments passed to this function will be
    passed on the the threadedselect reactors interleave function, these
    are the arguments one would usually pass to twisted's reactor.startRunning

.. warning::
    Unlike the default twisted reactor, the installed reactor will not handle
    any signals unnless you set the 'installSignalHandlers' keyword argument
    to 1 explicitly.  This is done to allow kivy to handle teh signals as
    usual, unless you specifically want the twisted reactor to handle the
    signals (e.g. SIGINT).



The kivy examples include a small example for a twisted server and client.
The server app has a simple twisted server running and log any messages.
The client app can send messages to teh server and will print its message
and the repsonse it got. The examples are based mostly on simple Echo example
from the twisted docs, which you can find here:
- http://twistedmatrix.com/documents/current/core/examples/simpleserv.py
- http://twistedmatrix.com/documents/current/core/examples/simpleclient.py

To try the example run echo_server_app.py first, and then launch
echo_client_app.py.  The server will, reply with simple echo messages to
anything the client app sends, when you hit enter after typing something
in the textbox.

Server App
~~~~~~~~~~

.. include:: ../../../examples/frameworks/twisted/echo_server_app.py
   :literal:

Client App
~~~~~~~~~~

.. include:: ../../../examples/frameworks/twisted/echo_client_app.py
   :literal:

