cmake_minimum_required(VERSION 3.26)
project(hello_sdl2)

set(CMAKE_CXX_STANDARD 17)

# กำหนด SDL2 Path
set(SDL2_PATH /opt/homebrew/Cellar/sdl2/2.28.2)

# กำหนด include และ lib directory
set(SDL2_INCLUDE_DIR ${SDL2_PATH}/include)
set(SDL2_LIB_DIR ${SDL2_PATH}/lib)

# หา package SDL2 ใน SDL2 path ที่เรากำหนด
find_package(SDL2 REQUIRED PATHS ${SDL2_PATH})

# include และ link lib/header
include_directories(${SDL2_INCLUDE_DIR})
link_directories(${SDL2_LIB_DIR})

add_executable(hello_sdl2 main.cpp)

# กำหนด target link library
target_link_libraries(${PROJECT_NAME} SDL2::SDL2)
