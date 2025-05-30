cmake_minimum_required(VERSION 3.10)
project(formatter)

# Создаем статическую библиотеку formatter из исходных файлов
add_library(formatter STATIC formatter.cpp formatter.h)
