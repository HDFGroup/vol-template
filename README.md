# HDF5 VOL connector template

**NOTE: This is a work in progress. It should be complete when HDF5 1.12.0 is
released in late 2019.**

This is a template for creating an HDF5 virtual object layer (VOL) connector.

Copy this code into your own repository and modify the source, test, and build
files as needed to implement your own functionality.

The code included in the source directory builds an "empty" VOL connector which
has no functionality aside from being capable of registration. Although lacking
as a "real" VOL connector, this shell can still serve as a useful test of
whether dynamic plugin loading is working.

For a demonstration connector with more functionality, see the Berkeley DB
VOL connector here:

LINK

and the associated tutorial here:

LINK


## Getting started

You will need a few things to build the code in this repository:

* HDF5 1.12.0 or later
* CMake (version?) or the Autotools

### Autotools Builds


### CMake Builds
