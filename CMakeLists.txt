cmake_minimum_required(VERSION 3.0.0)
project(httpserver VERSION 0.1.0 LANGUAGES C)

file(GLOB code_src
    "src/*.c"
)

add_executable(httpserver ${code_src})

target_include_directories(httpserver PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")

set_property(TARGET httpserver PROPERTY CXX_STANDARD 17)

set(CMAKE_CXX_FLAGS "-Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "-g")
#set(CMAKE_CXX_FLAGS_RELEASE "-O3")

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
