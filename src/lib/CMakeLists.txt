file(GLOB hdrs "*.h*") 
file(GLOB srcs "*.cpp")

add_library(${lib} SHARED ${srcs} ${hdrs})

find_package(Vulkan REQUIRED)
target_include_directories(${lib} PRIVATE ${Vulkan_INCLUDE_DIRS})
target_link_directories(${lib} PRIVATE ${Vulkan_LIBRARY_DIRS})

find_package(glfw3 REQUIRED)
target_include_directories(${lib} PRIVATE ${glfw_INCLUDE_DIRS})
target_link_directories(${lib} PRIVATE ${glfw_LIBRARY_DIRS})

find_package(GLM REQUIRED)
target_include_directories(${lib} PRIVATE ${GLM_INCLUDE_DIRS})
target_link_directories(${lib} PRIVATE ${GLM_LIBRARY_DIRS})
