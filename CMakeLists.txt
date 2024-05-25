cmake_minimum_required(VERSION 3.10)

project(imgui)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Vulkan REQUIRED)

set(IMGUI_SOURCE
        ${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_vulkan.cpp)

add_library(imgui ${IMGUI_SOURCE})

target_include_directories(imgui PRIVATE ${CMAKE_CURRENT_SOURCE_DIR} ${Vulkan_INCLUDE_DIRS})

target_link_libraries(imgui PRIVATE ${Vulkan_LIBRARY})
