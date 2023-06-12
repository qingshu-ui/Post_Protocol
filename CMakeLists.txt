cmake_minimum_required(VERSION 3.0.0)
project(protocol VERSION 0.1.0 LANGUAGES C CXX)

aux_source_directory(src PROTOCOL_SOURCES)
add_library(${PROJECT_NAME} STATIC ${PROTOCOL_SOURCES})

target_link_libraries(${PROJECT_NAME} PRIVATE protobuf::protobuf)