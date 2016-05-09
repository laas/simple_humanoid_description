cmake_minimum_required(VERSION 2.6)

include(cmake/base.cmake)
include(cmake/ros.cmake)

set(PROJECT_NAME simple-humanoid-description)
set(PROJECT_DESCRIPTION simple-humanoid URDF model and calibration data)
set(PROJECT_URL "")

setup_project()

# Install generated urdf files
install(FILES
  ${CMAKE_SOURCE_DIR}/urdf/simple_humanoid.urdf
  DESTINATION ${CMAKE_INSTALL_DATADIR}/${PROJECT_NAME}/urdf
)

# Install srdf files
install(FILES
  ${CMAKE_SOURCE_DIR}/srdf/simple_humanoid.srdf
  DESTINATION ${CMAKE_INSTALL_DATADIR}/${PROJECT_NAME}/srdf
)

# Install package.xml
install(FILES package.xml
  DESTINATION ${CMAKE_INSTALL_DATAROOTDIR}/${PROJECT_NAME}
)
setup_project_finalize()
