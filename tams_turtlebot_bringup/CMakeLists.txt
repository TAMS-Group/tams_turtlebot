cmake_minimum_required(VERSION 3.0.2)
project(tams_turtlebot_bringup)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
)

catkin_package(
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

