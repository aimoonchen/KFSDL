cmake_minimum_required(VERSION 3.20)

project(MY_APP)

set(INCLUDE_LOCATION ../bgfx.cmake/bgfx/include ../bgfx.cmake/bx/include ../bgfx.cmake/bimg/include ../SDL/include)
include_directories(${INCLUDE_LOCATION})

find_library(SDL2 SDL2)

add_library(main SHARED)

# target_sources(main PRIVATE main.cpp)
target_sources(main PRIVATE bgfx_utils.cpp cmd.cpp input.cpp entry.cpp entry_sdl.cpp helloworld.cpp)

target_link_libraries(main SDL2 bgfx bx bimg GLESv3 EGL android log m)
