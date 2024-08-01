cmake_minimum_required(VERSION 3.24)
project(ImGui VERSION 1.0)

set(SOURCES  
    imconfig.h
    imgui.cpp imgui.h
    imgui_draw.cpp
    imgui_internal.h
    imgui_widgets.cpp
    imstb_rectpack.h
    imstb_textedit.h
    imstb_truetype.h
    imgui_demo.cpp
    imgui_tables.cpp
    
    misc/cpp/imgui_stdlib.cpp misc/cpp/imgui_stdlib.h
    
    backends/imgui_impl_glfw.cpp backends/imgui_impl_glfw.h
    backends/imgui_impl_opengl3.cpp backends/imgui_impl_opengl3.h)

source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${SOURCES})

add_library(${PROJECT_NAME} STATIC)
target_sources(${PROJECT_NAME} PRIVATE ${SOURCES})
target_link_libraries(${PROJECT_NAME} glfw)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/backends)
