cmake_minimum_required(VERSION 3.23)
project(cmake_testapp)

set(CMAKE_CXX_STANDARD 11)

add_executable(cmake_testapp main.cpp calc.cpp)
add_executable(cmake_testapp_calc main.cpp calc.cpp)
add_library(test_library STATIC calc.cpp)

include_directories(includes/math)
include_directories(includes/general)

find_library(TEST_LIBRARY test_library lib)
target_link_libraries(cmake_testapp LINK_PUBLIC ${TEST_LIBRARY})
