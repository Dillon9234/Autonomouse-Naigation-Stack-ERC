cmake_minimum_required(VERSION 3.8)
project(leo_rover)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(urdf REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

ament_export_dependencies(urdf)
ament_export_dependencies(rclcpp)

install(DIRECTORY config launch maps media params worlds urdf models
  DESTINATION share/${PROJECT_NAME}
)

ament_package()
