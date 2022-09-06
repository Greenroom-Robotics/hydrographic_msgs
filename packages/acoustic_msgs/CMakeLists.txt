cmake_minimum_required(VERSION 3.5)

project(acoustic_msgs)

# Generate messages
find_package(ament_cmake_auto REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)

ament_auto_find_build_dependencies()

set(ACOUSTIC_INTERFACES
    msg/DetectionFlag.msg
    msg/Dvl.msg
    msg/PingInfo.msg
    msg/ProjectedSonarImage.msg
    msg/RawSonarImage.msg
    msg/SonarDetections.msg
    msg/SonarImageData.msg
    msg/SonarRanges.msg
)

rosidl_generate_interfaces(${PROJECT_NAME}
    ${ACOUSTIC_INTERFACES}

  DEPENDENCIES
    "std_msgs"
    "geometry_msgs"
  ADD_LINTER_TESTS
)

if(BUILD_TESTING)

endif()

ament_auto_package()