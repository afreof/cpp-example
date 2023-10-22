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

# A simple library linking json-c library found by pkgconfig
add_library(cmake-example-lib "")
target_sources(cmake-example-lib
  PRIVATE
    ${CMAKE_CURRENT_LIST_DIR}/cpp-example-lib.cpp
  PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}/cpp-example-lib/cpp-example-lib.hpp
)
set_target_properties(cmake-example-lib PROPERTIES 
    VERSION ${PROJECT_VERSION}
    SOVERSION ${PROJECT_VERSION_MAJOR}
)
target_include_directories(cmake-example-lib PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
)
target_link_libraries(cmake-example-lib PRIVATE json-c::json-c)

# target_link_libraries(cmake-example-lib ${JSONC_LIBRARIES})
# target_include_directories(cmake-example-lib PUBLIC ${JSONC_INCLUDE_DIRS})
# target_compile_options(cmake-example-lib PUBLIC ${JSONC_CFLAGS_OTHER})
install(TARGETS cmake-example-lib
    INCLUDES DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
)

# A simple executable linking the library
add_executable(cmake-example cpp-example.cpp)
target_link_libraries(cmake-example PRIVATE cmake-example-lib)

install(TARGETS cmake-example
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
