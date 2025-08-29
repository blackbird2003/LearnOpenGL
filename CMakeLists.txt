cmake_minimum_required(VERSION 3.10)

project(LearnOpenGL)

find_package(fmt CONFIG REQUIRED)
find_package(glfw3 CONFIG REQUIRED)
find_package(glad CONFIG REQUIRED)
find_package(assimp CONFIG REQUIRED)
find_package(imgui CONFIG REQUIRED)


set(COMMON_LIBS fmt::fmt glfw glad::glad assimp::assimp imgui::imgui)


include_directories(${CMAKE_SOURCE_DIR}/includes)


macro(add_exe source)
    get_filename_component(target ${source} NAME_WE)
    add_executable(${target} ${source})
    target_link_libraries(${target} PRIVATE ${COMMON_LIBS})
endmacro()

add_exe(Basic/hellowindow/helloworld.cpp)
add_exe(Basic/hellowindow/hello_triangle.cpp)
add_exe(Basic/GLSL/GLSL_1.cpp)
add_exe(Basic/GLSL/GLSL_2.cpp)
add_exe(Basic/GLSL/GLSL_3.cpp)
add_exe(Basic/texture/texture_1.cpp)
add_exe(Basic/texture/texture_2.cpp)
add_exe(Basic/Transformations/transformation.cpp)
add_exe(Basic/CoordinateSystems/coordinate_systems.cpp)
add_exe(Basic/Camera/camera.cpp)


add_exe(Lighting/color.cpp)

add_exe(Lighting/basic_lighting.cpp)
add_exe(Lighting/materials.cpp)
add_exe(Lighting/lighting_maps.cpp)
add_exe(Lighting/light_casters_directional.cpp)
add_exe(Lighting/light_casters_point.cpp)
add_exe(Lighting/light_casters_flashlight.cpp)
add_exe(Lighting/multiple_lights.cpp)

add_exe(imgui_test.cpp)

add_exe(model_test.cpp)



