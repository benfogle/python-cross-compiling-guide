.. The Python Cross-Compiling Guide documentation master file, created by
   sphinx-quickstart on Mon Mar  5 23:01:32 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

The Python Cross-Compiling Guide
================================

This guide is an in-depth look at porting Python apps to embedded systems.  It
covers cross compiling Python itself, any extension modules you might need, and
options for deploying the final bundle to your device.

Who is this guide for?
----------------------

This guide is for developers who:

* Need to port a Python app to an embedded system
* Want to make wheels for non-x86 architectures
* Want to test their extension modules on non-x86 architectures.

You should be familiar with Python, compiling C code in general, and with at
least the *idea* of cross compiling. While I'm trying to make this as
accessible as possible, cross-compiling is an advanced topic and this is not
meant to be an introductory text.

Format and scope
----------------

This guide is presented as a series of topics, more-or-less in the order you'll
need to do them in. Alongside each step is a case study (Android) to provide
concrete examples.

This guide covers the case where both the build and host platforms are
Unix-like. Windows, as either a host or build platform, is not supported.

We also strongly recommend Python 3.5 or greater. As covered in
:ref:`prerequisites`, a lot of work as gone into recent versions of Python to
make cross-compiling easier, and may actually be less work to upgrade your
codebase than to patch an old version of Python.

The Guide
=========

.. toctree::
   :maxdepth: 2

   vocabulary
   toolchain
   prerequisites
   building_build_python
   building_host_python
   packages
   deploying

Case Studies
============

.. toctree::
   :maxdepth: 2

   case_study_android

Indices and tables
==================

* :ref:`genindex`
* :ref:`search`

