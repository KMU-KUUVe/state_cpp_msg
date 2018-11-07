cmake_minimum_required(VERSION 2.8.3)

project(state_cpp_msg)

set(CMAKE_CXX_FLAGS "-std=c++11 ${CMAKE_CXX_FLAGS}")

find_package(catkin REQUIRED COMPONENTS
  actionlib_msgs
  message_generation
  std_msgs
)

include_directories(${catkin_INCLUDE_DIRS})

add_action_files(
	DIRECTORY action
	FILES MissionPlanner.action
)

generate_messages(
	DEPENDENCIES
	actionlib_msgs
	std_msgs
)

catkin_package(
	CATKIN_DEPENDS
	actionlib_msgs
	message_runtime
	std_msgs
)

