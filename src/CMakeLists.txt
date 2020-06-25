cmake_minimum_required(VERSION 3.0)
project (BUILD_BITCOIN CXX)
set(CMAKE_CXX_STANDARD 11)

add_subdirectory (crypto)
add_subdirectory (compat)
add_subdirectory (util)
add_subdirectory (support)

add_library(Bitcoin_Core uint256.h uint256.cpp attributes.h tinyformat.h)
add_executable(clean_build main.cpp)

target_link_libraries (clean_build LINK_PUBLIC Crypto)
target_include_directories (Bitcoin_Core PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
