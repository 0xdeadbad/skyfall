cmake_minimum_required(VERSION 3.25)

project(
    skyfall
    VERSION 0.0.1
    DESCRIPTION "A 3D game engine written in C++ 17"
    LANGUAGES CXX C
)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON CACHE INTERNAL "") # works

add_library(${PROJECT_NAME} STATIC 
    Source/Application.cpp

    Source/glad.c
)

target_include_directories( ${PROJECT_NAME}
    PUBLIC ${PROJECT_SOURCE_DIR}/Include
)

## sdl2 stuff
list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake/sdl2)
find_package(SDL2 REQUIRED)
target_link_libraries(${PROJECT_NAME} SDL2::Main)

add_subdirectory(Examples)
