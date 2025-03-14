# CMakeLists.txt for ImGuizmo

cmake_minimum_required(VERSION 3.10)
project(ImGuizmo)

# Use at least C++11 (required by ImGuizmo)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# List the ImGuizmo source files.
# (You can remove the demo file if you don't want to compile it.)
set(IMGUIZMO_SOURCES
    GraphEditor.cpp
    ImCurveEdit.cpp 
    ImGradient.cpp 
    ImSequencer.cpp
    ImGuizmo.cpp
)

# Create a static library target named "imguizmo"
add_library(ImGuizmo STATIC ${IMGUIZMO_SOURCES})

# Ensure that users of this library will include headers from this directory.
target_include_directories(ImGuizmo PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# Add ImGuizmo to the target link libraries
target_link_libraries(ImGuizmo PRIVATE ImGui)
