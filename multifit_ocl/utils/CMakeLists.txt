cmake_minimum_required(VERSION 3.8)
project(utlis)

set(CMAKE_CXX_STANDARD 11)

# for debug purposes
message(CMAKE_MODULE_PATH = ${CMAKE_MODULE_PATH})
message(CMAKE_PREFIX_PATH = ${CMAKE_PREFIX_PATH})
message(CMAKE_SOURCE_DIR = ${CMAKE_SOURCE_DIR})
message(CMAKE_BINARY_DIR = ${CMAKE_BINARY_DIR})
message(PROJECT_SOURCE_DIR = ${PROJECT_SOURCE_DIR})
message(PROJECT_BINARY_DIR = ${PROJECT_BINARY_DIR})
message (CMAKE_CXX_COMPILER_VERSION = ${CMAKE_CXX_COMPILER_VERSION})
message (CMAKE_CXX_COMPILER_ID = ${CMAKE_CXX_COMPILER_ID})

message("-------------------------------------------")

# find OpenCL
find_package(OpenCL REQUIRED)
include_directories(SYSTEM ${OpenCL_INCLUDE_DIRS})

include_directories(${OpenCL_INCLUDE_DIRS})
message(OpenCL_FOUND = ${OpenCL_FOUND})
message(OpenCL_INCLUDE_DIRS = ${OpenCL_INCLUDE_DIRS})
message(OpenCL_LIBRARIES = ${OpenCL_LIBRARIES})
message(OpenCL_VERSION_STRING = ${OpenCL_VERSION_MAJOR})
message(OpenCL_VERSION_MAJOR = ${OpenCL_VERSION_MAJOR})
message(OpenCL_VERSION_MINOR = ${OpenCL_VERSION_MINOR})
set (LINK_LIBRARIES ${OpenCL_LIBRARIES} ${LINK_LIBRARIES})

message("-------------------------------------------")


set(SOURCES ./src/opencl.cpp ./src/options.cpp)

message("sources:")
message(${SOURCES})

add_executable(utils ${SOURCES})
