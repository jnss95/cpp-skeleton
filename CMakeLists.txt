cmake_minimum_required(VERSION 3.21)

# The main project
project(
    "CppSkeleton"
    VERSION 1.0
    DESCRIPTION
        "The 'build-all' instructions for all examples for the book CMake Best Practices"
    LANGUAGES CXX
)
set(CMAKE_BUILD_TYPE
    "Debug"
    CACHE STRING "Default build type for single-config generators"
)
set(CMAKE_EXPORT_COMPILE_COMMANDS TRUE)

add_compile_options(-Wall -Wextra -Wpedantic -Werror)
FILE(GLOB_RECURSE sources "src/*.cpp")
add_executable(${PROJECT_NAME} ${sources})
target_include_directories(${PROJECT_NAME} PRIVATE "src")