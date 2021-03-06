Getting Started
===============

Supported Platforms
-------------------

LSQUIC compiles and runs on Linux, FreeBSD, and Mac OS.  It has been
tested on i386, x86_64, as well as Raspberry Pi.

Windows support is on the TODO list.

Dependencies
------------

LSQUIC library uses:

- zlib_;
- BoringSSL_; and
- `ls-qpack`_ (as a Git submodule).

The accompanying demo command-line tools use libevent_.

What's in the box
-----------------

- ``src/liblsquic`` -- the library
- ``test`` -- demo client and server programs
- ``test/unittests`` -- unit tests

Building
--------

To build the library, follow instructions in the README_ file.

Demo Examples
-------------

Fetch Google home page:

::

    ./http_client -s www.google.com -p / -o version=Q050

Run your own server (it does not touch the filesystem, don't worry):

::

    ./http_server -c www.example.com,fullchain.pem,privkey.pem -s 0.0.0.0:4433

Grab a page from your server:

::

    ./http_client -H www.example.com -s 127.0.0.1:4433 -p /

You can play with various options, of which there are many.  Use
the ``-h`` command-line flag to see them.

Next steps
----------

If you want to use LSQUIC in your program, check out the :doc:`tutorial` and
the :doc:`apiref`.

:doc:`internals` covers some library internals.

.. _zlib: https://www.zlib.net/
.. _BoringSSL: https://boringssl.googlesource.com/boringssl/
.. _`ls-qpack`: https://github.com/litespeedtech/ls-qpack
.. _libevent: https://libevent.org/
.. _README: https://github.com/litespeedtech/lsquic/blob/master/README.md
