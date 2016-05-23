cmake_minimum_required(VERSION 2.8.3)
project(sdp_egomapping)

find_package(catkin REQUIRED
    roscpp
    rospy
    depthimage_to_laserscan
    cob_scan_unifier
    gmapping)

install(DIRECTORY
    launch/
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)

### TESTS
if(CATKIN_ENABLE_TESTING)
    find_package(roslaunch REQUIRED)
    roslaunch_add_file_check(launch)
endif()


