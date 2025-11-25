# Demo-1 Basic CMake Setup

The most basic cmake project which contains a minimal hello world c++ program. For more details on the code itself, look at the comments in the ***CMakeLists.txt*** file.

### To build and run the code... On Linux

Make a new directory named build (or anything you wish) and inside that folder run. This command will run cmake (meta-build system generator) and make (build system on linux)

` cmake .. && make -j10 `

Then an executable file will be generated inside the build folder which can be run (on linux) using

` ./Demo1Core `