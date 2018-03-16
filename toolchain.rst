Setting up a Toolchain
======================

In a regular cross-compiling setup, we'd only have one compiler: the
cross-compiler itself. We would compile and link with cross-compiler on the
build machine, and we'd have an executable that runs on the host. Unfortunately, Python is a little more complicated: Python has to run to complete the build.

To get around this, we build Python twice. Once for the build machine
(build-Python), and again for the host machine (host-Python). During
host-Python's build, we use build-Python as a stand-in when we need a Python
interpreter. Although this may sound complicated, Python's own build system can
handle this case without much effort on our part. Because of this double build,
we need toolchains for the build machine and the host machine.

The build toolchain
-------------------

This toolchain is easy: You can use whatever version of gcc came with your
operating system. It's rare that you would need to modify anything here. Do
make sure that you have the necessary `dependencies`_ installed to build
Python. Beyond the compiler, you will want ``zlib`` and ``openssl`` development
libraries installed for pip to work. Most of the time, there's no need to
install dependencies for most extra modules, as build-Python's only job will
be cross-compiling.

.. _dependencies: https://devguide.python.org/setup/#build-dependencies

The host toolchain
------------------

If you can, download a pre-built toolchain for your host. Building your own
cross-compiler is beyond the scope of this guide. Also remember that a
toolchain is more than just a compiler. It is also the header files and
libraries you will need to build. (The more pre-built libraries your toolchain
comes with, the easier this process will be.) You will want a toolchain with
``zlib`` installed, but ``openssl`` is optional, depending on what you need
host-Python to do.

Some common pre-built toolchains:

*   Android NDK
*   Linaro
*   Raspberry Pi

.. topic:: Case Study: Python on Android

    In this case study...
