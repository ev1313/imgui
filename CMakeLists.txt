cmake_minimum_required(VERSION 3.20)
project(imgui LANGUAGES C CXX)

set(IMGUI_BUILD_DEMO ON CACHE BOOL "Build imgui demo window")

add_library(imgui imgui.cpp imgui_draw.cpp imgui_tables.cpp imgui_widgets.cpp $<$<BOOL:${IMGUI_BUILD_DEMO}>:imgui_demo.cpp>)
target_include_directories(imgui PUBLIC .)

add_subdirectory(backends)
add_subdirectory(misc/cpp)

