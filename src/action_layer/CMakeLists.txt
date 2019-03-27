cmake_minimum_required(VERSION 2.8.3)
project(action_layer)

find_package(catkin REQUIRED COMPONENTS vgazebo_plugins)

catkin_package(
  LIBRARIES ActionLayerLibrary
  CATKIN_DEPENDS vgazebo_plugins
)

add_library(ActionLayerLibrary src/Example1.cpp)

add_dependencies(ActionLayerLibrary ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

target_link_libraries(ActionLayerLibrary ${catkin_LIBRARIES})

#add_executable(action_executive src/Example2.cpp)
#add_dependencies(action_executive ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})
#target_link_libraries(action_executive ActionLayerLibrary)
