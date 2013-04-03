project(tarsia)
cmake_minimum_required(VERSION 2.8)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/modules/")

find_package(OpenSSL)
include_directories(${OPENSSL_INCLUDE_DIR})

aux_source_directory(src SRC_LIST)
include_directories(include)
add_library(${PROJECT_NAME} ${SRC_LIST})
target_link_libraries(${PROJECT_NAME} crypto pthread)
