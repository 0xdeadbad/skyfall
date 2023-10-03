cmake_minimum_required (VERSION 3.5)

project(001-rectangle)

add_executable(${PROJECT_NAME} src/main.cpp)

target_include_directories( ${PROJECT_NAME}
    PUBLIC ${PROJECT_SOURCE_DIR}/../../Include
)

target_link_libraries(${PROJECT_NAME}
    skyfall
)
