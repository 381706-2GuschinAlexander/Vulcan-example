add_executable(main main.cpp)

include_directories( ${include_dir})
target_link_libraries(main  PRIVATE ${lib})


find_package(Vulkan REQUIRED)
target_include_directories(main PRIVATE ${Vulkan_INCLUDE_DIRS})
target_link_libraries(main PRIVATE Vulkan::Vulkan)

find_package(glfw3 REQUIRED)
target_include_directories(main PRIVATE ${GLFW3_INCLUDE_DIRS})
target_link_libraries(main PRIVATE glfw)

find_package(GLM REQUIRED)
target_include_directories(main PRIVATE ${GLM_INCLUDE_DIRS})

