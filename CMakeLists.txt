
cmake_minimum_required(VERSION 3.2)

project(ImaginationStudio)

add_definitions(-std=c++11)

set(sdk_path "/home/fabiao2018/Downloads/vulkan-sdk/x86_64")
include_directories(
include
${sdk_path}/include
)

AUX_SOURCE_DIRECTORY(src DIR_SRCS)

set(libraries
libvkdisplay_xcb.so
libvulkan.so.1.1.82
)

link_directories(${sdk_path}/lib)
message(STATUS "==========================${sdk_path}===================")

add_executable(${PROJECT_NAME} main.cpp ${DIR_SRCS})

target_link_libraries(${PROJECT_NAME} vulkan)
target_link_libraries(${PROJECT_NAME} vkdisplay_xcb xcb)


