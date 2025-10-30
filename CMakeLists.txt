cmake_minimum_required(VERSION 3.16)

project(vulkan-tutorial)

# set(CMAKE_CXX_STANDARD 20)

option(ENABLE_CPP20_MODULE "Enable C++ 20 module support for Vulkan" OFF)

if(ENABLE_CPP20_MODULE)
    set(CMAKE_CXX_SCAN_FOR_MODULES ON)
endif()

add_executable(app main.cpp)

find_package(glfw3 REQUIRED)
find_package(glm REQUIRED)
find_package(stb REQUIRED)
find_package(Vulkan REQUIRED)
target_include_directories(app PRIVATE ${Vulkan_INCLUDE_DIRS})
target_link_libraries(app PRIVATE ${Vulkan_LIBRARIES})

target_link_libraries(app PRIVATE glfw)

