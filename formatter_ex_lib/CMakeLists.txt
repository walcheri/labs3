cmake_minimum_required(VERSION 3.10)
project(formatter_ex)

# Ищем собранную библиотеку formatter
find_library(FORMATTER_LIB formatter PATHS ~/labs3/formatter_lib/build NO_DEFAULT_PATH)

if(NOT FORMATTER_LIB)
    message(FATAL_ERROR "formatter library not found! Build formatter_lib first.")
endif()

add_library(formatter_ex STATIC formatter_ex.cpp formatter_ex.h)

target_link_libraries(formatter_ex PRIVATE ${FORMATTER_LIB})

target_include_directories(formatter_ex PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ~/labs3/formatter_lib
)
