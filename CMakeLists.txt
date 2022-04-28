cmake_minimum_required(VERSION 3.0)

project(linenoise)

set(SOURCES linenoise.c)
add_definitions(-DLINENOISE_INTERRUPTIBLE)

add_library(linenoise ${SOURCES})
target_include_directories(linenoise PUBLIC .)

add_executable(linenoise_example example.c)
target_link_libraries(linenoise_example linenoise)

install (TARGETS linenoise DESTINATION lib)
install (FILES linenoise.h DESTINATION include)
