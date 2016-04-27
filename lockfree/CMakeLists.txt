cmake_minimum_required(VERSION 2.8)
set(CMAKE_DISABLE_IN_SOURCE_BUILD ON)

project(lockfree CXX)
find_package(Threads)

add_executable(lockfree_race stack_race.cpp)
add_executable(lockfree_time stack_time.cpp)
add_executable(lockfree stack_test.cpp)
target_link_libraries(lockfree gtest)
target_link_libraries(lockfree_time gtest ${CMAKE_THREAD_LIBS_INIT})

add_test(Lockfree lockfree)
add_test(Lockfree_Race lockfree_race)
add_test(Lockfree_Time lockfree_time)