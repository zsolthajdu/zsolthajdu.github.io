---
layout: post
title:  "CMake example config for a simple C++ project"
date:   2023-12-16 15:15:24 -0700
categories: cmake makefile c++
---

CMake example config for a simple C++ project.

## CMakeLists.txt
The content of the CMakeLists.txt for cmake
```
project(example)
cmake_minimum_required(VERSION 3.2)

set ( example_VERSION_MAJOR 1)
set ( example_VERSION_MINOR 0)

configure_file (
  "${PROJECT_SOURCE_DIR}/exampleConfig.h.in"
  "${PROJECT_BINARY_DIR}/exampleConfig.h"
  )

include_directories("${PROJECT_BINARY_DIR}")
include_directories(${PROJECT_SOURCE_DIR}/include)

add_executable( example example.cpp )

if(UNIX)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g -O0")

# For gprof
# set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g -O0 -pg")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -D_LINUX -std=c++11")
target_link_libraries( example pthread )
endif()
```
This is a generic code completion plugin that supports many programming languages.

## Additional files
Some other files that go with the above config
#### exampleConfig.h.in
This will generate a file called exampleConfig.h in the build directory that your source module can include.
```
#define example_VERSION_MAJOR @example_VERSION_MAJOR@
#define example_VERSION_MINOR @example_VERSION_MINOR@
```
The content of exampleConfig.h should lokk something like
```
#define example_VERSION_MAJOR 1
#define example_VERSION_MINOR 0
```
IOW make the same macros available for the source code to check.