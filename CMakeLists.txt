cmake_minimum_required(VERSION 3.9.4)

project(cpp_catch_example)

# Prepare "Catch" library for other executables
set(CATCH_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/catch)
add_library(Catch INTERFACE)
target_include_directories(Catch INTERFACE ${CATCH_INCLUDE_DIR})

set(HEADER_FILES
  include/factorial.hpp
)
include_directories(include)

set(TEST_SRC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/tests)
set(SRC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src)

set(TEST_MAIN ${CMAKE_CURRENT_SOURCE_DIR}/tests-main.cpp)
set(MAIN ${CMAKE_CURRENT_SOURCE_DIR}/main.cpp)

set(TEST_SOURCES
  ${TEST_SRC_DIR}/tests-factorial.cpp
)

set(SOURCES
  ${SRC_DIR}/factorial.cpp
)

add_executable(tests ${SOURCES} ${HEADER_FILES} ${TEST_SOURCES} ${TEST_MAIN})
target_link_libraries(tests Catch)

add_executable(main ${SOURCES} ${HEADER_FILES} ${MAIN})
