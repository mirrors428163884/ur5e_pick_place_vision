cmake_minimum_required(VERSION 3.22)
project(ur5e_golf_pick_place)

find_package(ament_cmake REQUIRED)

# Install URDF files
install(DIRECTORY urdf/
  DESTINATION share/${PROJECT_NAME}/urdf
)

# Install launch files
install(DIRECTORY launch/
  DESTINATION share/${PROJECT_NAME}/launch
)

# Install config files (e.g., YAML)
install(DIRECTORY config/
  DESTINATION share/${PROJECT_NAME}/config
)

# Install meshes (this fixes your missing directory issue)
install(DIRECTORY meshes/
  DESTINATION share/${PROJECT_NAME}/meshes
)

# Install RViz config if present
install(DIRECTORY rviz/
  DESTINATION share/${PROJECT_NAME}/rviz
  OPTIONAL  # Only if the directory exists
)

# Install worlds if present
install(DIRECTORY worlds/
  DESTINATION share/${PROJECT_NAME}/worlds
  OPTIONAL
)

ament_package()