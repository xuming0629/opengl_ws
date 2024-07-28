# CMakeList.txt: OpenGLPrj 的 CMake 项目，在此处包括源代码并定义
# 项目特定的逻辑。
#
cmake_minimum_required (VERSION 3.8)

# 添加可执行文件
# add_executable(learnOpenGL main.cpp)
add_executable(learnOpenGL main01.cpp)

# 包含主项目的包含目录
target_include_directories(learnOpenGL PRIVATE
    "${CMAKE_SOURCE_DIR}/3rd_party/glfw3.4/include"
    "${CMAKE_SOURCE_DIR}/3rd_party/glad/include"
    "${CMAKE_SOURCE_DIR}/3rd_party"
    "${CMAKE_SOURCE_DIR}/3rd_party/glm"
)

# 链接静态库
target_link_libraries(learnOpenGL PRIVATE
    "${CMAKE_SOURCE_DIR}/3rd_party/glfw3.4/lib/libglfw3.a"
    "${CMAKE_SOURCE_DIR}/3rd_party/glad/lib/libglad.a"  # 确保路径正确
    OpenGL::GL
)