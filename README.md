# ROS-Task.3
# Ros noetic:


# 1. Launch the Turtlesim Node
In the first terminal, source your ROS 2 environment and start the Turtlesim node:



source /opt/ros/foxy/setup.bash
ros2 run turtlesim turtlesim_node
# 2. Publish Velocity Commands Directly from the Terminal
In a new terminal, you can use ros2 topic pub to manually send velocity commands to the turtle. Here are some example commands:

Move Forward:



source /opt/ros/foxy/setup.bash
ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}"
Move Backward:



source /opt/ros/foxy/setup.bash
ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: -2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}"
Turn Left:


source /opt/ros/foxy/setup.bash
ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 2.0}}"
Turn Right:


source /opt/ros/foxy/setup.bash
ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: -2.0}}"
Using the Command Line for Continuous Control
If you want continuous control similar to the teleop keyboard, you can repeatedly send commands by running the command in a loop in the terminal.

Example Loop for Forward Movement:


source /opt/ros/foxy/setup.bash
while true; do ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}"; sleep 0.1; done
You can similarly create loops for other movements.

This approach provides a quick and straightforward way to control the Turtlesim without any additional scripting.
