cmake_minimum_required(VERSION 3.10)
project(LearnOpenGL)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
add_compile_definitions(GL_SILENCE_DEPRECATION)

set(GLFW_DIR /Users/danielviklund/Downloads/glfw-3.4)

file(GLOB_RECURSE SOURCES 
    src/*.cpp
    src/*.c
)

add_executable(LearnOpenGL ${SOURCES})

target_include_directories(LearnOpenGL PRIVATE
    include
    ${GLFW_DIR}/include
)

target_link_libraries(LearnOpenGL PRIVATE
    ${GLFW_DIR}/build/src/libglfw3.a
    "-framework Cocoa"
    "-framework OpenGL"
    "-framework IOKit"
)
