cmake_minimum_required(VERSION 3.8)

project("SOP_VolumeCenterPoints")

# Find Houdini Package
find_package(Houdini REQUIRED)

# Set the name of the node
set (library_name ${PROJECT_NAME})

# Add a library with the sources
add_library(${library_name} SHARED
    SOP_VolumeCenterPoints.C
    SOP_VolumeCenterPoints.h
)

# Support to compile against Houdini headers
houdini_configure_target(${library_name})


# Target libraries
target_link_libraries(${library_name} PRIVATE Houdini)


target_include_directories(${library_name} PRIVATE
    ${CMAKE_CURRENT_BINARY_DIR}
)
