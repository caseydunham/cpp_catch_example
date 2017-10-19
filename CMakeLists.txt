cmake_minimum_required(VERSION 3.9.4)

project (cpp_catch_example)

# setup directory where we should look for cmake files
list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")

# Prepare "Catch" library for other executables
set(CATCH_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/catch)
add_library(Catch INTERFACE)
target_include_directories(Catch INTERFACE ${CATCH_INCLUDE_DIR})

set(TEST_SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/main.cpp)

add_executable(tests ${TEST_SOURCES})
target_link_libraries(tests Catch)

add_executable(cpp_catch_example main.cpp)
