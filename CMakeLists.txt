cmake_minimum_required(VERSION 3.20)
project (imgui)

add_library (imgui STATIC
    ${PROJECT_SOURCE_DIR}/src/imgui.cpp
    ${PROJECT_SOURCE_DIR}/src/imgui_demo.cpp
    ${PROJECT_SOURCE_DIR}/src/imgui_draw.cpp
    ${PROJECT_SOURCE_DIR}/src/imgui_tables.cpp
    ${PROJECT_SOURCE_DIR}/src/imgui_widgets.cpp
    ${PROJECT_SOURCE_DIR}/src/imgui_impl_glfw.cpp
    ${PROJECT_SOURCE_DIR}/src/imgui_impl_opengl3.cpp
)

find_package(OpenGL REQUIRED)
target_link_libraries (imgui LINK_PUBLIC ${OPENGL_LIBRARIES})
target_link_libraries (imgui LINK_PUBLIC glfw)
target_include_directories (imgui PUBLIC ${PROJECT_SOURCE_DIR}/include)

