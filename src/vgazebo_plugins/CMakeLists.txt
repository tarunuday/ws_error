cmake_minimum_required(VERSION 2.8.3)

project(vgazebo_plugins)

find_package(catkin REQUIRED COMPONENTS
  gazebo_plugins
)

## System dependencies are found with CMake's conventions
find_package(gazebo 9 REQUIRED)
#find_package(ignition-math4 REQUIRED)
#find_package(ignition-cmake0 REQUIRED)
#find_package(IgnProtobuf REQUIRED)

catkin_package(
  LIBRARIES Example_vgazebo
  CATKIN_DEPENDS gazebo_plugins
  DEPENDS GAZEBO
)

add_library(Example_vgazebo
   src/Example_vgazebo.cpp
 )

add_dependencies(Example_vgazebo ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

target_link_libraries(Example_vgazebo
   ${catkin_LIBRARIES}
   ${GAZEBO_LIBRARIES}
 )
 
