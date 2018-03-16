Vocabulary
==========

Cross-compiling, by definition, involves multiple machines, and keeping them all
straight quickly becomes difficult unless we have a clear vocabulary. In this
guide we follow the conventions used by GNU autotools (and therefore, by Python
itself).

build platform
    The machine doing the building. Also referred to here as the "build
    machine," or occasionally just "Build." This is usually a desktop, laptop,
    or server. Confusingly, some projects refer to this as the "host."

host platform
    The machine running the final product. Also referred to here as the "host
    machine," or just "Host." In other contexts, it may sometimes be referred
    to as the "target." This could be a phone, tablet, Raspberry Pi, or other
    embedded device.

build-Python
    The Python installation that runs on the build platform. It may be the
    version of Python installed globally, but for our purposes, it's typically
    compiled for the purposes of cross-compiling.

host-Python
    The Python installation built to run on the host platform. Note that
    during cross-compiling, host-Python is accessible on the build platform,
    even though it won't run there.

cross-Python
    A Python installation that runs on the build platform, but reports
    configuration information (architecture, build flags, etc.) exactly as
    host-Python would. This is used for cross-compiling extension modules.

