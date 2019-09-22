add_executable(test_sort test_sort.cpp)
target_include_directories(test_sort PRIVATE ${gtest_SOURCE_DIR}/include)
target_link_libraries(test_sort gtest gtest_main Threads::Threads)
add_test(test_sort test_sort)
