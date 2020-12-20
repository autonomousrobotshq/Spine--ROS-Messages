cmake_minimum_required(VERSION 3.0.2)
project(teleop)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  llc_messages
  roscpp
  std_msgs
)

find_package(SDL REQUIRED)
set(LIBS ${SDL_LIBRARY})

###################################
## catkin specific configuration ##
###################################

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES teleop
  CATKIN_DEPENDS llc_messages roscpp std_msgs
  DEPENDS sdl
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
  ${SDL_INCLUDE_DIR}
)

add_executable(${PROJECT_NAME}_node src/main.cpp src/teleop.cpp src/keyboard.cpp)

target_link_libraries(teleop
  ${LIBS}
  ${catkin_LIBRARIES}
)

add_dependencies(teleop teleop_gencpp)

#############
## Install ##
#############

install(TARGETS keyboard
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
