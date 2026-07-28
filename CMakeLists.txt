cmake_minimum_required(VERSION 3.16)

project(Atoms LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

option(HEADLESS_BUILD "Build the console-only atom model for environments without an OpenGL desktop context" ON)

if(HEADLESS_BUILD)
    add_executable(atom src/atom.cpp)
    target_compile_definitions(atom PRIVATE HEADLESS_BUILD)
else()
    find_package(OpenGL REQUIRED)
    find_package(GLEW REQUIRED)
    find_package(glfw3 CONFIG REQUIRED)

    add_executable(atom src/atom.cpp)
    target_link_libraries(atom PRIVATE OpenGL::OpenGL GLEW::GLEW glfw)
endif()
