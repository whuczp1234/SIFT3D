# SIFT3D
Analogue of the scale-invariant feature transform (SIFT) for three-dimensional images. Includes an image processing and linear algebra library with feature matching and RANSAC regression.

CONTENTS

This code creates the following executables:
- sift3d - CLI for the program functionality

and the following libraries:
- libsift3d.so - Extract and match SIFT3D features
- libimutil.so - A utility library for image processing, regression and linear algebra.
- libitkwrap.so - A C++ wrapper library using the Insight Toolkit (ITK). This is compiled only if ITK is found on your system.

Documentation can be found at:

See /examples for sample programs using the C library and C++ wrappers.

DEPENDENCIES

This code requires the following external libraries:
- LAPACK (http://www.netlib.org/lapack/)
- nifticlib (http://sourceforge.net/projects/niftilib/files/nifticlib/)

If the build system cannot find LAPACK, it will try to download and compile the source.

If you are using ITK, the build system will automatically find nifticlib there. Otherwise, you must install it yourself. (See the Ubuntu installation command below.)
- ITK (http://www.itk.org/)

This code requires the following tools to compile:
- CMake (http://www.cmake.org)
- A suitable C/C++ compiler, such as GCC.

On Ubuntu, as of version 14.04, the following command will install all dependencies and build tools:

	sudo apt-get install build-essential cmake liblapack-dev libnifti-dev

INSTALLATION INSTRUCTIONS

On Unix-like systems, the following commands will generate Makefiles and use them to compile the binaries in a subdirectory called "build":

	mkdir build
	cd build
	cmake ..
	make

If for some reason CMake cannot find the dependencies, you can specify the paths manually with "cmake -i .."

Use the following command to install the files:

	sudo make install

In principle you can use CMake to compile this code on Windows, but some modifications may be required to resolve the external dependencies.

Please contact me at blaine@stanford.edu if you have any questions or concerns.

USAGE INSTRUCTIONS

For instructions on using the CLI, type "sift3d -h".

Linkage dependencies are as follows:
	- libimutil - may be used as a standalone library
	- libsift3d - requires linking to libimutil
	- libitkwrap - requires linking to all other libraries
