cmake_minimum_required(VERSION 3.8)

project(learnRaylib)

file(GLOB_RECURSE SRC "src/*.cpp" "include/*.h")

add_executable(learnRaylib ${SRC})

if(WIN32)
    file(GLOB_RECURSE LIB "lib/*.a")
    target_link_libraries(learnRaylib ${LIB})
else()
endif()

target_include_directories(learnRaylib PRIVATE include)