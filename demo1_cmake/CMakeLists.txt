# Version of cmake required to build this project.
cmake_minimum_required(VERSION 4.0.0)

# Basic specifications of the project like name, version, language
project(
    demo1_cmake
    VERSION 1.0.0
    LANGUAGES C CXX
)

# Declaring and enforcing the C++ standards for this project.
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Now we want to add some executables, these are the files which are actually compiled and linked.
add_executable(Demo1Core
    ${CMAKE_CURRENT_SOURCE_DIR}/Demo1Core/src/main.cpp
)

