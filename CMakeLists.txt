cmake_minimum_required(VERSION 2.8)

PROJECT(Isosurface)
SET(VTK_DIR C:/VTKsrc)
SET(CMAKE_VERBOSE_MAKEFILE ON)
find_package(VTK REQUIRED)
include(${VTK_USE_FILE} ${VTK_DIR}/Rendering)

add_executable(Isosurface Isosurface)


target_link_libraries(Isosurface glu32)
target_link_libraries(Isosurface opengl32)
if(VTK_LIBRARIES)
target_link_libraries(Isosurface ${VTK_LIBRARIES})
else()
target_link_libraries(Isosurface vtkHybrid)
endif()