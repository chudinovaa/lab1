set(CMAKE_VER 3.14)
cmake_minimum_required(VERSION ${CMAKE_VER})
project(lab1)

set(CMAKE_CXX_STANDARD 17)
include_directories(${CMAKE_SOURCE_DIR})

add_executable(${PROJECT_NAME} src/main.cpp)
add_custom_command(TARGET ${PROJECT_NAME} POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_if_different
        "${PROJECT_SOURCE_DIR}/etc/abc.txt"
        $<TARGET_FILE_DIR:${PROJECT_NAME}>/abc.txt)

enable_testing()
include(cmake_macros/load_gtest.cmake)
find_package(Threads REQUIRED)
add_subdirectory(test)
