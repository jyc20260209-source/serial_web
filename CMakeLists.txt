cmake_minimum_required(VERSION 3.5)
project(serial_web C)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -O2 -pthread")

add_executable(serial_web
    src/main.c
    src/http_server.c
    src/serial_posix.c
    src/log_buffer.c
    src/base64.c
    src/json_simple.c
)

target_include_directories(serial_web PRIVATE src)

install(TARGETS serial_web DESTINATION bin)
install(DIRECTORY web/ DESTINATION share/serial_web)