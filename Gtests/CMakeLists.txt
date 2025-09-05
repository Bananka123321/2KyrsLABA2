include(FetchContent)

FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/refs/tags/v1.15.2.zip
)
FetchContent_MakeAvailable(googletest)

add_executable(GTestTests IPTests.cpp ../Tasks/IpTask.cpp)

target_include_directories(GTestTests PRIVATE ${CMAKE_SOURCE_DIR}/Tasks)

target_link_libraries(GTestTests PRIVATE gtest gtest_main)

include(GoogleTest)
gtest_discover_tests(GTestTests)
