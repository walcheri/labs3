# Только если файл еще не включен через add_subdirectory
if(NOT TARGET formatter_ex_lib)
    add_library(formatter_ex_lib STATIC formatter_ex.cpp)
    target_include_directories(formatter_ex_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
    
    # Связываем только если formatter_lib существует
    if(TARGET formatter_lib)
        target_link_libraries(formatter_ex_lib PRIVATE formatter_lib)
    endif()
endif()
