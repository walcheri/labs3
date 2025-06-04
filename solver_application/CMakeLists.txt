# Всегда создаем исполняемый файл
add_executable(solver_application equation.cpp)

# Связываем с библиотеками, если они существуют
if(TARGET formatter_ex_lib)
    target_link_libraries(solver_application PRIVATE formatter_ex_lib)
endif()

if(TARGET solver_lib)
    target_link_libraries(solver_application PRIVATE solver_lib)
endif()
