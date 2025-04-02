# fish_hpurv


## Installation and Setup
Follow these steps to set up and use the `fish_hpurv` package in ROS 2:

1. Clone the package repository:
   ```sh
   git clone https://github.com/konthamaashini/fish_hpurv.git
   ```
2. Navigate to your ROS 2 workspace and build the package using colcon:
   ```sh
   colcon build
   ```
3. Source the workspace (consider adding it to your `~/.bashrc` for convenience):
   ```sh
   source install/setup.bash
   ```
4. Launch the robot model in Gazebo:
   ```sh
   ros2 launch fish_hpurv display.launch.py
   ```

## Package Structure
```
fish_hpurv/
│── urdf/            # Contains the Xacro file for the robot description
│── meshes/          # Stores STL files for the robot model
│── launch/          # Python launch file for spawning the robot
│── world/           # Fish_world to manually check SDF functionality
│── models/          
│   └── fish_hpurv/  # Model folder containing the necessary files
│       ├── model.config   # Model configuration file
│       ├── fish.sdf       # SDF file for Gazebo simulation
│       └── *.stl          # Additional STL files
│── scripts/         # Contains scripts such as joint_publisher.cpp
│── worlds/          # Stores world files for Gazebo
│── CMakeLists.txt   # CMake build system configuration
│── package.xml      # ROS 2 package configuration
│── README.md        # This README file
```
This package allows the simulation of a bio-inspired fish robot in an underwater Gazebo world.

## Running `joint_publisher.cpp`
The `joint_publisher.cpp` script in the `scripts` directory is responsible for publishing joint states. To compile and run it, follow these steps:

1. Ensure the package is built:
   ```sh
   colcon build --packages-select fish_hpurv
   ```
2. Source the workspace:
   ```sh
   source install/setup.bash
   ```
3. Run the joint publisher node:
   ```sh
   ros2 run fish_hpurv joint_publisher
   ```


