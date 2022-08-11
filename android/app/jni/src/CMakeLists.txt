cmake_minimum_required(VERSION 3.20)

project(MY_APP)

find_library(SDL2 SDL2)

add_library(main SHARED)

target_sources(main PRIVATE main.cpp)

target_link_libraries(main
    GLESv3
    android
    log
    m
    SDL2)