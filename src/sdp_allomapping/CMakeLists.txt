cmake_minimum_required(VERSION 2.8.3)
project(sdp_egomapping)

find_package(catkin REQUIRED roscpp depthimage_to_laserscan cob_scan_unifier gmapping)
install(DIRECTORY launch/
   DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)

