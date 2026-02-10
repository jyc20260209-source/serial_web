cmake_minimum_required(VERSION 3.10)

project(serial_web)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(serial_web main.cpp) # Replace main.cpp with your source files

# Link with pthread
find_package(Threads REQUIRED)
target_link_libraries(serial_web PRIVATE Threads::Threads)