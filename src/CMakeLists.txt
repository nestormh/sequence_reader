
#################################################################
# stereo_and_odom
#################################################################
add_executable(sequence_reader
    ObstaclesFromStereo.cpp
    sequence_reader/calibrationmanager.cpp
    sequence_reader/groundtruthmanager.cpp
    ${LIBELAS_SRC_FILES}
    main.cpp
)

include_directories(sequence_reader
    ${PCL_INCLUDE_DIRS}/pcl-1.7
    ${OpenCV_INCLUDE_DIR}
    ${LIBELAS_INCLUDE_DIRS}
    ${Boost_INCLUDE_DIR}
    /opt/ros/indigo/include
)

link_directories(sequence_reader
    /usr/local/lib
    /usr/lib/x86_64-linux-gnu/
)

target_link_libraries(sequence_reader
  ${EIGEN3_LIBRARIES}
  ${PCL_LIBRARIES}
  ${OpenCV_LIBS}
  ${Boost_LIBRARIES}
  ${catkin_LIBRARIES}
)

# add_dependencies(sequence_reader ${PROJECT_NAME}_generate_messages_cpp)