# CMake 프로그램의 최소 버전
cmake_minimum_required(VERSION 3.11)

# 프로젝트 정보
project(
  vulkan_vscode
  VERSION 0.1
  DESCRIPTION "build vulkan program in vscode"
  LANGUAGES CXX)

add_executable (main main.cpp)
target_compile_options(main PUBLIC
    /opt/homebrew/lib/libglfw.3.4.dylib
    /usr/local/lib/libvulkan.1.4.321.dylib
    /usr/local/lib/libvulkan.1.dylib
    -g
    )

target_include_directories(main PUBLIC
    /opt/homebrew/include
    /Users/kim/VulkanSDK/1.4.321.0/macOS/include
    )

target_link_directories(main PUBLIC
    /opt/homebrew/lib
    /Users/kim/VulkanSDK/1.4.321.0/macOS/lib)

target_link_libraries(main
    /opt/homebrew/lib/libglfw.3.4.dylib
    /usr/local/lib/libvulkan.1.4.321.dylib
    /usr/local/lib/libvulkan.1.dylib
)
