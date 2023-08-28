cmake_minimum_required(VERSION 3.10)

project(VulkanApp)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Include GLFW as a subdirectory
add_subdirectory(external/glfw)

# Find Vulkan package
find_package(Vulkan REQUIRED)

# Your main executable
add_executable(VulkanApp src/main.cpp)

# Link against Vulkan and GLFW
target_include_directories(VulkanApp PRIVATE ${Vulkan_INCLUDE_DIRS})
target_link_libraries(VulkanApp Vulkan::Vulkan glfw)
