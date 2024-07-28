cmake_minimum_required (VERSION 3.8)

project ("learnOpenGL")


set(CMAKE_CUDA_STANDARD 17)
SET(CMAKE_CUDA_STANDARD_REQUIRED TRUE)
SET(CMAKE_CUDA_SEPARABLE_COMPILATION ON)
# 包含子项目。

# 查找OpenGL包
find_package(OpenGL REQUIRED)

if(OpenGL_FOUND)
    include_directories(
        "${CMAKE_SOURCE_DIR}/3rd_party/glfw3.4/include"
        "${CMAKE_SOURCE_DIR}/3rd_party/glad/include"
        "${CMAKE_SOURCE_DIR}/3rd_party"
        "${CMAKE_SOURCE_DIR}/3rd_party/glm"
    )
    link_directories(
        "${CMAKE_SOURCE_DIR}/3rd_party/glfw3.4/lib/"
        "${CMAKE_SOURCE_DIR}/3rd_party/glad/lib/"
    )

    set(HAVE_OpenGL True)
    message(STATUS "Configure package with OpenGL!")
else()
    set(HAVE_OpenGL False)
    message(STATUS "Configure package without OpenGL!")
endif()

add_subdirectory("learnOpenGL")
add_definitions(-w)





