#
# Copyright OpenEmbedded Contributors
#
# SPDX-License-Identifier: MIT
#

cmake_minimum_required(VERSION 3.22)

project(test-cmake-example
  VERSION 1.0.0
  LANGUAGES CXX
)

# A simple test executable for testing the library
add_executable(test-cmake-example test-cpp-example.cpp)
target_link_libraries(test-cmake-example PRIVATE cmake-example-lib)

install(TARGETS test-cmake-example
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

add_test(NAME test-cmake-example COMMAND test-cmake-example)
