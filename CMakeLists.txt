cmake_minimum_required(VERSION 2.8.3)

project(fbsched)

find_package(OROCOS-RTT REQUIRED ${RTT_HINTS})

include(${OROCOS-RTT_USE_FILE_PATH}/UseOROCOS-RTT.cmake)

add_definitions(-DRTT_COMPONENT)

orocos_component(${PROJECT_NAME} fbsched.cpp)

orocos_install_headers( fbsched.hpp )

orocos_generate_package()
