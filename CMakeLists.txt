cmake_minimum_required(VERSION 3.10)

project(LearnOpenGL)

find_package(fmt CONFIG REQUIRED)
find_package(glfw3 CONFIG REQUIRED)
find_package(glad CONFIG REQUIRED)

set(COMMON_LIBS fmt::fmt glfw glad::glad)


include_directories(${CMAKE_SOURCE_DIR}/includes)

macro(add_exe source)
    get_filename_component(target ${source} NAME_WE)
    add_executable(${target} ${source})
    target_link_libraries(${target} PRIVATE ${COMMON_LIBS})
endmacro()

add_exe(hellowindow/helloworld.cpp)
add_exe(hellowindow/hello_triangle.cpp)
add_exe(GLSL/GLSL_1.cpp)
add_exe(GLSL/GLSL_2.cpp)
add_exe(GLSL/GLSL_3.cpp)
add_exe(texture/texture_1.cpp)
add_exe(texture/texture_2.cpp)
add_exe(Transformations/transformation.cpp)
add_exe(CoordinateSystems/coordinate_systems.cpp)
add_exe(Camera/camera.cpp)




