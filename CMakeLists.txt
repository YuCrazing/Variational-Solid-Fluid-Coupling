cmake_minimum_required(VERSION 3.1...3.25)

set(project_name "coupling")

project(
  ${project_name}
  VERSION 1.0
  LANGUAGES CXX)

# OpenGL && GLUT
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)

aux_source_directory(. CPP_SOURCES)

add_executable(${project_name} ${CPP_SOURCES})

target_include_directories(${project_name}
PRIVATE
  ${CMAKE_CURRENT_SOURCE_DIR}
)
target_include_directories(${project_name}
PRIVATE
  ${OPENGL_INCLUDE_DIRS}
)
target_include_directories(${project_name}
PRIVATE
  ${GLUT_INCLUDE_DIRS}
)

target_link_libraries(${project_name} ${OPENGL_LIBRARIES} ${GLUT_LIBRARIES})