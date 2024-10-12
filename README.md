# Navigating Turtle bot

https://github.com/shoaib6174/Navigating-Turtlebot/assets/40586752/87173fcf-a3dc-487a-963a-f58a2f94ea11


This repository demonstrates the usage of the Navigation 2 framework in ROS 2 using a TurtleBot3 simulation in Gazebo. The core task is to make the robot patrol an area, navigating through four pre-configured waypoints on a simulated map. The project is designed to provide a practical introduction to autonomous navigation using ROS 2.

### Tools and Technologies
- Navigation 2 Framework: For autonomous navigation and path planning.
- Behavior Trees (C++): Implementation and integration inspired by BehaviorTree.CPP for flexible decision-making.
- ROS 2 Python Package Usage: Example usage of Python-based ROS 2 packages.
- ROS 2 C++ Package Usage: Demonstration of C++ packages for core functionality.
- ROS 2 Launch System: Utilizing the ROS 2 launch infrastructure for setting up and running simulations.
- Gazebo Simulator: A 3D simulation environment for testing the TurtleBot3 in a virtual environment.
- TurtleBot3: A simulated mobile robot used for demonstrating navigation tasks.





To reproduce the above result, follow the steps below -

1. Clone this repository in a new ros2 workspace in src directory (`turtlebot3_ws/src`) 
```
git clone https://github.com/shoaib6174/Navigating-Turtlebot.git .
```
2. Import TurtleBot3 packages with vcs 
```
vcs import . < turtlebot3.repos
```
3. Build all packages from workspace directory (`turtlebot3_ws`)
```
colcon build --symlink-install
```
4. Source the workspace
```
source ./install/setup.bash
```
5. Export TurtleBot3 model

```
export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:~/turtlebot3_ws/src/turtlebot3/turtlebot3_simulations/turtlebot3_gazebo/models

export TURTLEBOT3_MODEL=waffle_pi
```

6. Launch turtlebot3 simulation infrastructure

```
ros2 launch tb3_sim turtlebot3_world.launch.py
```

7. Launch nav2 infrastructure (nav2 + amcl initial pose)

```
source ./install/setup.bash
ros2 launch tb3_sim nav2.launch.py
```

8. Launch autonomy behavior for demo

```
source ./install/setup.bash
ros2 launch tb3_autonomy autonomy.launch.py
```

This starts our demonstration where TurtleBot moves between 4 different locations in the world simulation.


References:
- https://github.com/thehummingbird/nav2_demo_turtlebot3


