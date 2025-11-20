cmake_minimum_required(VERSION 3.16)
project(SimpleGLFWExample VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GLFW REQUIRED glfw3)

include_directories(${GLFW_INCLUDE_DIRS})
link_directories(${GLFW_LIBRARY_DIRS})
add_definitions(${GLFW_CFLAGS_OTHER})

find_package(OpenGL REQUIRED)

add_executable(SimpleGLFWExample main.cpp)
target_link_libraries(SimpleGLFWExample ${GLFW_LIBRARIES} OpenGL::GL dl pthread X11 Xrandr Xi Xxf86vm Xcursor)
