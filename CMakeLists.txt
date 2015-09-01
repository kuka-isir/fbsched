cmake_minimum_required(VERSION 2.8.3)

project(fbsched)

find_package(catkin REQUIRED COMPONENTS rtt_ros)

catkin_package(
  CATKIN_DEPENDS rtt_ros 
)

add_definitions(-DRTT_COMPONENT)
# Creates an orocos component HelloWorld
orocos_component(${PROJECT_NAME} fbsched.hpp fbsched.cpp) # ...you may add multiple source files
target_link_libraries(${PROJECT_NAME} ${catkin_LIBRARIES})

# Additional headers: (installs in the include/orocos/fbsched/ directory)
orocos_install_headers( fbsched.hpp ) # ...you may add multiple header files

# Makes this an installable/usable package for other packages.
#    Must be the last statement such that it can pick up all above settings.
orocos_generate_package()
