cmake_minimum_required (VERSION 2.6)

set(exec_server_name "test_server")
set(exec_client_name "test_client")

#aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR} server_srcs)
set(server_srcs ${CMAKE_CURRENT_SOURCE_DIR}/test_server.cpp)
set(client_srcs ${CMAKE_CURRENT_SOURCE_DIR}/test_client.cpp)

add_definitions(
    -g
    -Wall
    -O0
    -std=c++11
)

add_executable(${exec_server_name} ${server_srcs})
target_link_libraries(${exec_server_name} sword)

add_executable(${exec_client_name} ${client_srcs})
target_link_libraries(${exec_client_name} sword)