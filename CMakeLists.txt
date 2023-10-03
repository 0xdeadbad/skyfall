cmake_minimum_required(VERSION 3.5)

project(
    skyfall
    VERSION 0.0.1
    DESCRIPTION "A 3D game engine written in C++ 17"
    LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON CACHE INTERNAL "") # works

add_library(${PROJECT_NAME} STATIC 
    Source/Application.cpp
)

target_include_directories( ${PROJECT_NAME}
    PUBLIC ${PROJECT_SOURCE_DIR}/Include
)

add_subdirectory(Examples)
