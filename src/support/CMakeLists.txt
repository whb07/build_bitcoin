cmake_minimum_required(VERSION 3.0)

add_library(
        Support cleanse.cpp cleanse.h events.h
        lockedpool.cpp lockedpool.h
)
add_subdirectory(allocators)
target_include_directories(Support PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(Support Allocators)