# CMakeLists.txt

cmake_minimum_required(VERSION 3.10)
project(MyProject)

# Enable testing
enable_testing()

# Add GoogleTest
include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/refs/heads/main.zip
)
FetchContent_MakeAvailable(googletest)

# Add your test executable
add_executable(testsuite tests/main_test.cpp)

# Link with gtest and gtest_main
target_link_libraries(testsuite gtest gtest_main)

# Add test
include(GoogleTest)
gtest_discover_tests(testsuite)
