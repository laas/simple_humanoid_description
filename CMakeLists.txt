cmake_minimum_required(VERSION 3.1)

# Project properties
set(PROJECT_ORG laas)
set(PROJECT_NAME simple_humanoid_description)
set(PROJECT_DESCRIPTION "simple-humanoid URDF model and calibration data")
set(PROJECT_URL "http://github.com/${PROJECT_ORG}/${PROJECT_NAME}")

# Project configuration
set(PROJECT_USE_CMAKE_EXPORT TRUE)

# JRL-cmakemodule setup
include(cmake/base.cmake)

# Project definition
compute_project_args(PROJECT_ARGS LANGUAGES CXX)
project(${PROJECT_NAME} ${PROJECT_ARGS})

add_library(${PROJECT_NAME} INTERFACE)
install(
  TARGETS ${PROJECT_NAME}
  EXPORT ${TARGETS_EXPORT_NAME}
  DESTINATION lib)

foreach(dir urdf srdf launch)
  install(DIRECTORY ${dir} DESTINATION share/${PROJECT_NAME})
endforeach(dir)

install(FILES package.xml DESTINATION share/${PROJECT_NAME})
