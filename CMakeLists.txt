cmake_minimum_required(VERSION 3.5)
project(obstacle_detector_interfaces)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)

set(msg_files
  "msg/CircleObstacle.msg"
  "msg/SegmentObstacle.msg"
  "msg/Obstacles.msg"
)
# set(srv_files
#   "srv/CalcTwoFloats.srv"
# )
rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  # ${srv_files}
  DEPENDENCIES builtin_interfaces geometry_msgs
)
ament_export_dependencies(rosidl_default_runtime geometry_msgs)
ament_package()
