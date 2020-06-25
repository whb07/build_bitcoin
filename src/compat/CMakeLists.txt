cmake_minimum_required(VERSION 3.15)

add_library(
        Compat assumptions.h byteswap.h cpuid.h endian.h
        glibc_compat.cpp glibc_sanity.cpp glibcxx_sanity.cpp
        sanity.h stdin.h stdin.cpp stdin.h strnlen.cpp
)

target_include_directories(Compat PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(Compat Bitcoin_Core)
target_link_libraries(Compat Crypto)
target_link_libraries(Compat Util)