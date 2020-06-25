# CMakeLists files in this project can
# refer to the root source directory of the project as ${HELLO_SOURCE_DIR} and
# to the root binary directory of the project as ${HELLO_BINARY_DIR}.
cmake_minimum_required(VERSION 3.0)
project (BUILD_BITCOIN CXX)
set(CMAKE_CXX_STANDARD 11)

# Recurse into the "Hello" and "Demo" subdirectories. This does not actually
# cause another cmake executable to run. The same process will walk through
# the project's entire directory structure.
add_subdirectory (crypto)
add_subdirectory (compat)
add_subdirectory (util)
add_subdirectory (support)

add_library(Bitcoin_Core uint256.h uint256.cpp attributes.h tinyformat.h)
add_executable(clean_build main.cpp)
target_link_libraries (clean_build LINK_PUBLIC Crypto)
target_include_directories (Bitcoin_Core PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
