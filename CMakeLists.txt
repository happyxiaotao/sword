
cmake_minimum_required(VERSION 3.16)

project(sword)

set(LIB_NAME "sword")
set(CMAKE_CXX_FLAGS "-std=c++11")

set(LIBRARY_OUTPUT_PATH "${PROJECT_SOURCE_DIR}/lib")
set(EXECUTABLE_OUTPUT_PATH "${PROJECT_SOURCE_DIR}/bin")

aux_source_directory(${PROJECT_SOURCE_DIR}/src/utils/. SRCS)

include_directories(
    "${PROJECT_SOURCE_DIR}/third_party/asio/include"
)

add_library(${LIB_NAME} STATIC ${SRCS})
target_link_libraries(${LIB_NAME} pthread)

add_subdirectory(test)

