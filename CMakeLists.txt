cmake_minimum_required(VERSION 3.19)
project(opengl_demo)

set(CMAKE_CXX_STANDARD 14)

include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(${PROJECT_SOURCE_DIR}/lib)

# 添加目标链接
set(GLEW_LINK /usr/local/Cellar/glew/2.2.0_1/lib/libGLEW.2.2.0.dylib)
set(GLFW_LINK /usr/local/Cellar/glfw/3.3.4/lib/libglfw.3.dylib)
link_libraries(${OPENGL} ${GLEW_LINK} ${GLFW_LINK})


set(SOURCE_FILES "src/glad.c" "main.cpp")
add_executable(opengl_demo ${SOURCE_FILES})

if (APPLE)
    target_link_libraries(opengl_demo "-framework OpenGL")
    target_link_libraries(opengl_demo "-framework GLUT")
endif()
