cmake_minimum_required(VERSION 3.24.1)
project (HELLO_WORLD)
add_executable(hello main.cpp)

include(ExternalProject)
ExternalProject_add(spdlog
    SOURCE_DIR ${PROJECT_SOURCE_DIR}/include/spdlog
    CMAKE_ARGS -DSPDLOG_BUILD_SHARED=OFF)
add_dependencies(hello spdlog)
