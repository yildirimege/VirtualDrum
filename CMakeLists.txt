# -------------------------------------------------------------------------------------------------
# CMake setup for standalone desktop application.
#
# Notes:
#   - build via:
#       mkdir build_debug && cd build_debug
#       cmake -DCMAKE_BUILD_TYPE=Debug ..
#       make
# -------------------------------------------------------------------------------------------------
cmake_minimum_required(VERSION 3.13)
message(STATUS "Using CMake v${CMAKE_VERSION}")


# -------------------------------------------------------------------------------------------------
# Set the C++ standard
# -------------------------------------------------------------------------------------------------
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)


# -------------------------------------------------------------------------------------------------
# project settings
# -------------------------------------------------------------------------------------------------
project(VirtualDrum LANGUAGES CXX)


# -------------------------------------------------------------------------------------------------
# Place binaries and libraries according to GNU standards
# -------------------------------------------------------------------------------------------------
include(GNUInstallDirs)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/${CMAKE_INSTALL_LIBDIR})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/${CMAKE_INSTALL_LIBDIR})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/${CMAKE_INSTALL_BINDIR})

# -------------------------------------------------------------------------------------------------
# Project Definitions
# -------------------------------------------------------------------------------------------------
add_subdirectory(lib)
add_subdirectory(app)

