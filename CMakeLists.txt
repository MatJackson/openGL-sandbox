cmake_minimum_required(VERSION 3.15)
project(openGL_sandbox)

set(CMAKE_CXX_STANDARD 20)

add_executable(openGL_sandbox src/glad/glad.c src/main.cpp src/shaders/Shader.cpp src/shaders/Shader.h src/stb/stb_image.cpp src/camera/Camera.h)

add_subdirectory(dependencies/glfw-3.3.2)
add_subdirectory(dependencies/glm-0.9.9.7)

target_include_directories(openGL_sandbox PRIVATE ${PROJECT_SOURCE_DIR}/dependencies/glad/include)
target_include_directories(openGL_sandbox PRIVATE ${PROJECT_SOURCE_DIR}/dependencies/stb/include)
target_link_libraries(openGL_sandbox glfw)
target_link_libraries(openGL_sandbox glm)

find_package(OpenGL REQUIRED)

target_link_libraries(openGL_sandbox OpenGL::GL)