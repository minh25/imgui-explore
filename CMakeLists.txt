cmake_minimum_required(VERSION 3.28)
project(imgui_explore)

set(CMAKE_CXX_STANDARD 20)

file(GLOB imgui_sources
     "imgui/*.h"
     "imgui/*.cpp"
)
add_executable(imgui_explore main.cpp ${imgui_sources})

find_package(glad CONFIG REQUIRED)
target_link_libraries(imgui_explore PRIVATE glad::glad)

find_package(glfw3 CONFIG REQUIRED)
target_link_libraries(imgui_explore PRIVATE glfw)

target_include_directories(imgui_explore PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/imgui)