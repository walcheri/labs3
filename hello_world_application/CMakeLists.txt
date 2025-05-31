cmake_minimum_required(VERSION 3.10)
project(hello_world)

# Подключаем библиотеку formatter_ex (используем относительный путь)
add_subdirectory(../formatter_ex_lib ${CMAKE_BINARY_DIR}/formatter_ex)

# Создаем исполняемый файл
add_executable(hello_world hello_world.cpp)

# Указываем зависимости
target_link_libraries(hello_world formatter_ex)

# Явно указываем пути к заголовкам
target_include_directories(hello_world PRIVATE
    ../formatter_ex_lib
    ../formatter_lib
)

# Устанавлием стандарт C++ (альтернативный способ для старых CMake)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

