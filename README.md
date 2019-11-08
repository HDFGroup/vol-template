# HDF5 VOL connector template

**NOTE: This is a work in progress. It should be complete when HDF5 1.12.0 is released in late 2019.**

This is a template for creating an HDF5 virtual object layer (VOL) connector.

Copy this code into your own repository and modify the source, test, and build files as needed to implement your own functionality.

The code included in the source directory builds an "empty" VOL connector which has no functionality aside from being capable of registration. Although lacking as a "real" VOL connector, this shell can still serve as a useful test of whether dynamic plugin loading is working.

For a demonstration connector with more functionality, see the Berkeley DB VOL connector and associated tutorial here:

https://bitbucket.hdfgroup.org/projects/HDF5VOL/repos/berkeley-db/browse


## Getting started

You will need a few things to build the code in this repository:

* HDF5 1.12.0 or later
* CMake or the Autotools

The autotools don't do anything fancy, so any reasonably recent version should work. The configure.ac file explicitly requires autoconf 2.69 (from 2012) and automake, etc. from about that time on should be fine.


### Autotools Builds

1) The first thing you need to do is run the autogen.sh script located in the source root. This will run the autotools and generate the build files.

2) Next, switch to your build directory and run configure. You might need to specify the path to a VOL-enabled HDF5 (version 1.12.0 or later) using the --with-hdf5 option. Oddly, --with-hdf5 needs you to point to the h5cc file. This will be improved in the future.

3) Once configured, you should be able to make and build. Switching to the test directory and running 'make check' will run the test script.

### CMake Builds

1) Run ccmake or the CMake GUI and point it at a VOL-enabled HDF5 installation. You may need to switch to "advanced mode" to see all the options. Configure and generate.

2) Build the software using 'make', etc.

3) Run the test program using 'make test', 'ctest .', etc.
