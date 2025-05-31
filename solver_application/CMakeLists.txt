cmake_minimum_required(VERSION 3.10)
project(solver)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Подключаем библиотеки
add_subdirectory(../formatter_lib formatter)
add_subdirectory(../formatter_ex_lib formatter_ex)

# Добавляем исполняемый файл
add_executable(solver equation.cpp ../solver_lib/solver.cpp)

# Указываем где искать заголовочные файлы
target_include_directories(solver PRIVATE 
    ${CMAKE_SOURCE_DIR}/../solver_lib
    ${CMAKE_SOURCE_DIR}/../formatter_ex_lib
    ${CMAKE_SOURCE_DIR}/../formatter_lib
)

# Линкуем с библиотеками
target_link_libraries(solver PRIVATE formatter_ex)
