cmake_minimum_required(VERSION 3.8)

project(GameEngine)

set(CMAKE_PREFIX_PATH $ENV{CMAKE_INSTALL_PREFIX} CACHE PATH "install prefix" FORCE)

file(GLOB_RECURSE SRC "src/*.cpp" "include/*.h")

add_executable(GameEngine ${SRC})

set(GLEW_USE_STATIC_LIBS)

find_library(OpenGL NAMES opengl32 GL)
find_library(glfw NAMES glfw3)
find_library(glew NAMES GLEW glew32s)

target_link_libraries(GameEngine ${LIB} ${OpenGL} ${glfw} ${glew})

target_include_directories(GameEngine PRIVATE include)