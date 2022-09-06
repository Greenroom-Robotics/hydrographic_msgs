cmake_minimum_required(VERSION 3.5)

project(environmental_msgs)

# Generate messages
find_package(ament_cmake_auto REQUIRED)
find_package(std_msgs REQUIRED)

ament_auto_find_build_dependencies()

set(ENVIRONMENTAL_INTERFACES
  msg/TurbidityNTU.msg
)

rosidl_generate_interfaces(${PROJECT_NAME}
    ${ENVIRONMENTAL_INTERFACES}

  DEPENDENCIES
    "std_msgs"
  ADD_LINTER_TESTS
)

if(BUILD_TESTING)

endif()

ament_auto_package()


