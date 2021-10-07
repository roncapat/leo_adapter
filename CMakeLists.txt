cmake_minimum_required(VERSION 3.0.2)
project(leo_adapter)

find_package(catkin REQUIRED COMPONENTS std_msgs geometry_msgs sensor_msgs nav_msgs)

catkin_package(CATKIN_DEPENDS message_runtime std_msgs geometry_msgs sensor_msgs nav_msgs)

install(
  DIRECTORY
    launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

catkin_install_python(
  PROGRAMS scripts/leo_adapter
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)