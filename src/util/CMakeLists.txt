
add_library(Util strencodings.cpp strencodings.h util_string.cpp util_string.h)
target_include_directories(Util PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(Util Bitcoin_Core)