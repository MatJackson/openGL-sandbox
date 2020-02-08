cmake_minimum_required(VERSION 3.15)
project(openGL_sandbox)

set(CMAKE_CXX_STANDARD 20)

add_executable(openGL_sandbox src/glad/glad.c src/main.cpp)

add_subdirectory(dependencies/glfw-3.3.2)

target_include_directories(openGL_sandbox PRIVATE ${PROJECT_SOURCE_DIR}/dependencies/glad/include)
target_link_libraries(openGL_sandbox glfw)

find_package(OpenGL REQUIRED)

target_link_libraries(openGL_sandbox OpenGL::GL)