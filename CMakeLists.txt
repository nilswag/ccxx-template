cmake_minimum_required(VERSION 3.10)
project(idk)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

add_compile_definitions(${PROJECT_NAME} BASE_PATH="{CMAKE_SOURCE_DIR}/")
add_compile_definitions(${PROJECT_NAME} RES_PATH="{CMAKE_SOURCE_DIR}/res/")

add_subdirectory(ext/glfw)
add_subdirectory(ext/glad)

add_executable(${PROJECT_NAME} src/main.cpp)

target_include_directories(${PROJECT_NAME}
    PRIVATE src/
)

target_link_libraries(${PROJECT_NAME}
    PRIVATE glfw
    PRIVATE glad
)