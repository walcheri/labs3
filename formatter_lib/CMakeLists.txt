# Только если файл еще не включен через add_subdirectory
if(NOT TARGET formatter_lib)
    add_library(formatter_lib STATIC formatter.cpp)
    target_include_directories(formatter_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
endif()
