# Только если файл еще не включен через add_subdirectory
if(NOT TARGET solver_lib)
    add_library(solver_lib STATIC solver.cpp)
    target_include_directories(solver_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
endif()
