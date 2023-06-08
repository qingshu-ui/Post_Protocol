cmake_minimum_required(VERSION 3.0.0)
project(Post_Protocol VERSION 0.1.0 LANGUAGES C CXX)

set(CMAKE_POSITION_INDEPENDENT_CODE ON)

file(GLOB_RECURSE Post_Protocol_SOURCES src/*.cpp src/*.cc src/*.h)
add_library(Post_Protocol STATIC ${Post_Protocol_SOURCES})

if(MSVC)
    set_property(TARGET Post_Protocol PROPERTY MSVC_RUNTIME_LIBRARY "MultiThreadedDLL")
endif()

find_package(Protobuf CONFIG REQUIRED)
target_link_libraries(Post_Protocol PRIVATE protobuf::protobuf)