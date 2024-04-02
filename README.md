# Navigating Turtle bot




https://github.com/shoaib6174/Jderobot--Navigating-Turtlebot/assets/40586752/87173fcf-a3dc-487a-963a-f58a2f94ea11


To reproduce the above result, follow the steps below -

1. Clone this repository in a new ros2 workspace in src directory (`turtlebot3_ws/src`) 
```
git clone https://github.com/shoaib6174/Jderobot--Navigating-Turtlebot.git .
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


