#
# Copyright OpenEmbedded Contributors
#
# SPDX-License-Identifier: MIT
#

cmake_minimum_required(VERSION 3.22)

project(cmake-example
  VERSION 1.0.0
  LANGUAGES CXX
)

option(BUILD_SHARED_LIBS "Build using shared libraries" ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED On)
set(CMAKE_CXX_EXTENSIONS Off)

include(GNUInstallDirs)

# Find json-c
# find_package(PkgConfig REQUIRED)
# pkg_check_modules(JSONC REQUIRED json-c)
find_package(json-c)

add_subdirectory(src)

include(CTest)
add_subdirectory(tests)
