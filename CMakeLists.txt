cmake_minimum_required(VERSION 3.1)

# Project properties
SET(PROJECT_ORG laas)
SET(PROJECT_NAME simple_humanoid_description)
set(PROJECT_DESCRIPTION "simple-humanoid URDF model and calibration data")
SET(PROJECT_URL "http://github.com/${PROJECT_ORG}/${PROJECT_NAME}")

# Project configuration
SET(PROJECT_USE_CMAKE_EXPORT TRUE)

# JRL-cmakemodule setup
INCLUDE(cmake/base.cmake)

# Project definition
COMPUTE_PROJECT_ARGS(PROJECT_ARGS LANGUAGES CXX)
PROJECT(${PROJECT_NAME} ${PROJECT_ARGS})

ADD_LIBRARY(${PROJECT_NAME} INTERFACE)
INSTALL(TARGETS ${PROJECT_NAME} EXPORT ${TARGETS_EXPORT_NAME} DESTINATION lib)

FOREACH(dir urdf srdf launch)
  INSTALL(DIRECTORY ${dir} DESTINATION share/${PROJECT_NAME})
ENDFOREACH(dir)

INSTALL(FILES package.xml DESTINATION share/${PROJECT_NAME})
